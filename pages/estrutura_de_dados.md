# Estrutura de Dados Básicas

Estrutura de dados fazem o agrupamento de dados e são uteis para resolver problemas em diversas situações, no Python nós iremos ter algumas implementações delas. As principais estruturas são as Listas, Tuplas, Sets e Dicionários e nesta seção veremos as principais características de cada uma.

## Listas
No Python, uma lista é um tipo de dado que armazena uma sequência de diferentes tipos de dados, seus valores são definidos separados por vírgula, **(,)**, e podem ser mutáveis, ou sejam, uma vez definidas seus valores podem ser alterados. Seus valores são acessados através de um índice que é representado por um  valor inteiro iniciando de 0.

```python
lista1 = [1,2,3,4,5]
lista2 = ["P","Y","T","H","O","N"]
lista3 = ["PY", 2022]

```

Podemos construir listas a partir de strings, tuplas, sets e dicionários a partir da função `list()`.

```python
string = "python"
print(list(string))

## output: ['p','y','t','h','o','n']

```
### Métodos de listas:

Listas apresentam uma vasta quantidade de métodos, dentre ela destaco:

- append(): adiciona novos valores ao final da lista

```python
>>> frutas = ['laranja', 'maçã', 'pera', 'banana', 'kiwi', 'maçã', 'banana']

>>> frutas.append('uva')
>>> frutas
['banana', 'maçã', 'kiwi', 'banana', 'pera', 'maçã', 'laranja', 'uva']
```
- extend(): extende os valores de uma lista adicionando todos os valores de outro objeto iterável, por exemplo, lista A pode ser extendida com os valores uma lista B.

```python
>>> frutas = ['laranja', 'maçã', 'pera', 'banana', 'kiwi', 'maçã', 'banana']

>>> frutas.extend(["abacaxi", "melão"])
['maçã', 'maçã', 'banana', 'banana', 'uva', 'kiwi', 'laranja', 'pera', 'abacaxi', "melão"]

```

- count(): conta a quantidade de ocorrências de um dado item na lista.
```python
>>> frutas = ['laranja', 'maçã', 'pera', 'banana', 'kiwi', 'maçã', 'banana']

>>> frutas.count('maçã')
2
>>> frutas.count('tangerine')
0

```

- sort(): ordena a lista de forma crescente.

```python
>>> frutas = ['laranja', 'maçã', 'pera', 'banana', 'kiwi', 'maçã', 'banana']

>>> frutas.sort()
>>> frutas
['maçã', 'maçã', 'banana', 'banana', 'uva', 'kiwi', 'laranja', 'pera']

```

- reverse(): reverte as posições dos valores na lista, o primeiro valor se tornará o último e o último se tornará o primeiro.

```python
>>> frutas = ['laranja', 'maçã', 'pera', 'banana', 'kiwi', 'maçã', 'banana']

>>> frutas.reverse()
>>> frutas
['banana', 'maçã', 'kiwi', 'banana', 'pera', 'maçã', 'laranja']
```

