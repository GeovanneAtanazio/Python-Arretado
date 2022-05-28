# Funções

Funções são blocos de códigos que executam um processamento em específico e retornam valores. São uma ótima forma de evitar duplicação de código e promover a reutilização de processamento em múltiplos lugares dos seus algoritmos.

As funções vão tornar o seu código mais legível, fácil de programar, de testar e manter. Um exemplo de uma função que já aprendemos e utilizamos bastante ao longo desse tutorial é a `print()`. No Python nós vamos ter funçÕes chamadas de *built-in*, que significam função que são definidas pela própria linguagem e por isso são disponibilizadas por padrão em qualquer lugar que você execute um código em Python. Você também vai poder definir suas próprias funções, o que chamaremos de funções *user-defined*.

## Definindo Funções

Para definir uma função é muito simples, todas as funções em Python iniciam com a nomeclatura `def` seguida por um nome para a função, parenteses e dois pontos (:).

```python
def dizer_ola():
    """ Imprime no console uma saudação. """
    print("Hello World!")

dizer_ola()
# output = Hello World!
    
```

Para definir os nomes das suas funções lembre-se das seguintes regras:

1. Evitar o uso de acentos
2. A letras devem estar minúsculas e as palavras devem estar separadas por underscores.

Além disso, opcionalmente as funções podem ou não retornar valores. Para retornar valores em uma função é utilizado a cláusula `return (expressão)`.

## Funções com Argumentos

Para invocar uma função basta definir o seu nome juntamente com os parenteses e argumentos, se necessário. Algumas função definem argumentos como necessidade para fazer a sua execução, como é o caso do exemplo `multiplicar(x, y)` que esperar receber dois argumentos para realizar a multiplicação.

```python

def multiplicar(x, y):
    """ Multiplica os valores x vezes y."""
    return x * y

resultado_multiplicacao = multiplicar(2, 3)
print(resultado_multiplicacao)
# output = 6

print(multiplicar(2, 3))
# output = 6

print(multiplicar(10, 2))
# output = 20

```


Algumas vezes as funções que recebem argumentos podem necessitar de valores padrões. Nesse caso é garantido que a função sempre terá um valor para o argumento da função. Por exemplo:

```python
def dizer_ola(nome="World"):
    """ Imprime no console uma saudação. """
    return f"Hello {nome}!"

print(dizer_ola())
# output = Hello World!

print(dizer_ola("Maria"))
# output = Hello Maria!

print(dizer_ola(nome="Jose")))
# output = Hello Jose!
```

Alternativamente, também podemos usar as variáveis mágicas `*args` e `**kwargs` na definição de funções. Essas variáveis permitem que no momento da chamada da função nós possamos passar um número variável de argumentos. Ou seja, quando não temos uma definição exata de quais serão os argumentos que estamos passando para uma função, esses atributos nos permite flexibilizar a definição das funções.

Enquato o `*args` significa argumentos que não são nomeados, ou seja, não acompanhem palavras chaves, os `**kwargs` seguem uma estrutura de múltiplos argumentos que seguem o padrão **chave=valor**.

```python
def soma(*args):
    total = 0
    for num in args:
        total += num 
    return total

print(soma(2,3,4,6)) # 15
print(soma(2,3,4,6,5,5,5,1,2)) # 32
print(soma(2,3)) # 5
```

```python

def paises(**kwargs):
    print(kwargs)
    for pais, sigla in kwargs.items():
        print(f"A sigla do País {pais} é {sigla}.")

paises(Brasil="BR", Portugal="PT")
# output:
# {"Brasil": "BR", "Portugal": "PT"}
# A sigla do País Brasil é BR. 
# A sigla do País Portugal é PT.
```