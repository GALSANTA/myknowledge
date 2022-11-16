<h1 align="center">2. Processos e Threads</h1>

## 2.1 Processos

<br/>

### **2.1.1 Modelo do processo**

 Processos são estrutura de dados que representam instâncias de programas em execução, incluindo nisso valores atuais de registradores, contadores , variáveis e e os recursos utilizados (arquivos abertos, processos relacionados ...). Embora o usuário tenha a ideia de um parelismo, na realidade, a CPU (com 1 núcleo) vai e volta de processo em processo através de uma algoritmo escalonador de processos que decide quando parar e quando começar outro processo . Essa rápida troca é chamada de multiprogramação. 

**Multiprogramação**: Multiprogramação (ou time-sharing) é o chaveamento entre a execução de vários processos criando a ilusão de uma execução em paralelo.

<br/>

### **2.1.2 Criação de Processo e  Hierarquia de Processo**

Todos os processos instanciados são filhos de um processo pai e existe um processo que é inicializado ao realizar o carregamento do Sistema Operacional. No linux, esse processo é chamado de systemd.Um PID é um identificador único para um processo. Na família de SO UNIX existe uma operação chamada fork. Essa operação clona o processo em dois. O resultado do fork no filho retorna 0 e no pai retorna o PID do filho.
imagem de fork

<br/>

### **2.1.3 Estados do processo**

<center>
    <img src="../assets/estados-processos.jpg"/>
</center>
<br/>
Existem três principais estados para um processo: Bloqueado, Rodando e Pronto para Rodar. Segue um exemplo abaixo de troca de contexto.
<br/>
<ol>
    <li>
    Através da exceção ou interrupção, no caso onde um processo que está em estado de "pronto" e aguardando CPU,  é escolhido (escalonado), esse processo passa a ocupar a CPU dado que a fatia de tempo destinada ao processo que estava em estado de "executando" acabou.
    </li>
    <li>
     Essa transição ocorre em consequência de uma interrupção de hardware. Um dispositivo requer atenção. O relógio de hardware gera uma interrupção para indicar que a fatia de tempo destinada ao processo acabou.
    </li>
    <li>
        Essa transição ocorre, devido a uma exceção, quando um processo de usuário solicita algo ao sistema operacional através de um system call. Por exemplo  um programa que espera a entrada do teclado, sendo então necessário esperar para receber essa entrada.
    </li>
    <li>
        Essa transição corre através da exceção ou interrupção em que a solicitação de um processo que estava em estado de "bloqueado" é atendida pelo SO. O processo irá ocupar um posição na fila de prontos onde será em seguida escolhida pelo escalonador.
    </li>
</ol>



## 2.2 Threads

## 2.3 Comunicação entre Processos

<br/>

### **2.3.1 Condição de corrida**

É uma situação onde os eventos que ocorrem podem influenciar na execução de processos, especialmente quando existem vários fluxos de execução "simultâneos", e também soluções para esse problema.

Para entender possíveis problemas que podem acontecer com vários processos operando sobre uma mesma Área de Memória Compartilhada, imagine a seguinte situação: um usuário possui uma conta no banco que tem R$ 1.000,00. Ele deseja fazer uma compra de R$ 100,00 com seu cartão de débito e, ao mesmo tempo, ele recebe seu pagamento mensal de R$ 3.500,00. Neste caso, existirão dois processos concorrentes, um que vai retirar 100 reais de sua conta, e outro que vai adicionar 3500.

Como o sistema operacional do banco implementa o pseudo-paralelismo, ele tem que realizar o chaveamento de processos. Imagina que o primeiro processo faz a diferença, verifica que o novo saldo é de 900 reais, e no instante em que ele vai fazer a atualização desse valor, a CPU o interrompe e faz o chaveamento para o outro processo que adiciona 3500 reais em sua conta. Para esse outro processo, o valor ainda é 1000, então quando fizer a soma, vai ficar 4500 reais na conta do usuário. Porém, quando esse segundo processo parar de executar, e o anterior ganhar a CPU novamente, ele não terá a informação da atualização do e vai salvar como 900 reais.

Ou seja, o saldo final desse usuário ficará R$ 900,00. Isso dá a impressão que o sistema "ignorou" o pagamento recebido pelo usuário, já imaginou a confusão que isso causaria?

Quando acontece?
Para existir uma condição de corrida, é necessário que vários fluxos de execução (processos ou threads) operem sobre tais recursos compartilhados e, quando um desses fluxos vai executar pressupondo um estado inicial dos recursos, algo acontece entre a obtenção de tal estado, alterando-o, e a execução final.

É importante ter em mente que a condição de corrida não é um erro, e sim inerente a alguns problemas, e não há como fugir. O possível erro ocasionado por uma condição de corrida só ocorre se não for devidamente tratado.


### **2.3.2 Região critica**

A região crítica de um determinado processo é a parte de seu código que acessa a **área de memória compartilhada** que, como o próprio nome sugere, é um conjunto de recursos que podem ser compartilhados entre dois ou mais processos, por exemplo, memória, variáveis, arquivos, etc. Essa área depende expressivamente que a parte do processo que a acessa tenha sua execução de forma sequencial, e esse é um dos principais fatores que influenciam para a ocorrência de uma condição de corrida.

### **2.3.3 Exclusão mútua**

Exclusão mútua é uma forma de garantir a prevensão de situações onde há compartilhamento de mémoria, compartilhamento de arquivo e compartilhamento de qualquer outra coisa nas regiões críticas, garantindo que nenhum outro processo possa executar até que o primeiro processo acessando essa região termine. São soluções de exclusão mútua:

