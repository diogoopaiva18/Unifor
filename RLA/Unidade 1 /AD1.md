<img src="https://drive.google.com/uc?id=1SOzRTjUt7cuBJpSqoK90fcAiKBrnpUJo" width="400">

**Curso:** Engenharia de Computação <br>
**Disciplina:** Raciocínio lógico e algoritmo <br>
**Código/Turma:** T998-08 <br>
**Professor:** Ricardo Carubbi <br>
**Data:** 21/03/24 <br>
**Aluno(a):** Diogo Oliveira Paiva do Nascimento <br>
**Matrícula:** 2410314 <br>

**1a chamada (Sim/Não):** Não <br>
**2a chamada (Sim/Não):** Sim

# Avaliação Diagnóstica 1

## Normas e exigências

Avaliação diagnóstica (**AD**) consiste em exercícios ou projetos desenvolvidos em grupo ao longo da disciplina. <br>
A primeira avaliação diagnóstica (**AD1**) será composta por exercícios e equivale a 30% da nota da primeira avaliação (**AV1**).

Segue abaixo a expressão para o cálculo da **AV1**, sendo sendo **AF1** equivale a primeira avaliação formativa e **AD1**, a primeira avaliação diagnóstica.

$$AV_1 = AF_1 \times 0,30 + AD_1 \times 0,70$$

A **AD1** é formada pela entrega dos exercícios (**EX1**) na data prevista e apresentação (**AP1**) de um dos exercícios escolhido pelo professor.
Segue abaixo a expressão para o cálculo da **AD1**.

$$AD_1 = (EX1_1 + AP_1)/2 $$

A **EX1** é avaliada mediante a **correção dos exercícios**, sendo a avaliação no intervalo de 0% (não atende a questão), 50% (atende parcialmente) e 100% (atende em sua totalidade).
Por exemplo, se o exercício equivale a 2 pontos e sua correção atente parcialmente a questão, então sua avaliação deste exercício será 1 ponto.

A **AP1** é avaliada mediante aos pré-requisitos de **clareza, organização e domínio do conteúdo**. Portanto, o aluno deve demonstrar um bom entendimento do algoritmo, explicando seus princípios fundamentais, seu propósito e como ele funciona passo a passo. <br>

A avaliação da **AP1** é apenas considerada no intervalo de 0% (não atende os pré-requisitos), 25% (pouco atende os pré-requisitos), 50% (atende de forma mediana os pré-requisitos), 75% (atende de forma razoável os pré-requisitos) e 100% (atende em a totalidade dos pré-requisitos).
Por exemplo, se na apresentação do exercício, o aluno atenter de forma razoável a questão, então sua avaliação da apresentação será 7.5 pontos.

## Datas
- Entrega da primeira avaliação formativa (**AF1**) composta pelas listas de exerciícios 1, 2 e 3: 21/03/24
- Entrega dos exercícios da primeira avaliação diagnóstica (**EX1**): 21/03/24
- Apresentação da primeira avaliação diagnóstica (**AP1**): 21/03/24

## Lista de questões

### Questão 1 - Troca dos valores de duas variáveis (1 ponto)

Dadas duas variáveis, $a$ e $b$, implemente e teste um algoritmo para trocar os valores atribuídos a elas.

#### Descrição geral do algoritmo

