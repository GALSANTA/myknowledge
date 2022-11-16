<h1 align="center">1. Introdução à probabilidade</h1>

<br/>

## 1.1 Conceitos iniciais

### **Esperimento Determinístico**: São experimentos os quais repetidos sob mesmas condições levam ao mesmo resultado.
s
<br/>

### **Experimento Aleatório ($\epsilon$)**: São experimentos os quais quando repetidos sob mesmas condições levam a resultados geralmentes diferentes.

<br/>

### **Espaço Amostral ($\Omega$)**: Ao conjunto de todos os possíveis resultados de um experimento aleatório damos o nome de espaço amostral.

<br/>

### **Evento**: Seja $\Omega$ um espaço amostral associado a um esperimento $\epsilon$. Um evevto é quaisquer subconjunto desse espaço amostral, podendo assumir quaisquer notação.

<br/>

### **Eventos Mutuamente Excludentes (ou disjuntos)**: Dois eventos A e B são ditos mututamente excludentes (ou disjuntos) se eles não puderem ocorrer simultaneamente, ou seja, $ A \cup B = \oslash $. 

<br/>

### **Leis de De Morgam**:

* $(A \cup B)^c  = A^c \cap B^c$
*  $(A \cap B)^c = A^c \cup B^c $

<br/>

### **Exercícios**:

**Exercício 1**: Considere o fenômeno aleatório que consiste em lançar um dado honesto. Sejam os seguintes eventos. </br>
a) A: ocorrer um número ímpar. </br>
b) B: ocorrer um número par. </br>
c) C: ocorrer um número maior que 3. </br>
d) Os eventos A e B são disjuntos? </br>
e) Os eventos A e C não são disjuntos? </br>
f) Os eventos B e C não são disjuntos?

> **Respostas Exercício 1**: </br>
a) A = {1,3,5} </br>
b) B = {2,4,6} </br>
c) C = {4,5,6} </br>
d) Sim, A  $\cap$ B = $\oslash$ </br>
e) Sim, A  $\cap$ C = {5} $\neq$ $\oslash$ </br> 
f) Sim, B  $\cap$ C = {4,5} $\neq$ $\oslash$

**Exercício 2**: Lança-se um dado e observa-se o número da face superior. Considere este experimento aleatório e os eventos a seguir:

 * A: O número da face superior ser par.
 * B: O número da face superior ser menor que 4.

Determine em notação de conjuntos os seguintes eventos:

a) $A \cup B$ </br>
b) $A \cap B$ </br>
c) $A^c$ </br>
d) $B^c$ </br>
e) $(A \cup B)^c$ </br>
f) $(A \cap B)^c$ </br>
g) $A^c \cup B^c$ </br>
h) $A^c \cap B^c$ </br>
i) $A^c - B^c = A \cap B^c$  </br>
j) $B - A = B \cap A^c$  </br>

<br/>

> **Respostas Exercício 2**: </br>
Sabendo que $\Omega$ = {1,2,3,4,5,6}, que A = {2,4,6} e que B = {1,2,3}. </br></br>
a) $A \cup B$ = {1,2,3,4,6}</br>
b) $A \cap B$  = {2} </br> 
c) $A^c$ = {1,3,5} </br>
d) $B^c$ = {4,5,6} </br>
e) $(A \cup B)^c$ = {5} </br>
f) $(A \cap B)^c$ = {1,3,4,5,6} </br>
g) $A^c \cup B^c$ = {1,3,4,5,6}</br>
h) $A^c \cap B^c$ = {5}</br>
i) $A^c - B^c = A \cap B^c$ = {4,6}  </br>
j) $B - A = B \cap A^c$ = {1,3} </br>

<br/>

## 1.2 Teoria das probabilidades: Abordagem clássica.

<br/>

### **Modelo probabilístico**

Em resumo, todo fenômeno aleatório terá seu modelo probabilístico especificado quando estabelecermos:

a) Um espaço amostral ($\Omega$) que consiste, no caso discreto, da enumeração (finita ou infinita) de todos os resultados possíveis do fenômeno em questão. $\Omega$= {$\omega_1,  \omega_2, ..., \omega_n, ...$}

b) Uma probabilidade, P($\omega_i$) para cada ponto amostral $\omega_i$ , de modo que seja possível encontrar a probabilidade P(A) de qualquer subconjunto (evento) A de $\Omega$.

