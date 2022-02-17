# 01_EstruturaSequencialPython

uma estrutura sequencial é uma estrutura de desvio do fluxo de controle presente em linguagens de programação que realiza um conjunto predeterminado de comandos de forma sequencial, de cima para baixo, na ordem em que foram declarados. 

Até aqui, trabalhamos com variáveis simples, capazes de armazenar apenas um tipo, como bool, float e int.

Nessa aula introduziremos o conceito de lista (= tipo list), uma estrutura sequencial indexada muito utilizada e uma das principais estruturas básicas do Python.

Uma lista (= list) em Python é uma sequência ou coleção ordenada de valores de qualquer tipo ou classe tais como int, float, bool, str e mesmo list, entre outros.

Diariamente utilizamos listas para organizar informação, como a lista de coisas a fazer, lista de compras, lista de filmes em cartaz etc.

Existem várias maneiras de criarmos uma lista. A maneira mais simples é envolver os elementos da lista por colchetes ( [ e ]). Podemos criar a lista contendo os 5 primeiros primos da seguinte maneira:

>>> primos = [2, 3, 5, 7, 11]

Podemos criar uma lista de vários objetos de tipos distintos:

>>> uma_lista = [11, "oi", 5.4, True]
>>> outra_lista = ["joão", "masculino", 15, 1.78, "brasileira", "solteiro"]
>>> fernanda = ["Fernanda", "Montenegro", 1929, "Central do Brasil", 1998, "Atriz", "Rio de Janeiro, RJ"]

Observe o uso de colchetes ([, ]) para marcar o início e o final da lista, e os elementos separados por vígula.

Uma lista pode ser criada vazia, da seguinte forma:

>>> lista_vazia = []

Comprimento de uma lista

A função len() retorna o comprimento (= o número de elementos ou objetos) de uma lista:

>>> len(primos)
5
>>> len(uma_lista)
4
>>> len(outra_lista)
6
>>> len(fernanda)
7
>>> len(lista_vazia)
0

Índices

Cada valor na lista é identificado por um índice.

Dizemos que uma lista é uma estrutura sequencial indexada pois os seus elementos podem ser acessados sequencialmente utilizando índices. O primeiro elemento da lista tem índice 0, o segundo tem índice 1, e assim por diante. Observe que, por começar pelo índice zero, o último elemento da lista primos, o número 11, tem índice 4, sendo que essa lista tem comprimento 5.

Para acessar um elemento de uma lista usamos o operador de indexação []. A expressão dentro dos colchetes especifica o índice. O índice do primeiro elemento é 0. O seguinte programa imprime os valores da lista primos:

1

primos = [2, 3, 5, 7, 11]

2

i = 0

3

while i < len(primos):

4

    print( "elemento de indice %d = %d"%(i, primos[i]) )

5

    i = i + 1

6

​

ActiveCode (exemplo_percorrer_lista_com_while)

Simule a execução desse programa e observe que a variável i recebe o valor zero que corresponde ao primeiro índice e, enquanto o índice for menor que o comprimento da lista (= len(primos)), o elemento de índice i é impresso.

Índices negativos indicam elementos da direita para a esquerda ao invés de da esquerda para a direita.

1

numeros = [17, 123, 87, 34, 66, 8398, 44]

2

print("%3d: %d" %(2,numeros[2]))

3

print("%3d: %d" %(5,numeros[-5]))

4

print("%3d: %d" %(9-8,numeros[9-8]))

5

print("%3d: %d" %(-2,numeros[-2]))

6

print("%3d: %d" %(len(numeros)-1,numeros[len(numeros)-1]))

7

print("%3d: %d" %(-7,numeros[-7]))

8

​

ActiveCode (indices_negativos)

Um erro comum em programas é a utilização de índices inválidos (= list index out of range):

1

numeros = [17, 123, 87, 34, 66, 8398, 44]

2

print("%3d: %d" %(len(numeros),numeros[len(numeros)])) # índice inválido

3

​

ActiveCode (indice_invalido_0)

1

numeros = [17, 123, 87, 34, 66, 8398, 44]

2

print("3d: %d" %(-8,numeros[-8])) # índice inválido

3

​

ActiveCode (indice_invalido_1)

1

lista_vazia = []

2

lista_vazia[0] = 10   # índice inválido

3

​

ActiveCode (indice_invalido_2)
Concatenação e Repetição

Nota sobre eficiência computacional

Por ser um curso introdutório, utilizaremos nesse curso apenas as operações de concatenação e fatiamento de listas. Nosso objetivo é empoderar os alunos para que eles possam entender, aprender e usar essas estruturas rapidamente em seus programas, independente da eficácia computacional dessas soluções, permitindo que o aluno mantenha foco no problema e não na linguagem. O custo computacional dessas soluções será abordado em cursos mais avançados.