1. Guardar o valor original da variável $a$ em uma variável auxiliar $aux$;
2. Atribuir à variável $a$ o valor original da variável $b$;
3. Atribuir à variável $b$ o valor original da variável $a$, que está armazenado na variável auxiliar $aux$.
4. Exibir os novos valores de $a$ e $b$.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o valor da a: }}
B --> C[\a\]
C --> D{{Digite o valor da b: }}
D --> E[\b\]
E --> F[aux = a]
F --> G[a = b]
G --> H[b = aux]
H --> I{{"a =", a}}
I --> J{{"b =", b}}
```

#### Pseudocódigo (1 ponto)

```
1 Algoritmo TrocaValores
2 DECLARE a, b, aux
3 ESCREVA: Digite o valor de a:
4 ESCREVA: Digite o valor de b:
5 INICIO
6 LEIA a, b
7 aux = a
8 a = b
9 b = aux
ESCREVA "a =", a
ESCREVA "b =", b
FIM
```

#### Teste de mesa

| a  | b  | aux | a  | b  | saída 1 | saída 2 | 
| -- | -- | --  | -- | -- | --      | --      | 
| 0  | 1  | 0   | 1  | 0  | a = 1   | b = 0   |

### Questão 2 - Contagem (1 ponto)

Dado um conjunto $n$ de notas de alunos em um exame, implemente e teste um algoritmo para fazer uma contagem $cont$ do número de alunos que foram aprovados no exame. 
Será considerado aprovado o aluno que tirar $nota$ 50 ou maior (no intervalo de 0 a 100).

#### Descrição geral do algoritmo

1. Obter o número de notas $n$ a serem processadas;
2. Inicializar a contagem $cont$ com zero;
3. Enquanto houver notas a serem processadas, fazer repetidamente:
    - obter a próxima nota;
    - se a nota for suficiente para passar no exame ($n ≥ 50$) então adicionar 1 (um) à contagem $cont$;
4. Exibir a contagem $cont$ (número total de aprovações).

#### Fluxograma 01
Fluxograma conforme descrição do algoritmo acima, usando o loop ENQUANTO.

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o número de alunos: }}
B --> C[\n\]
C --> D[\cont = 0\]
D --> E[\i = 1\]
E --> F{i <= n}
F --FALSE--> W{{Número de alunos aprovados: cont}}
W --> Z([FIM])
F --TRUE--> G{{Digite a nota do aluno, i}}
G --> H[\nota\]
H --> I{"nota >= 50 <br>E <br>nota <=100"}
I --TRUE--> J[\cont =+ 1\]
I --FALSE--> K[\i =+ 1\]
J --> K
K --LOOP--> F
```

#### Fluxograma 02
Fluxograma opcional usando o loop PARA.

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o número de notas: }}
B --> C[\n\]
C --> D[\cont = 0\]
D --> E[[i=1 ATE n PASSO 1]]
E --"i=1,2...,n"--> F{{Digite nota, i}}
E --"i > n"--> K{{Número de alunos aprovados: , cont}}
K --> L([FIM])
F --> G[\nota\]
G --> H{"nota >= 50 <br>E <br>nota <=100"}
H --FALSE/LOOP--> E
H --TRUE--> J[\cont =+ 1\]
J --LOOP--> E
```

#### Pseudocódigo 01 (1 ponto)

```
Algoritmo ContaAprovacoes
1  ALGORITMO ContarAprovados         
2  DECLARE n, nota, cont, i: INTEIRO
3  INICIO
4    ESCREVA “Digite o número de alunos: “         //Solicitar ao usuario o numero total de alunos
5    LEIA n         //Armazenar no sistema o numero de alunos na variavel "n"
6    cont ← 0         //Atribuir o valor 0 para a variavel "cont"
7    i ← 1         //Atribuir o valor 1 para a variavel "i"
8    ENQUANTO i <= n FAÇA         //Tomar uma decisão dependende da variavel "i" e assim criar um loop
9      ESCREVA “Digite a nota do aluno “, i, “: “         //Perguntar ao usuario qual a nota do aluno de acordo com "i"
10     LEIA nota         //Armazenar a nota no sistema como um variavel 
11     SE nota >= 50 E nota <= 100 ENTÃO         //Tomar um decisão apartir do valor da nota
12       cont ← cont + 1         //Atribuir +1 na variavel "cont" para que seja gerado um novo valor de "cont" e assim gerar novamente o loop
13     FIM_SE
14     i ← i + 1             //Atribuir +1 na variavel "i" para que possa dar continuidade na contagem das notas e dos alunos
15   FIM_ENQUANTO
16   ESCREVA “Número de alunos aprovados: “, cont         //Falar para o usuario a quantidade de alunos aprovados 
17 FIM_ALGORITMO
18 FIM
```

#### Teste de mesa 01
Teste de mesa referente ao algoritmo usando o loop ENQUANTO.

| it | n  | i  | cont | i<=n  | nota, i | nota | nota_valida | cont+1 | i+1 | saída        | 
| -- | -- | -- | --   | --    | --      | --   | --          | --     | --  | --           |
| 1  | 3  | 1  |  0   | True  | nota 1  | 60   | True        | 1      | 2   | Aprovados: 1 |
| 2  | 3  | 2  |  1   | True  | nota 2  | 40   | False       | 1      | 3   | Aprovados: 0 |
| 3  | 3  | 3  |  1   | True  | nota 3  | 90   | True        | 2      | 4   | Aprovados: 1 |
| 4  | 3  | 4  |  2   | False | nota 4  | 50   | True        | 3      | 5   | Aprovados: 2 |

#### Teste de mesa 02
Teste de mesa referente ao algoritmo usando o loop PARA.

| it | n  | cont | i  | nota, i | nota | nota_valida | cont+1 | saída        | 
| -- | -- | --   | -- | --      | --   | --          | --     | --           |
| 1  | 3  | 0    | 1  | nota 1  | 60   | True        | 1      | Aprovados: 1 |
| 2  | 3  | 1    | 2  | nota 2  | 40   | False       | 1      | Aprovados: 0 |
| 3  | 3  | 1    | 3  | nota 3  | 90   | True        | 2      | Aprovados: 2 |

### Questão 3 - Soma de um conjunto de números (1 ponto)

Dado um conjunto de $n$ números, implemente e teste um algoritmo para calcular a soma desses números. <br>
Aceite apenas $n$ maior ou igual a zero.

#### Descrição geral do algoritmo

1. Obter a quantidade de números $n$ a serem somados.
2. Inicializar a variável $soma$ com 0 (zero).
3. Enquanto menos do que $n$ números tiverem sido somados, fazer repetidamente:
    - obter o próximo número $i$;
    - calcular a soma atual, adicionando o número $i$ obtido à soma mais recente;
4. Exibir a soma dos $n$ números

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite a quantidade de números<br> (n >= 0):"}}
B --> C[\n\]
C --> D{n >= 0}
D --FALSE-->N{{"O valor deve ser maior ou igual a zero!"}}
N --> M([FIM])
D --TRUE--> E[/soma = 0/]
E --> F[i = 1]
F --> G{i <= n}
G --FALSE--> L{{"A soma dos numeros é , soma"}}
L --> M
G --TRUE--> H{{Digite um número: }}
H --> I[\num\]
I --> J[soma =+ num]
J --> K[i =+ 1]
K --LOOP--> G
```