<br/>

### **Abordagem clássica definição**

Se $\Omega$ for um espaço _finito_ e _equiprovável_ podemos utilizar a abordagem clássica para definir a probabilidade de um evento A $\subset \Omega$.

Seja $\Omega$ um espaço amostral finito, $\Omega$ = {$\omega_1,  \omega_2, ..., \omega_n$}, em que todos os
pontos amostrais têm mesma probabilidade $\dfrac{1}{n}$. Se A for um evento com m pontos amostrais, então:

m = número de casos favoráveis à ocorrência do evento A

n = número de casos possíveis

$\dfrac{m}{n} = \dfrac{A}{\Omega}$

<br/>

**Exemplo**: Considere o lançamento de dois dados honestos. Considere os evento:

A: soma dos números obtidos igual a 9.

B: número de primeiro dado maior do que o segundo.

a) Enumere os elementos de A, B, A $\cap $ B e A $ \cup $ B. 

b) Calcule a probabilidade dos eventos dados no item a).

<br/>

> **Respostas**: </br>
a) </br>
A = {(3,6);(4,5);(5,4);(6,3)}</br>
B = {(2,1);(3,1);(4,1);(5,1);(6,1);(3,2);(4,2);(5,2);(6,2);(4,3);(5,3);(6,3);(5,4);(6,4);(6,5)}</br>
A $\cap$ B = {(6,3);(5,4)} </br>
A $\cup$ B = {(2,1);(3,1);(3,6);(4,1);(4,5);(5,1);(6,1);(3,2);(4,2);(5,2);(6,2);(4,3);(5,3);(6,3);(5,4);(6,4);(6,5)} </br><br/>
b) </br><br/>
$P(A)=\dfrac{A}{\Omega} = \dfrac{4}{36}$ <br/><br/>
$P(B)=\dfrac{B}{\Omega} = \dfrac{15}{36}$ <br/><br/>
$P(A \cap B)=\dfrac{A \cap B}{\Omega} = \dfrac{2}{36}$ <br/><br/>
$P(A \cup B)=\dfrac{A \cup B}{\Omega} = \dfrac{17}{36}$ <br/><br/>

<br/>

### **Espaços amostrais finitos**
Vamos considerar agora experímentos para os quais o espaço amostra $\Omega$ seja um conjunto finito, **não necessariamente equiprovável**, ou seja, o espaço $\Omega$  é da forma <br/>
    
<center>

$\Omega$ = {$w_1$, $w_2$, ..., $w_k$ }

</center>

A fim de caracterizar P(A) para este espaço, devemos inicialmente considerar o evneto formado por um resultado simples, do tipo {$w_i$}. A cada evento simples {$w_i$} associaremos um número $p_i$, denominado probabilidade de  {$w_i$} que satisfaça as seguintes condições:

<center>

a) $p_i \geq 0, i-1,...,k$ <br/>
b) $p_1+p_2+...+p_k = 1$
</center>

**Exemplo**: Um dado é viciado, de tal forma que a probabilidade de sair um centro ponto é dada pela expressão $p_i= P({i}) = \dfrac{i}{21}$ com i = 1,2,3,4,5,6. Calcule a probabilidade dos seguintes eventos.

a) A: sair um número par.

b) B: sair um número ímpar.

c) C: sair um número maior que 4.

> **Respostas**: </br> 
a) P(A) = $p_2$+$p_4$+$p_6$ = $P({2})+P({4})+P({6}) = \dfrac{2}{21}+ \dfrac{4}{21}+ \dfrac{6}{21} = \dfrac{12}{21}$ <br/><br/>
b) P(B) =  $p_1$+$p_3$+$p_5$ = $P({1})+P({3})+P({5}) = \dfrac{1}{21}+ \dfrac{3}{21}+ \dfrac{5}{21} = \dfrac{9}{21}$ <br/><br/>
c) P(C) =  $p_5$+$p_6$ = $P({5})+P({6}) =\dfrac{5}{21}+ \dfrac{6}{21} = \dfrac{11}{21}$ <br/><br/>

<br/>

## 1.3 Teoria das probabilidades: Abordagem Axiomática.

<br/>

