# Variaveis e seus tipos

Quando se trata de linguagens de programação, é comum identificar o tipo de dado que uma variável receberá. No entanto, em Python, isso não é necessário. Por ser uma linguagem dinamicamente tipada — o que significa que não é necessário declarar o tipo de variável ou fazer *casting*, mudar o tipo de variável, pois o interpretador se encarrega disso — é fácil banalizar a importância de conhecer os tipos de variáveis.

Porém, compreender esse assunto é muito importante para quem desenvolve código. Isso porque, durante uma execução, o tipo da variável pode ser alterado e entender esse comportamento pode ser o diferencial para conseguir realizar a construção de um algoritmo.  

Durante esta seção será utilizado o método `type()` do Python. Com ele, é possível saber o tipo de uma variável ou de um dado com precisão.

## Tipos numéricos

Os tipos de dados usados para números se dividem em três conjuntos: inteiro, ponto flutuante e complexos. 


### Inteiro (`int`)

Esse tipo representa o conjunto dos números inteiros, ou seja, são os números positivos e negativos que não apresentam parte decimal. A seguir, será apresentado um algoritmo que insere um valor inteiro dentro de uma variável e exibe o seu tipo, que no caso é um `int`, veja:

```python
numero = 7
print(type(numero))
# output = <class 'int'>
```

> #### ⚠️ **Observação**: 
> Os números inteiros podem ser representados também nos formatos binário, hexadecimal e octal. Abaixo há exemplos dessas representações de forma respectiva:
> - 0b10000, 0b11111111 
> - 0x01, 0x10, 0xFF
> - 0o1, 0o20, 0o377 

### Ponto flutuante ou decimal (`float`) 

Representação de números reais, ou seja, os que contém casas decimais. A seguir, será apresentado um algoritmo que insere um valor decimal dentro de uma variável e exibe o seu tipo, que no caso é um `float`, veja:

```python
altura = 7.1
print(type(altura))
# output = <class 'float'>
```

### Complexo (`complex`)

Os números complexos são mais utilizados na engenharia e pesquisa. No Python, a parte imaginária do número recebe a letra `j`  — podendo ser maiúscula ou minúscula. A seguir, será apresentado um algoritmo que insere um numero complexo dentro de uma variável e exibe o seu tipo, que no caso é um `complex`, veja:

```python
complexo = 7j
print(type(complexo))
# output = <class 'complex'>
```

## *String* (`str`)

Trata-se de um conjunto de caracteres dispostos numa determinada ordem, geralmente utilizada para representar palavras, frases ou textos. No Python, para indicar que o código escrito é uma string, é preciso colocar aspas simples (`'`) ou aspas duplas (`"`) tanto no inicio, quanto no fim da cadeia de caracteres. A seguir, será apresentado um algoritmo que insere uma *string* dentro de uma variável e exibe o seu tipo, que no caso é um `str`, veja:

```python
texto = 'Olá mundo!'
print(type(texto))
# output = <class 'str'>
```

## *Boolean* (`bool`)

É um tipo de dado lógico que pode assumir apenas dois valores: falso ou verdadeiro — `False` ou `True` em Python. A seguir, será apresentado um algoritmo que insere um *boolean* dentro de uma variável e exibe o seu tipo, que no caso é um `bool`, veja:

```python
mentira = True
print(type(mentira))
# output = <class 'bool'>
```

Na lógica computacional, considera-se o `False` como 0 e o `True` como 1. Por isso, no Python, um *boolean* é  um subtipo inteiro onde 1 é equivalente a `True` e 0 equivale a `False`. 