#### Pseudocódigo (1 ponto)

```
Algoritmo SomaNumeros
1 DECLARE n, soma, i, num: INTEIRO
2 INICIO
3   ESCREVA “Digite a quantidade de números (n >= 0): “         //Solicitar ao usuario a quantidade de termos que vai ser utilizada
4   LEIA n         //Armazenar no sistema a quantidade como variavel "n"
5   SE n < 0 ENTÃO         //Tomar um decisão apartir da variavel, e vericar se ela é positiva
6     ESCREVA “O valor deve ser maior ou igual a zero!”          //Caso a quantidade de termos for negativa, ira falar para o usuario que o valor tem que ser maior ou igual a zero 
7   SENÃO
8     soma ← 0         //Atribuir o valor 0 para a variavel "soma"
9     i ← 1         //Atribuir o valor 1 para a variavel "i" 
10    ENQUANTO i <= n FAÇA         //Tomar uma decisão em relação a variavel "n" e inciar o loop caso precise
11      ESCREVA “Digite um número: “         //Perguntar o usuario um numero 
12      LEIA num         //Armezenar no sistema a variavel "num"
13      soma ← soma + num         //Atribuiur "soma + num" a variavel "soma", para que possa existir um novo valor da soma total e poder gerar um loop 
14      i ← i + 1         //atribuir o novo valor de i apartir da quantidade de vezes que for utilizado o "i"
15    FIM_ENQUANTO
16    ESCREVA “A soma dos números é “, soma         //Digitar ao usuario qual a soma total dos numero de acorodo com a variavel "soma"
17   FIM_SE
18 FIM_ALGORITMO
19 FIM
```

#### Teste de mesa

| it | n  | n >= 0 | soma | i  | i <= n | num | soma =+ num  | saída                   |
| -- | -- | --     | --   | -- | --     | --  | --           | --                      |
|    | -3 | False  |      |    |        |     |              | O valor deve ser ...    |
| 1  | 0  | True   | 0    | 1  | False  |     |              | A soma dos números é 0  |
| 1  | 3  | True   | 0    | 1  | True   | 5   | 0 + 5 = 5    | A soma dos números é 0  |
| 2  | 3  | True   | 5    | 2  | True   | 10  | 5 + 10 = 15  | A soma dos números é 5  |
| 3  | 3  | True   | 15   | 3  | True   | 20  | 15 + 20 = 35 | A soma dos números é 15 |
| 4  | 3  | True   | 35   | 4  | False  |  0  | 35 + 0 = 35  | A soma dos números é 35 |

### Questão 4 - Cálculo de uma série (1 ponto)