### **Definição Axiomática de probabilidade**
Considere um experimento cujo espaço amostral e $\Omega$. Para cada evento A espaço amostral $\Omega$, associaremos um número real representado por P(A) e denominado **probabilidade** de A, que satisfaça os três axiomas a seguir.

<center>

**Axioma 1:** 0 $\leq P(A)\leq 1$

**Axioma 2:** $ P(\Omega) = 1$

**Axioma 3:** Se $A_1, A_2, ..., A $ é uma sequência de eventos dois a dois mutuamente excludentes (ou disjuntos), ou seja, $A_i \cap A_j$ = $\oslash$,  
</center>

<br/>

### **Propriedades**

* P($\oslash$) = 0, em que $\oslash$ denota o conjunto vazio.
* P($A^c$) = 1 - P($A$), em que $A^c$ é o evento complementar de $A$.
* P($A \cap B^c$) = P($A$) - P($A \cap B$)
* P($A^c \cap B$) = P($B$) - P($A \cap B$)
* P($A\cup B$) = P($A$) + P($B$) - P($A \cap B$)

**Exemplo**: Pedro leva dois livros para ler durante as férias. A probabilidade de ele gostar do primeiro livro é de 0,7 e de gostar do segundo livro é de 0,4 e de gostar de ambos os livros é de 0,3. Calcule a probabilidade de que ele:

a) goste de pelo menos um dos livros.

b) não goste nem do primeiro e nem do segundo livro.

c) goste apenas do primeiro livro.

d) goste de exatamente um dos livros.

> **Respostas**: </br>
a) P($A \cup B$) = P($A$) + P($B$) - P($A \cap B$) = 0,7 + 0,4 - 0,3 = 0,8. <br/><br/>
b) P($A^c \cup B^c$) = 1 - P($A \cup B$) = 1 - 0,8 = 0,2. <br/><br/>
c) P($A \cap B^c$) = P($A$) - P($A \cap B$) = 0,7 - 0,3 = 0,4. <br/><br/>
d) P[($A \cap B^c$) $\cup$ ($A^c \cap B$)] = P($A \cap B^c$) + P($A \cap B^c$) = <br/>
P($A$) - P($A \cap B$) + P($B$) - P($A \cap B$) = <br/> 
P($A$) + P($B$) - $2 \cdot P(A \cap B$) = <br/>
$ 0,7 + 0,4 -  2 \cdot 0,3 = 0,5$

<br/>

## 1.4 Teoria das probabilidades: Probabilidade Condicional.

<br/> 

### **Motivação**

Em algumas situações a probabilidade de ocorrência de um certo evento pode ser afetada se tivermos algumas informações sobre a ocorrência ou não de um outro evento.

**Exemplo**: Considere o experimento aleátorio que consiste no lançamento de um dado honesto. Considere, agora, os seguintes eventos:

* A: sair um número par.
* B: sair um número diferente de 4.

Obtenha as seguintes probabilidades: P($A$), P($B$) e P($A \cap B$).

<br/>

> **Respostas**: </br>
P($A$) = $\dfrac{A}{\Omega}$ = $\dfrac{3}{6}$ = $0,5$ <br/><br/>
P($B$) = $\dfrac{B}{\Omega}$ = $\dfrac{5}{6}$ = $0,83$ <br/><br/>
P($A \cap B$) = $\dfrac{P(A \cap B)}{\Omega}$ = $\dfrac{2}{6}$ $\approx$ $0,33$ <br/><br/>

<br/>

### **Probabilidade Condicional**
Agora considere que soubéssemos da ocorrência de B = {1,2,3,5,6} e que quiséssimos calcular a probabilidade de A = {2,4,6}. Assim P(A) dado que P(B) ocorreu seria algo como $\dfrac{2}{5}$. Formalmente, definimos probabilidade condicional de A dado a ocorrência de B da seguinte maneira.

<br/>
<center>

$P(A | B)$ = $\dfrac{P(A \cap B)}{P(B)}$, desde que $P(B) > 0$ 
</center>
<br/>

**Exemplo**: Considerando o contexto do exemplo anterior, calcule $P(A|B)$ utilizando a definição formal de probabilidade condicional.

> **Resposta**: </br>
$P(A | B)$ = $\dfrac{P(A \cap B)}{P(B)} = \dfrac{ \dfrac{2}{6}}{\dfrac{5}{6}} = 0,40$