* Espera ocupada Espera ocupada (busy wait)
* Semafóros
* Mutex
* Monitores

### **2.3.4 Espera ocupada (busy wait)**

Uma solução baseada em espera ocupada consiste em: um fluxo de execução, antes de entrar na região crítica, precisa passar por uma verificação para saber se ele pode ou não entrar lá. Caso não possa e já exista outro processo executando sua região crítica, ele fica em loop até que ele possa ganhar essa região.

Um dos exemplos mais conhecidos de solução para condição de corrida que implementa a espera ocupada é a **Solução de Peterson** ou **Algoritmo de Peterson**. O código abaixo exemplifica como essa solução pode ser implementada para resolver esse problema com dois fluxos alternativos de execução:

<br/>

```c
// suponha que existam dois processos, i = 0 e j = 1

int vez = 0; // indica de quem é a vez
bool interessado[2]; // array que indica quem está interessado em acessar a região crítica

// Código de entrada na região crítica
void entraNaRegiaoCritica(int processo) {
  int other = 1 - processo; // representa o outro processo
  vez = processo;
  interessado[processo] = true;
  while(vez == processo && interessado[other] == true); // fica em loop, caso não possa entrar
}

// Código para saída da região crítica
void saiDaRegiaoCritica(int processo) {
  interessado[processo] = false; // indica que o processo que estava na região crítica terminou sua atividade.
}

// Código que exemplifica o 'main' em um dos fluxos de execução
int main() {
  int ID = 1;s
  entraNaRegiaoCritica(ID);
  acessaArquivoCompartilhado(); // código de acesso à região crítica.
  saiDaRegiaoCritica(ID);

  return 0;
}
```




### **2.3.4 Semáforos e Mutex**

Semáforos e Mutex são variáveis do tipo inteiro utilizada para controlar acesso a recursos compartilhados.


### Semáforo 

* semáforo = 0 não há recurso livre
* semáforo > 0 recurso livre


#### **wait** 

1. verifica se o valor do semáforo é maior que 0.
2. se for, semáforo = semáforo -1, executa 
3. se for 0, o processo que executou o wait é colocado para dormir, sem completar o wait

#### **signal** 

1. semaforo = semaforo +1
2. se há processos dormindo nesse semaforo escolhe um deles e o desbloqueia, nesse caso o valor do semaforo permanece o mesmo.

### Mutex

* mutex = 0 não há recurso livre
* mutex = 1 recurso livre

#### **wait** 

1. verifica se o valor do mutex é igual 1.
2. se for 1, mutex = mutex -1, executa 
3. se for 0, o processo que executou o wait é colocado para dormir até que o processo que está acessando essa região critíca dê o signal.

#### **signal** 

1. mutex = mutex + 1

<br/>

O solução foi proposta por E. W. Disjktra em 1965.  Disjktra prôpos que as operações se chamassem de _down_ (wait) e _up_ (signal). Para melhor didática podemos representar na prática semáforos e mutex pelo problema do Produtor-Consumidor.

```c

#define N 100 // number of slots in the buffer
typedef int semaphore; // semaphores are a special kind of int
semaphore mutex = 1; // controls acces to critical regions
semaphore empty = N; // counts empty buffer slots
semaphore full = 0; // counts full butter slots

void producer(void) {

    int item;

    while(TRUE) {
        item = produce_item();
        wait(&empty);
        wait(&mutex);
        insert_item(item);
        signal(&mutex);
        signal(&full);
    }
}

void consumer(void) {

    int item;

    while(TRUE) {
        wait(&full);
        wait(&mutex);
        item = remove_item();
        signal(&mutex);
        signal(&full);
        consume_item(item);
    }
}
```

### **2.3.5 DeadLocks**

Segundo Tanenbaum, deadlock pode ser definido como: “Um conjunto de processos estará em situação de deadlock se todo processo pertencente ao conjunto estiver esperando por um evento que somente um outro processo desse mesmo conjunto poderá fazer acontecer”.

De uma forma mais simples, para melhor entendimento, podemos dizer que deadlock é um termo empregado para traduzir um problema ocorrido quando um grupo de processos competem entre si. A ocorrência do deadlock depende das características de dois ou mais programas diferentes e dos respectivos processos a executar pelos diferentes programas ao mesmo tempo. Pode ser, que esses processos possam ser executados de forma repetitiva usando diferentes processos sem que ocorra deadlock, todavia, basta um único processo padrão complicado para entrar em situação de deadlock.

Mesmo não relacionado a computação, podemos citar um exemplo de situação de deadlock que facilita o entendimento do que seja uma situação de deadlock. Dois carros estão seguindo em direções opostas, um de encontro ao outro, em uma pista que permite apenas a passagem de um veículo. Nesse caso os dois ficam impedidos de continuar seu percurso.

Existem quatro condições para a ocorrência de deadlock:

Condição de exclusão mútua. Em um determinado instante, cada recurso está em uma de duas situações: ou associado a um único processo ou disponível.
Condição de posso e espera. Processos que, em um determinado instante, retêm recursos concedidos anteriormente podem requisitar novos recursos.
Condição de não preempção. Recursos concedidos previamente a um processo não podem ser tomados a força desse processo, eles devem ser explicitamente liberados pelo processo que os retém.
Condição de espera circular. Deve existir u encadeamento circular de dois ou mais processos; cada um deles encontra-se à espera de um recurso que está sendo usado pelo membro seguinte dessa cadeia.

## 2.4 Escalonamento

Troca de contexto é quando um processo é retirado de execução para que outro seja executado. Escalonador é responsável por realizar a troca de contexto entre os processos em execução.