Dado um conjunto de $n$ termos da série, implemente e teste um algoritmo para calcular o valor de S, conforme definido abaixo:

$$ S = \frac{1}{2} + \frac{3}{4} + \frac{5}{6} + \frac{7}{8} + \dots $$

#### Descrição geral do algoritmo

1. Obter o número de termos $n$;
2. Inicializar a variável $S$ com 0 (zero).
3. Iterar o valor de $n$ na variável $i$ iniciando com 0 (zero), de acordo com as instruções abaixo:
    - calcular o numerador na variável $numerador$;
    - calcular o denominador  na variável $denominador$;;
    - calcular o termo da série na variável $termo$, onde $termo = numerador/denominador$;
    - adicionar esse termo à variável $S$.
4. Exibir o valor da série $S$.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite o número de termos da série S: }}
B --> C[/n/]
C --> D[S = 0]
D --> E[[i=0 ATE n PASSO 1]]
E --i > n--> J{{"Soma da série S é ", S}}
J --> K([FIM])
E --"i=0,1,2,..,n"--> F[numerador = 2 * i + 1]
F --> G[denominador = 2 * i + 2]
G --> H[termo = numerador / denominador]
H --> I[S += termo]
I --LOOP--> E
```

#### Pseudocódigo (1 ponto)

```
Algoritmo SomaSerie
1 DECLARE n, S, numerador, denominador, termo, i: INTEIRO
2 INICIO
3 ESCREVA “Digite o número de termos da série S: “          //Solicitar ao usuario a quantidade de termos que se vai utilizar
4 LEIA n         //Armazenar no sistema a variavel como "n"
5 S ← 0         //Atribuir o valor 0 para a variavel "S"
6   PARA i DE 0 ATÉ n PASSO 1 FAÇA         //Determinar o passo q vai ser utilizado e iniciar um loop 
7     numerador ← (2 * i) + 1         //Atribuir "(2 * i) + 1 " a variavel "numerador" para que 
8     denominador ←(2 * i)+ 2         //Atribuir "(2 * i) + 2" a variavel "denominador"
9     termo ← numerador / denominador         //Atribuir duas variaveis em uma so, como se fosse uma divisão 
10    S ← S + termo         //Atribuir a variavel "S" e a variavel "termo" em uma nova variavel "S" para que possa acontecer o loop 
11  FIM_PARA 
12 ESCREVA “Soma da série S é “, S         //Digitar ao usuario que a soma total é igual a variavel "S"
13 FIM_ALGORITMO
14 FIM
```

#### Teste de mesa (0.25 ponto)

| it | n  | S  | i | numerador | denominador | termo | S += termo     | saída                  |
| -- | -- | -- |-- | --        | --          | --    | --             | --                     |
|    | 0  | 0  |   |           |             |       |                |                        |
| 1  | 4  | 0  | 0 | 2*0+1 = 1 | 2*0+2 = 2   | 1/2   | 0+1/2 = 1/2    | Soma da série S é 1/2  |
| 2  | 4  | 0  | 1 | 2*1+1 = 1 | 2*1+2 = 2   | 3/4   | 1/2+3/4 = 1.25 | Soma da série S é 1.25 |
| 3  | 4  | 0  | 2 | 2*2+1 = 1 | 2*2+2 = 2   | 5/6   | 0+1/2 = 2.08   | Soma da série S é 2.08 |
| 4  | 4  | 0  | 3 | 2*3+1 = 1 | 2*3+2 = 2   | 7/8   | 0+1/2 = 2.96   | Soma da série S é 2.96 |

### Questão 5 - Cálculo fatorial (2 pontos)

Dado um número $n$, implemente e teste um algoritmo para calcular o fatorial de $n$ (escrito como $n!$), onde $n ≥ 0$.

#### Descrição geral do algoritmo

1. Obter o número $n$, onde $n \geq 0$;
2. Inicializar a variável $fator$ com 1 (um) para armazenar o resultado do cálculo do fatorial;
3. Iterar o valor de $n$ na variável $i$, ou seja, executar $n$ vezes, as instruções abaixo:
    - Incrementar o valor atual $fator$ multiplicando pelo valor de $i$;
4. Exibir o resultado ($n!$).

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{"Digite um numero inteiro nao-negativo:"}}
B --> C[/n/]
C --> D{n >= 0}
D --TRUE--> E[fator = 1]
D --FALSE--> J{{O valor deve ser maior ou igual a zero!}}
J --> I([FIM])
E --> F[[i=1 ATÉ n PASSO 1]]
F --"i > n"--> H{{O fatorial de, n, é:, fator}}
F --"i=1,2,..n"--> G[fator = fator * i]
G --LOOP--> F
H --> I
```

