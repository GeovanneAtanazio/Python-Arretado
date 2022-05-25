# Estrutura de Dados Básicas

Estruturas de dados resolvem um tipo de problema e podem ser úteis em diversas situações, no Python nós iremos ter algumas implementações delas. As principais estruturas são as Listas, Tuplas, Sets e Dicionários e nesta seção veremos as principais características de cada uma.

## Listas
No Python, uma lista é um tipo de dado que armazena uma sequência de diferentes tipos de dados, seus valores são definidos separados por vírgula, **(,)**, e podem ser mutáveis, ou sejam, uma vez definidas seus valores podem ser alterados. Seus valores são acessados através de um index que é representado por um  valor inteiro iniciando de 0.

```python
lista1 = [1,2,3,4,5]
lista2 = ["P","Y","T","H","O","N"]
lista3 = ["PY", 2022]

```

Podemos construir listas a partir de strings, tuplas, sets e dicionários a partir da função `list()`.

```python
string = "python"
print(list(good_string))

## output: ['p','y','t','h','o','n']

```
### Métodos de listas:

Listas apresentam uma vasta quantidade de métodos, dentre ela destaco:

- append(): adiciona novos valores ao final da lista
- extend(): extende os valores de uma lista adicionando todos os valores de outro objeto iterável, por exemplo, lista A pode ser extendida com os valores uma lista B.
- count(): conta a quantidade de ocorrências de um dado item na lista.
- sort(): ordena a lista de forma crescente.
- reverse(): reverte as posições dos valores na lista, o primeiro valor se tornará o último e o último se tornará o primeiro.

```python
>>> fruits = ['orange', 'apple', 'pear', 'banana', 'kiwi', 'apple', 'banana']
>>> fruits.count('apple')
2
>>> fruits.count('tangerine')
0
>>> fruits.reverse()
>>> fruits
['banana', 'apple', 'kiwi', 'banana', 'pear', 'apple', 'orange']
>>> fruits.append('grape')
>>> fruits
['banana', 'apple', 'kiwi', 'banana', 'pear', 'apple', 'orange', 'grape']
>>> fruits.sort()
>>> fruits
['apple', 'apple', 'banana', 'banana', 'grape', 'kiwi', 'orange', 'pear']
>>> fruits.extend(["pineapple"])
['apple', 'apple', 'banana', 'banana', 'grape', 'kiwi', 'orange', 'pear', 'pineapple']

```

Existem outros métodos mais que são bastante interessantes, como atividade complementar recomendo essa [leitura](https://docs.python.org/3/tutorial/datastructures.html).

## Tuplas

As tuplas são estrutura de dados muito similar às Listas, são tipos de dados que armazenam múltiplos tipos de dados, separados por uma vírgula. Sua principal diferença é que tuplas representam objetos ordenados e imutáveis, ou seja, uma vez definidos seus valores não podem ser alterados.

```python
fruits = ('apple', 'mango', 'banana')
print(fruits)
# output: ('apple', 'mango', 'banana')

# or

fruits_2 = 'apple', 'mango', 'banana'
print(fruits_2)
# output: ('apple', 'mango', 'banana')

fruits_3 = ('pineapple',)
print(fruits_3)
# output: ('pineapple',)
```

As tuplas podem ser definidas com ou sem parentêsis. Para definir tuplas com valores únicos nós utilizando uma virgula após o valor da tupla, importante ressaltar que se não definirmos com a virgula após um valor única de uma tupla, o Python não irá considerar a variável como uma tupla.

```python
eh_tupla = ('apple')
print(type(eh_tupla)) # OUTPUT: <class ‘str’>

eh_tupla_2 = 'apple',
print(type(eh_tupla_2)) # OUTPUT: <class ‘tuple’>

nao_eh_tupla = ('apple',)
print(type(nao_eh_tupla)) # OUTPUT: <class ‘tuple’>
```

Por ser um tipo de dados imutável, não temos muitos métodos que interagem com a tupla como é o caso das listas, porém podemos acessar as tuplas através de `index` e calcular o tamanho da tupla com o método `len()`.

```python
fruits = ('apple', 'mango', 'banana')

print(len(fruits))
# output: 3

print(fruits[1])
# output: "mango"
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

Como podemos ver, existem duas formas de se definir Sets, eles podem ser definidos com o uso de chaves e virgulas ou passando um iteravel (lista, tupla, dicionario) para o método `set()`. Outra coisa também que podemos observar é que mesmo que passemos valores duplicado no momento de criação de um Set, este não ficará com o valor pois apenas aceita valores não duplicados.

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

Para remover valores de um Set existem algumas possibilidades diferentes que podem ser utilizadas de acordo com o cenário que você tenha no seu programa, vamos de exemplos:

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
dict_example = {'nome':'Maria', "idade":22}
print(dict_example)
# output = {'nome':'Maria', "idade":22}

empty_dict = {}
print(empty_dict)
# output = {}

fruits = {1 :'apple', 2 :'banana', 3 :'cherry'}
print(fruits)
# output = {1 :'apple', 2 :'banana', 3 :'cherry'}

mixed_dics = {1:'red','name':'Jose'}
print(mixed_dics)
# output = {1:'red','name':'Jose'}
```

Para acessar valores de dicionários nós utilizamos das suas chaves.

```python
dict_example = {'nome':'Maria', "idade":22}

print(dict_example["nome"]) # lança excessão se essa chave não existir
#  output = Maria

print(dict_example.get("nome")) # retorna None ou valor default caso não encontre a chave.
#  output = Maria

print(dict_example.get("inexistente")) # j
#  output = None

print(dict_example.get("inexistente", "Não tem valor")) # j
#  output = Não tem valor
```

Para atualizar um dicionário ou para adicionar novos valores nós podemos fazer a partir das chaves

```python
dict_example = {}
print(dict_example)
# output = {}

dict_example["nome"] = "Maria"
print(dict_example)
# output = {"nome" : "Maria"}

dict_example["idade"] = 22
print(dict_example)
# output = {'nome':'Maria', "idade":22}

dict_example["nome"] = "Jose"
print(dict_example)
# output = {'nome':'Jose', "idade":22}

dict_example["idade"] = "25"
print(dict_example)
# output = {'nome':'Jose', "idade":"25"}
```

E para deletar uma chave de um dicionário nós utilizamos a cláusula  `del`.

```python
my_dict={1: 'James', 2: 'Apple', 3: 'Jake', 4: 'Banana,Cherry,Kiwi'}
del my_dict[4]
print(my_dict)

# output = {1:'James', 2: 'Apple', 3: 'Jake'}
```