Duas listas podem ser concatenadas utilizando o operador +.

1

um = [10, 11, 12]

2

dois = [20, 21]

3

​

4

tres = um + dois

5

print(tres)

6

​

ActiveCode (concatenacao_1)

Nesse exemplo, a concatenação da lista um com a lista dois cria uma nova lista formada por cópias dos elementos da lista um e dois.

Uma lista vazia é o elemento neutro da concatenação de listas:

1

um = [10, 11, 12]

2

dois = [20, 21]

3

​

4

tres = um + [] + dois + []

5

print(tres)

6

​

ActiveCode (concatenacao_1b)

O exemplo abaixo, concatena a lista um três vezes:

1

um = [10, 11, 12]

2

​

3

tres = um + um + um

4

print(tres)

5

​

ActiveCode (concatenacao_2)

Para concatenar uma lista repetidas vezes, podemos utilizar o operador * para multiplicar uma lista por um inteiro:

1

um = [10, 11, 12]

2

​

3

print("um + um + um", um + um + um)

4

print("3 * um", 3 * um)

5

print("um * 3", um * 3)

6

print("[] * 3", [] * 3)

7

​

ActiveCode (repeticao_1)

Observe que, assim como o * em operações aritméticas, o operador de repetição * de listas também é comutativo, assim como a repetição de listas vazias resulta em uma lista vazia.

O operador de repetição * é bastante útil para criar uma lista de comprimento N com valor inicial determinado como:

1

# cria lista de tamanho n com zeros

2

n = int(input("Digite o tamanho da lista: "))

3

lista = [0] * n

4

print(lista)

5

​

ActiveCode (repeticao_2)
Fatias de um lista

Muitas vezes, ao invés de considerar a lista completa, é necessário consider apenas um pedaço contínuo da lista, que podemos definir por 2 índices que marcam o início e o fim desse pedaço, que chamamos de fatia da lista.

Em Python, uma fatia de uma lista é definida colando o ínicio e o fim entre colchetes, separados por :, como:

>>> primos = [2, 3, 5, 7, 11]
>>> primos[1:2]
[3]
>>> primos[2:4]
[5, 7]
>>> primos[:3] # observe que o início não precisa ser definido
[2, 3, 5]
>>> primos[3:] # observe que o fim não precisa definido
[7, 11]
>>> primos[:]
[2, 3, 5, 7, 11]

Observe que o intervalo é sempre fechado à esquerda (inclui o primeiro elemento na fatia) e aberto à direita (não inclui o último elemento). A operação de fatiamento devolve uma cópia do pedaço da lista definido pelo intervalo.
Referência versus cópia

Quando uma lista é atribuída a uma variável, dizemos que a variável passa a fazer uma referência a lista. Assim, várias variáveis com nomes distintos podem fazer referência a mesma lista.
1	lista_1 = ["oi", 2, 3.14, True]
2	lista_2 = lista_1
3	lista_2[2] = 5
4	
5	print(lista_1)  # observe que o elemento lista_1[2] TAMBÉM foi modificado
line that just executed

next line to execute
Step 1 of 4
Python Tutor by Philip Guo
Customize visualization (NEW!)
	
Print output (drag lower right corner to resize)
Frames
	
Objects

CodeLens: (clonar_uma_lista_0)

Nesse exemplo, para que possamos trabalhar com a lista_2 sem alterar os elementos da lista_1, precisamos copiar a lista_1.

A forma mais comum para copiar uma lista é criando uma fatia da lista inteira como:

lista_1 = ["oi", 2, 3.14, True]
lista_2 = lista_1[:]   # cria uma cópia da lista_1
lista_2[2] = 5

print(lista_1)  # observe que o elemento lista_1[2] NÃO foi modificado

Comando for

Vários problemas envolvendo listas requerem percorrer (varrer) todos os elementos da lista, um a um, do início até o fim. Nesses casos, podemos utilizar o comando for:
1	primos = [2, 3, 5, 7, 11, 13]
2	print("Varredura usando for: ")
3	for elemento in primos:
4	    print("Valor da variável elemento: ", elemento)
5	print("Fim da varredura com for")
6	
7	print()
8	print("Varredura usando while: ")
9	i = 0
10	while i < len(primos):
11	    print("Valor na posição %d da lista: %d"%(i, primo[i]))
12	    i += 1
line that just executed

next line to execute
Step 1 of 21
Python Tutor by Philip Guo
Customize visualization (NEW!)
	
Print output (drag lower right corner to resize)
Frames
	
Objects

CodeLens: (exemplo_percorrer_lista_com_for_elem)

