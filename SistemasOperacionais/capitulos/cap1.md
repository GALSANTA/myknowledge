<h1 align="center">1. Sistema operacional</h1>

## 1.1 O que é sistema operacional

O sistema operacional é um software, ou conjunto de softwares, cuja função é administrar e gerenciar os recursos de um sistema, desde componentes de hardware e sistemas de arquivos a programas de terceiros, estabelecendo a interface entre o computador e o usuário.

### Funções de um sistema operacional

O sistema operacional tem como uma de suas funções prover para os programas do usuário abstrações, por meios de processos, sistemas de arquivos, etc. Além disso, o sistema operacional é responsável por gerenciar os recursos da máquina e controlar os periféricos. Por fim, um computador pode conter muitas informações que os usuários querem proteger ou manter confidêncial. Portanto, um das funções do sistema operacional é gerenciar o sistema de segurança para que esses arquivos, por exemplo, sejam acessíveis apenas para alguns usuários autorizados.

## 1.2 História dos sistemas operacionais

## 1.3 Hardware de um computador

## 1.4 Conceitos de um sistema operacional

### Macanismos básicos do sistema operacional

**System Call**: As system calls são chamadas síncronas ao sistema feitas pelos programas que solicitam um serviço do kernel (como acesso ao hardware ou criação de novos processos por exemplo), portanto, são situações "esperadas" e previsíveis.

**Exceções (Traps)**:  A excução de uma chamada ao sistema gera uma exceção no modo kernel, ou seja, ela será tratada pelo próprio sistema operacional e, através de uma tabela pre determinada, o SO determina qual será a rotina a ser executada.

**Interrupções**: As interrupções são causadas pelo próprio hardware e são assícronos. No sentido que não são sincronizadas com a execução do código das aplicações e do kernel. Geralmente são vinculadas aos eventos de I/O ou do clock. São importantes pois, como o exemplo do clock, ajudam o escalonador a realizar a troca de contexto.
