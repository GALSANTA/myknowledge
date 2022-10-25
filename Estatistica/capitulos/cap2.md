## 2. Introdução à probabilidade.

## 2.1 Conceitos iniciais

### **Esperimento Determinístico**: São experimentos os quais repetidos sob mesmas condições levam ao mesmo resultado.

### **Experimento Aleatório ($\epsilon$)**: São experimentos os quais quando repetidos sob mesmas condições levam a resultados geralmentes diferentes.

### **Espaço Amostral ($\Omega$)**: Ao conjunto de todos os possíveis resultados de um experimento aleatório damos o nome de espaço amostral.

### **Evento**: Seja $\Omega$ um espaço amostral associado a um esperimento $\epsilon$. Um evevto é quaisquer subconjunto desse espaço amostral, podendo assumir quaisquer notação.

### **Eventos Mutuamente Excludentes (ou disjuntos)**: Dois eventos A e B são ditos mututamente excludentes (ou disjuntos) se lees não puderem ocrrer simultaneamente, ou seja, $ A \cup B = \oslash $.

### **Leis de De Morgam**:

* $(A \cup B)^c  = A^c \cap B^c $
*  $(A \cap B)^c = A^c \cup B^c $

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


## 2.2. Teoria das probabilidades: Abordagem clássica.

### Modelo probabilístico

Em resumo, todo fenômeno aleatório terá seu modelo probabilístico especificado quando estabelecermos:

a) Um espaço amostral ($\Omega$) que consiste, no caso discreto, da enumeração (finita ou infinita) de todos os resultados possíveis do fenômeno em questão. $\Omega$= {$\omega_1,  \omega_2, ..., \omega_n, ...$}

b) Uma probabilidade, P($\omega_i$) para cada ponto amostral $\omega_i$ , de modo que seja possível encontrar a probabilidade P(A) de qualquer subconjunto (evento) A de $\Omega$.

### Abordagem clássica definição

Se $\Omega$ for um Espaço Finito e Equiprovável podemos utilizar a abordagem clássica para definir a probabilidade de um evento A $\subset \Omega$.

Seja $\Omega$ um espaço amostral finito, 00$\Omega$ = {$\omega_1,  \omega_2, ..., \omega_n$}, em que todos os
pontos amostrais têm mesma probabilidade 1/n. Se A for um evento com m pontos amostrais, então:

m = número de casos favoráveis à ocorrência do evento A

n = número de casos possíveis

$\dfrac{m}{n} = \dfrac{A}{\Omega}$

### Espaços amostrais finitos

## 2.3. Teoria das probabilidades: Abordagem Axiomática.

## 2.4. Teoria das probabilidades: Probabilidade Condicional.