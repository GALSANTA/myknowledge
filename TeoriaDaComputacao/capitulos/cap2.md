<h1 align="center"> Linguagens Livre-do-contexto </h1> 
<br/> 


Neste capítulo, apresentamos **gramáticas livres-do-contexto**, um método mais poderoso de descrever linguagens. Tais gramáticas podem descrever certas características que têm uma estrutura recursiva, o que as torna úteis em uma variedade de aplicações.

Uma aplicação importante de gramáticas livres-do-contexto ocorre na especificação e compilação de linguagens de programação.

A coleção de linguagens associadas com gramáticas livres-do-contexto são denominadas **linguagens livres-do-contexto**. Elas incluem todas as linguagens regulares e muitas linguagens adicionais. Neste capítulo, damos uma definição formal de gramáticas livres-do-contexto e estudamos as propriedades de linguagens livres-do-contexto. Também introduzimos **autômatos com pilha**, uma classe de máquinas que reconhecem as linguagens livres-do-contexto. Autômatos com pilha são úteis porque nos permitem ganhar melhor percepção cobre o poder de linguagens livres-do-contexto.


## 2.1 Gramáticas Livres-do-Contexto
<br/> 

Segue um exemplo de uma gramática livre-do-contexto chamada $G_1$.



<center>

$A \longrightarrow 0A1$
<br/>
$A \longrightarrow B$
<br/>
$B \longrightarrow \#$
</center>

Uma gramática consiste de uma coleção de **regras de substituição** tamtém denominadas **produções**. Cada regra aparece como uma linha na gramática, compreendendo um símbolo (A) e uma cadeia (0A1) separados por uma seta. A cadeia é constituída de variáveis e outros símbolos chamados **terminais**. Os símbolos de variáveis são representados por letras maiúsculas. Os terminais são análogos ao alfabeto de entrada e são representados por letras minúsculas, números ou simbolos especiais. Uma variável é designada como a **variável inicial** e ela ocorre no lado esquerdo da primeira regra. Por exemplo, a gramática $G_1$ contém três regras. As variáveis de $G_1$ são $A$ e $B$, sendo $A$ a variável inicial. Seus terminais são 0,1 e #.

Você usa uma gramática para descrever uma linguagem gerando cada cadeia dessa linguagem da seguinte maneira:

<ol>
    <li>Escreva a variável inicial. Ela é a variável no lado esquerdo da primeira regra.</li>
    <li>Encontre uma variável que esteja escrita e uma regra que comece com essa variável. Substituia a variável escrita pelo lado direito dessa regra.</li>
    <li>Repita o passo 2 até que não reste nenhuma variável</li>
</ol>

Por exemplo, a gramática $G_1$ gera a cadeia 000#111. A sequência de substituições para obter uma cadeia é denomidada **derivação**. Uma derivação da cadeia 000#111 na gramática $G_1$ é:

<center>

$A \Rightarrow 0A1 \Rightarrow 00A11 \Rightarrow 000A111 \Rightarrow 000B111 \Rightarrow 000\#111$
</center>

Você também pode apresentar a mesma informação pictorialmente com uma **árvore sintática**. Um exemplo de ávore sintática para a 000#111 na gramática $G_1$.

<center>

```mermaid
  stateDiagram-v2
    r10: 0
    r20: 0
    r30: 0
    r40: 0
    q1:A
    q2: A
    q3: A
    q4: A
    q5: B
    q6: #
    r11: 1
    r21: 1
    r31: 1
    r41: 1
      q1-->r11: 
      q1-->r10: 
      q1-->q2: 
      q2-->r21: 
      q2-->r20: 
      q2-->q3: 
      q3-->r31: 
      q3-->r30: 
      q3-->q4: 
      q4-->r41: 
      q4-->r40: 
      q4-->q5: 
      q5-->q6: 
```
</center>


O conjunto de todas as cadeias deradas dessa maneira constitui a **linguagem da gramática**. Escrevemos $L(G_1)$ para a linguagem da gramática $G_1$. Sabemos também que $L(G_1)$ é {$0^n \# 1^n | n \geq 0$}. 

### 2.1.1 Definição formal de uma gramática livre-do-contexto
<br/> 

Uma gramática livre-do-contexto é uma 4-upla ($V , \Sigma , R, S$), onde:

* $V$ é o conjunto finito denominado **variáveis**
* $\Sigma$ é um conjunto finito, disjunto de $V$, denominado **terminais**
* $R$ é um conjunto finito de **regras**, com cada regra sendo uma variáveis e terminais
* $S \in V$ é a **variável inicial**

 
### 2.1.2 Projetando gramáticas livres-do-contexto
<br/> 

### 2.1.3 Ambiguidade
<br/> 

### 2.1.4 Forma normal de Chomsky
<br/> 

## 2.2 Autômato com pilha