#### Pseudocódigo (2 pontos)

```
Algoritmo CalcFatorial
1 DECLARE n, fator, i: INTEIRO
2 INICIO
3 ESCREVA “Digite um número inteiro não-negativo:”         //Solicitar ao usuario um numero inteiro não-negativo 
4 LEIA n         //Armazenar no sistema a variavel "n" como o numero inteiro não-negativo 
5   SE n >= 0 ENTÃO         //Decidir se o "n" é positivo 
6     fator ← 1         //Atribuir o valor 1 para a variavel "fator"
7     PARA i DE 1 ATÉ n PASSO 1 FAÇA            //Decida qual vai ser o passo e decidir ate "n"  
8       fator ← fator * i                //Atribuir o "fator * i" para a variavel "fator" para que seja criada uma nova variavel e possa ser gerado o loop
9     FIM_PARA
10  ESCREVA “O fatorial de “, n, “ é: “, fator              //Aqui voce vai expor para o usuario qual o fator de acordo com o "n" que ele escreveu no comeco da questão 
11  SENÃO
12    ESCREVA “O valor deve ser maior ou igual a zero!”         //Essa mensagem sera encaminhada para o usuario caso ele escreva um numero menor que 0
13  FIM_SE
14 FIM_ALGORITMO
FIM
```

#### Teste de mesa

| n  | fator | i  | fator = fator * i | saída               |
| -- | --    | -- | --                | --                  |
| 3  | 1     | 1  | 1*1 = 1           | O fatorial de 1 é 1 |
| 3  | 1     | 2  | 1*2 = 2           | O fatorial de 2 é 2 |
| 3  | 2     | 3  | 2*3 = 6           | O fatorial de 3 é 6 |

### Questão 6 - Geração da sequência de Fibonacci (2 pontos)

Gerar e imprimir os $n$ primeiros termos da sequência de Fibonacci, onde $n ≥ 1$. <br>
Os primeiros termos são: $0, 1, 1, 2, 3, 5, 8, 13, \dots$. Cada termo, além dos dois primeiros, é derivado da soma dos seus dois antecessores mais próximos.

#### Descrição geral do algoritmo

1. Obter o número de termos $n$, onde $n \geq 1$;
2. Inicializar os dois primeiros termos da série nas variável $a$ e $b$ com 0 (zero);
3. Iterar o valor de $n$, ou seja, executar $n$ vezes, as instruções abaixo:
    - Imprimir o termo inicial $a$ (instrução para exibir a sequência ao atualizar a variável $a$);
    - Somar os termos $a$ e $b$ na variável $termo_atual$;
    - Atribuir a variável $a$ o valor da variável $b$;
    - Atribuir a variável $b$ o valor da variável $termo_atual$.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{"Número de termos da série Fibonacci:"}}