Para usar o comando for, você precisa definir uma variável que vai receber o valor de um elemento da lista a cada iteração. Nesse exemplo, a variável elemento recebe o valor de cada elemento da lista primos, ou seja, primeiro o valor 2, depois 3, 5, e assim por diante, até 13. A repetição termina quando o último elemento da lista primos for utilizado.

Observe também que a varredura da lista pode ser feita usando o comando while. A sequência de índices válidos é gerada variando a variável i de 0 até len(primos).

Muitas vezes é mais conveniente varrer uma lista usando uma variável que assume valores dentro do intervalo dos índices válidos. Com isso, temos mais poder e flexibilidade no acesso aos elementos da lista, como por exemplo, varrer a lista da direita para a esquerda, ou pegar apenas os elementos de índice par.

Nesses casos também, quando queremos ter controle sobre os índices, é muito comum utilizar o comando for em conjunto com a função range(). Basicamente, devemos chamar a função range() para que ela “devolva uma lista” contendo os valores dos índices que queremos utilizar.

A função range() recebe 3 parâmetros: início, fim e passo, que definem a sequência de números a ser criada. Modifique o trecho de programa abaixo para ver como a função range se comporta em conjunto com o for:

1

inicio = 10

2

fim    = 20

3

passo  = 3

4

for i in range(inicio, fim, passo):

5

    print( i )

6

​

ActiveCode (funcao_range_com_for)

Observe que, como na definição de intervalos em fatias de lista, o intervalo de números cobertos pela função range() é fechado no início e aberto no fim.

Quando o passo desejado é 1 (um), o valor não precisa ser passado a função range(), como abaixo:

1

inicio = 5

2

fim    = 11

3

for i in range(inicio, fim):

4

    print( i )

5

​

ActiveCode (funcao_range_com_passo_1)

Para facilitar mais ainda a varredura de listas, quando o início desejado é 0 (zero) e o passo 1 (um), você pode definir apenas o fim, como:

1

primos = [2, 3, 5, 7, 11, 13]

2

for i in range(len(primos)):

3

    print( "%d: %d"%(i,primos[i]) )

4



ActiveCode (exemplo_percorrer_lista_com_for_range)

Nesse exemplo, usando a função len() o final do intervalo a ser gerado pela função range(). Para saber mais sobre essa função, consulte a documentação da função range().

Para verificar se você entendeu como funciona a função range(), modifique o inicio, fim e passo no trecho de programa abaixo para varrer a lista de forma reversa, ou seja, da direita para a esquerda.

1

primos = [2, 3, 5, 7, 11, 13]

2

# modifique os valores abaixo

3

inicio = 0

4

fim    = len(primos)

5

passo  = 1

6



7

for i in range(inicio, fim, passo):

8

    print( "%d: %d"%(i,primos[i]) )

9



ActiveCode (exemplo_percorrer_lista_reversa)
Exercícios com listas
Exercício 1

(exercício 1 da lista de exercícios sobre vetores).

Dados n > 0 e uma sequência com n números reais, imprimí-los na ordem inversa a da leitura.

1

def main():

2

    # escreva o seu programa abaixo e remova o print()

3

    print("Vixe! Ainda nao fiz o exercicio!")

4



5

main()

6



ActiveCode (aula_lista_ex1_tentativa)

Clique aqui para ver uma solução.
Exercício 2

Dada uma sequência de n > 0 números reais, imprimi-los eliminando as repetições.

1

def main():

2

    # escreva o seu programa abaixo e remova o print()

3

    print("Vixe! Ainda nao fiz o exercicio!")

4



5

main()

6



ActiveCode (aula_lista_ex2_tentativa)
Exercício 3

Dados dois números naturais m e n e duas sequências ordenadas com m e n números inteiros, obter uma única sequência ordenada contendo todos os elementos das sequências originais sem repetição.

Sugestão: Imagine uma situação real, por exemplo, dois fichários de uma biblioteca.

1

def main():

2

    # escreva o seu programa abaixo e remova o print()

3

    print("Vixe! Ainda nao fiz o exercicio!")

4



5

main()

6



ActiveCode (aula_lista_ex3_tentativa)
Exercício 4

Dados um número inteiro n e uma sequência com n números reais, determinar a maior soma de um segmento da sequência (com pelo menos um elemento). Um segmento é uma subsequência de números consecutivos.

Para n == 12 e a sequência

5   -2   -2   -7   3   14  10  -3   9   -6   4   1

a soma do segmento de soma máxima é 3+14+10-3+9 = 33.

1

def main():

2

    # escreva o seu programa abaixo e remova o print()

3

    print("Vixe! Ainda nao fiz o exercicio!")

By: Debora S Simão