Existem outros métodos mais que são bastante interessantes, como atividade complementar recomendo essa [leitura](https://docs.python.org/3/tutorial/datastructures.html).

## Tuplas

As tuplas são estrutura de dados muito similar às Listas, são tipos de dados que armazenam múltiplos tipos de dados, separados por uma vírgula. Sua principal diferença é que tuplas representam objetos ordenados e imutáveis, ou seja, uma vez definidos seus valores não podem ser alterados.

```python
frutas = ('maçã', 'manga', 'banana')
print(frutas)
# output: ('maçã', 'manga', 'banana')

# ou

frutas_2 = 'maçã', 'manga', 'banana'
print(frutas_2)
# output: ('maçã', 'manga', 'banana')

frutas_3 = ('abacaxi',)
print(frutas_3)
# output: ('abacaxi',)
```

As tuplas podem ser definidas com ou sem parentêsis. Para definir tuplas com valores únicos nós utilizando uma virgula após o valor da tupla, importante ressaltar que se não definirmos com a virgula após um valor única de uma tupla, o Python não irá considerar a variável como uma tupla.

```python
eh_tupla = ('maçã')
print(type(eh_tupla)) # OUTPUT: <class ‘str’>

eh_tupla_2 = 'maçã',
print(type(eh_tupla_2)) # OUTPUT: <class ‘tuple’>

nao_eh_tupla = ('maçã',)
print(type(nao_eh_tupla)) # OUTPUT: <class ‘tuple’>
```

Por ser um tipo de dados imutável, não temos muitos métodos que interagem com a tupla como é o caso das listas, porém podemos acessar as tuplas através de `index` e calcular o tamanho da tupla com o método `len()`.

```python
frutas = ('maçã', 'manga', 'banana')

print(len(frutas))
# output: 3

print(frutas[1])
# output: "manga"
```

## Sets

Na matemática os Sets são os conjuntos de objetos distintos que forma um grupo, e é exatamente isso que o Sets representa no Python. Temos algumas definições que são básicas quanto aos conjuntos, eles precisam:

1. Não conter valores duplicados;
2. Não possui ordem nos seus elementos;
3. Os seus elementos são imutáveis porém o Set como um todo é mutável.

Vamos ver exemplos que demonstram essas características:

```python

conjunto = {0, 2, 4, 6}
print(conjunto)
# output = {0, 2, 4, 6}

conjunto_2 = {"zero", 2, "quatro", 6.0}
print(conjunto_2)
# output = {"zero", 2, "quatro", 6.0}

conjunto_3 = {0, 2, 2, 4 , 4}
print(conjunto_3)
# output = {0, 2, 4}

conjunto_4 = set([1, 1, 2, 3])
print(conjunto_4)
# output = {1, 2, 3}
```

Como podemos ver, existem duas formas de se definir Sets, eles podem ser definidos com o uso de chaves ({}) e virgulas (,) ou passando um iteravel (lista, tupla, dicionario) para o método `set()`. Outra coisa também que podemos observar é que mesmo que passemos valores duplicado no momento de criação de um Set, este não ficará com o valor pois apenas aceita valores não duplicados.

Para adicionar novos valores a um Set já definido podemos fazer da seguinte forma:

```python
conjunto = {0, 2, 4, 6}
print(conjunto)
# output = {0, 2, 4, 6}

conjunto.add(8) # adiciona um elemento por vez
print(conjunto)
# output = {0, 2, 4, 6, 8}

conjunto.update([10, 12]) # adiciona múltiplos elementos por vez
print(conjunto)
# output = {0, 2, 4, 6, 8, 10, 12}
```

Para remover valores de um Set existem algumas possibilidades diferentes que podem ser utilizadas de acordo com o cenário que você tenha no seu algoritmo, vamos de exemplos:

```python
conjunto = {0, 2, 4, 6}
conjunto.remove(6) # se não encontrar o elemento o código lançará um erro.
print(conjunto)
# output = {0, 2, 4}

conjunto.discard(4) # se não encontrar o elemento nada acontecerá ao Set.
print(conjunto)
# output = {0, 2}

conjunto.discard(4)
print(conjunto)
# output = {0, 2}

conjunto.clear() # remove todos os elementos de um Set.
print(conjunto)
# output = set()
```


## Dicionários

Você pode pensar nesse tipo de dado como exatamente um dicionário onde teremos uma chave e para cada chave teremos um valor. Os valores das chaves em um dicionário são sempre únicas, e elas também são **case-sensitive**, já os seus valores podem ou não serem únicos. As chaves são valores imutáveis em um dicionário, uma vez definidos só podem ser excluídos e nunca alterados, seus valores no entanto podem sofre modificações.

Vamos de exemplos sobre como criar o seu dicionário em Python:

```python
dict_exemplo = {'nome':'Maria', "idade":22}
print(dict_exemplo)
# output = {'nome':'Maria', "idade":22}

empty_dict = {}
print(empty_dict)
# output = {}

frutas = {1 :'maçã', 2 :'banana', 3 :'cereja'}
print(frutas)
# output = {1 :'maçã', 2 :'banana', 3 :'cereja'}

dicionarios_misto = {1:'vermleho','nome':'Jose'}
print(dicionarios_misto)
# output = {1:'vermleho','nome':'Jose'}
```

Para acessar valores de dicionários nós utilizamos das suas chaves.

```python
dict_exemplo = {'nome':'Maria', "idade":22}

print(dict_exemplo["nome"]) # lança excessão se essa chave não existir
#  output = Maria

print(dict_exemplo.get("nome")) # retorna None ou valor default caso não encontre a chave.
#  output = Maria

print(dict_exemplo.get("inexistente")) # j
#  output = None

print(dict_exemplo.get("inexistente", "Não tem valor")) # j
#  output = Não tem valor
```

Para atualizar um dicionário ou para adicionar novos valores nós podemos fazer a partir das chaves

```python
dict_exemplo = {}
print(dict_exemplo)
# output = {}

dict_exemplo["nome"] = "Maria"
print(dict_exemplo)
# output = {"nome" : "Maria"}

dict_exemplo["idade"] = 22
print(dict_exemplo)
# output = {'nome':'Maria', "idade":22}

dict_exemplo["nome"] = "Jose"
print(dict_exemplo)
# output = {'nome':'Jose', "idade":22}

dict_exemplo["idade"] = "25"
print(dict_exemplo)
# output = {'nome':'Jose', "idade":"25"}
```

E para deletar uma chave de um dicionário nós utilizamos a cláusula  `del`.

```python
meu_dicionario={1: 'Jose', 2: 'Maçã', 3: 'Maria', 4: 'Banana,Cereja,Kiwi'}
del meu_dicionario[4]
print(meu_dicionario)

# output = {1:'Jose', 2: 'Maçã', 3: 'Maria'}
```