B --> C[a = 0]
C --> D[b = 1]
D --> E[[i=1 ATÉ n PASSO 1]]
E --"i > n"--> J([FIM])
E --"i=1,2,...,n"--> F{{a}}
F --> G[termo_atual = a + b]
G --> H[a = b]
H --> I[b = termo_atual]
I --LOOP--> E 
```

#### Pseudocódigo (2 pontos)

```
Algoritmo GeraFibonacci
1 DECLARE n, a, b, termo_atual, i: INTEIRO
2 INICIO
3   ESCREVA “Número de termos da série Fibonacci: “          //Solicitar ao usuario a quantidade de termos que ele quer utiizar
4   LEIA n          //Armazenar no sistema a quantidade de termos na variavel "n"
5   a ← 0          //Atribuir o valor 0 para a variavel "a"
6   b ← 1         //Atribuir o valor 1 para a variavel "b"
7   PARA i DE 1 ATÉ n PASSO 1 FAÇA             //Determinar o passo que vai ser utilizado 
8     ESCREVA a         //Utilizar a variavel "a"
9     termo_atual ← a + b         //Atribuir "a + b" a variavel "termo_atual", pois ira atualizar o termo e poder realizar a troca de numeros 
10    a ← b         //Atribuir "b" a "a" pra poder haver a troca de numeros
11    b ← termo_atual         //atriuir o "termo_atual" para "b" pra finalizar a troca dos termos 
12 FIM_PARA
13 ESCREVA “FIM”         //Sinalizar ao usuario o fim do algoritmo 
14 FIM_ALGORITMO
FIM
```
#### Teste de mesa

| it | n  | a  | b  | i  | saída | termo_atual = a + b | a = b | b = termo_atual |
| -- | -- | -- | -- | -- | --    | --                  | --    | --              |
| 1  | 5  | 0  | 1  | 1  | 0     | 0 + 1 = 1           | 1     | 1               |
| 2  | 5  | 1  | 1  | 2  | 1     | 1 + 1 = 2           | 1     | 2               |
| 3  | 5  | 1  | 2  | 3  | 1     | 1 + 2 = 3           | 2     | 3               |
| 4  | 5  | 2  | 3  | 4  | 2     | 2 + 3 = 5           | 3     | 5               |
| 4  | 5  | 3  | 5  | 5  | 3     | 3 + 5 = 8           | 5     | 8               |

### Questão 7 - Inversão dos dígitos de um número inteiro (2 pontos)

Implemente e teste um algoritmo para inverter a ordem dos dígitos de um número inteiro positivo.

#### Descrição geral do algoritmo

1. Obter o número inteiro positivo $num$ a ser invertido;
2. Inicializar a variável $num \textunderscore inv$ com 0 (zero);
3. Enquanto o número for maior que zero ($num > 0$), faça repetidamente:
    - Calcular o último dígito do número na variável $digito$;
    - Adicionar o dígito ao número invertido $num \textunderscore inv$;
    - Remover o último dígito do número original $num$; 
4. Exibir o número invertido.

#### Fluxograma

```mermaid
flowchart TD
A([INICIO]) --> B{{Digite um número inteiro: }}
B --> C[\num\]
C --> D{num >= 0}
D --TRUE--> G[num_inv = 0]
G --> H{num > 0}
H --FALSE--> Z{{"Número invertido:", numero_inv}}
Z --> W([FIM])
H --TRUE--> I[digito = num % 10]
I --> J[num_inv = num_inv * 10 + digito]
J --> K[numero = numero // 10]
K --LOOP--> H
D --FALSE--> E{{O número deve ser positivo!}}
E --> W
```

#### Pseudocódigo (2 pontos)

```
Algoritmo InverteInteiro
1 DECLARE num, num_inv, digito: INTEIRO
2 INICIO
3 ESCREVA “Digite um número inteiro: “         //Solicitar ao usuario o numero interio 
4 LEIA num         //Armazenar o numero inteiro dentro do sistema como variavel "num"
5   SE num >= 0 ENTÃO         //Decidir de o "num" é positvo 
6     num_inv ← 0         //Atribuir o valo 0 para a variaveel "num_inv" para poder a contagem da variavel estar zerada
7     SE num > 0 ENTÃO         //Decidir se o "num" é positivo e qual ação ira ter 
8       ENQUANTO num > 0 FAÇA         //Decidir o que vai ser feito caso o "num" seja positivo, iniciando aqui o loop 
9         digito ← num % 10         //Atribuir "num % 10" pra poder ter a divisao por inteiro do numero e descobrir qual o valor das dezenas 
10        num_inv ← num_inv * 10 + digito         //Atribuir o valor das unidades e invertero numero 
11        num ← num // 10         //Atribuir o "num//10" antigo para o novo "num" para que possa existir o loop 
12      FIM_ENQUANTO
13    SENÃO
14      ESCREVA “O número deve ser positivo!”         //Caso usuario não escreva um numero positivo essa vai ser a sua resposta 
15    FIM_SE
16    ESCREVA “Número invertido:”, num_inv         //Responder o usuario com o numero invertido e utilizando a variavel nova 
17  SENÃO
18    ESCREVA “O número deve ser não-negativo!”
19  FIM_SE
20 FIM_ALGORITMO
FIM
```

#### Teste de mesa

| it | num | num_inv | num > 0 | digito | num = num // 10 | num_inv = (num_inv * 10) + digito | Saída                       |
| -- | --  | --      | --     | --      | --              | --                                | --                          |
|    | -1  | 0       | False  |         |                 |                                   | O número deve ser positivo! |
| 1  | 0   | 0       | False  |         |                 |                                   | Número invertido:: 0        |
| 1  | 42  | 0       | True   | 2       | 4               | 2                                 |                             |
| 2  | 4   | 2       | True   | 4       | 0               | 24                                |                             |
| 3  | 0   | 24      | False  |         |                 |                                   | Número invertido:: 24       |
