# Controle de fluxos: Condicionais e Loops

Podemos dizer que todo programa Python consistirá em um conjunto de definições de operações que devem ser executadas pelo programa. Por exemplo, podemos ter um programa cujo o intuito é de realizar a soma de dois valores, desse modo nosso programa estará definindo uma operação de adição do número A e do número B. Um programa pode ser composto pode diversos tipos de definição de operações, com número, palavras e etc. Mas da forma como estamos fazendo até o momento não nos permite controlar ou definir nenhum fluxo para a execução das nossas operações.

Vamos imaginar com um exemplo da vida real, quando encontramos com um amigo e vamos cumprimentá-lo nós falamos *Bom dia!* se estiver de dia, *Boa tarde!* se estiver de tarde e *Boa noite!* se estiver a noite. Ou seja, definimos qual a operação estamos realizando com base em uma condição externa a nossa operação, no caso do nosso exemplo definimos com base no horário do dia. Algo similar acontece com nossos programas, podemos construir diferentes fluxos com base em condições definidas no nosso código. Vamos entender mais sobre como podemos definir o controle de fluxos com Python.


## Condicionais

O tipo de fluxo condicional é composto pelo uso de um dos três tipos de termos da linguagem:

- ```python
    if (condição):
        (ação)
    ```

- ```python
    if (condição):
        (ação 1)
    else:
        (ação 2)
    ```

- ```python
    if (condição):
        (ação 1)
    elif (condição):
        (ação 2)
    else:
        (ação 3)
    ```


### If

O `if` é a estrutura mais simples de condição e representa um **se**. Vejamos o exemplo abaixo:

```python

turno = "tarde"

if turno == "manhã":
    print("Bom dia!")

if turno == "tarde":
    print("Boa Tarde!")

if turno == "noite":
    print("Boa noite!")

```

Temos no exemplo 3 definições de operação que verificam **SE** a variável `turno` tem um dos valores comparados. O programa então irá executar a primeira verificação da condicional e identificar se a variável possui o valor `"manhã"` e essa verificação irá retornar o valor `False` pois a variável `turno` não possui o valor `"manhã"` e por isso não irá executar o trecho de código `print("Bom dia!")`. A seguir o programa irá verificar se a variável `turno` é igual ao valor `"tarde"` e essa operação irá retornar True, com isso o programa irá entrar nesse novo fluxo marcado pela condicional e imprimir na console o resultado da operação `print("Boa Tarde!")`. Por fim, o programa irá verificar se a variável `turno` é igual ao valor `"noite"` e essa verificação irá retornar False, encerrando o programa.

Então como podemos observar, o programa executa todas as verificações de condicional e executa somente aqueles que se enquadram no que a expressão de condicional está informando. Enquanto isso pode ser útil em alguns casos, no caso do nosso exemplo não é, pois se identificamos que o turno já equivale a tarde não faz sentido verificar se o turno também é noite. Por isso podemos ter outras estruturas de condicional.


### If Else

Podemos reformular nosso exemplo para dizer `Boa tarde!` toda vez que for tarde e quando for outro turno o programa deverá dizer outro tipo de cumprimento. Na estrutura If Else nós teremos a relação Se- Senão, onde se a condição não for satisfeita a segunda ação sempre será executada, mas se a condição for verdadeira essa ação será a única a ser executada.

```python

turno = "tarde"

if turno == "tarde":
    print("Boa Tarde!")
else:
    print("Olá!")
```

Dessa forma, o programa irá verificar se o turno é igual a `tarde` e se não for ele irá executar o `Olá!`. Mas podemos ver que esse código não está completo com o cenário que tínhamos previamente, então podemos reformular ele de uma forma diferente utilizando a estrutura If-Else.


```python

turno = "tarde"

if turno == "manhã":
    print("Bom dia!")
else:
    if turno == "tarde":
        print("Boa Tarde!")
    else:
        print("Boa noite!")

```

Nesse novo formato nós teremos uma estrutura condicional mais aninhada, onde o else somente será executado se a condicional do primeiro if `turno == "manhã"` for falsa, e dentro do else nós temos outro if-else. No nosso exemplo teremos a seguinte sequência de passos:

1. Verifica se o turno é igual a manhã e retorna falso, entrando na ação definida no else.
2. Dentro do else ele cai em uma nova condicional, onde a verificação de se turno é igual a tarde  o que retorna verdadeiro. Nesse ponto o programa irá imprimir no console `Boa Tarde!` e encerrar, como a condição do SE foi completada não é necessário executar a ação do SENÃO.

Ainda que agora nosso código funcione um pouco melhor, encerrando o programa quando a condição é verdadeiramente satisfeita, essa ainda não é a estrutura que melhor representa o nosso programa. Vamos seguir para o próximo exemplo.

### If Elif Else

Como podemos ter um cenário onde apenas queremos executar um tipo de cumprimento e ele é de acordo com o valor atribuído para variável `turno`, podemos reformular o programa para verificar três condicionais. Dessa forma, seria mais eficiente identificar se é manhã, tarde ou noite para saber qual o valor deve ser impresso no console. E supondo que o valor de turno seja por exemplo `"madrugada"`, um turno não mapeado no nosso fluxo, podemos retornar o valor padrão de "Olá!".

```python

turno = "tarde"

if turno == "manhã":
    print("Bom dia!")

elif turno == "tarde":
    print("Boa Tarde!")

elif turno == "noite":
    print("Boa noite!")

else:
    print("Olá!")

```

Com essa modificação podemos aproveitar o melhor do que o controle de fluxos do Python nos oferece, podemos misturar expressões e combinar a estrutura If Elif e Else para definir melhor o fluxo que o nosso programa deve seguir.


## Loops

No geral, loops representam estruturas que ficam executando repetidamente até uma condição ser completada. Dessa forma, loops são compostos pela sua inicialização, definição da condição e incrementação. Podemos combinar o uso de loops com as condicionais e assim montar fluxos que executam repetidas operações e seguem determinadas condições para a sua execução. Vamos observar os exemploes:

### For loops

A estrutura do For loop é composta pela definição `for (contador) in (incremendo): (ação)`, que representa algo do tipo "por X interações faça a ação".

```python
limite_iteracoes = 5

for iteracao in range(0, limite_iteracoes):
    print(iteracao)

# output:
# 0
# 1
# 2
# 3
# 4
```

Nesse exemplo, para fazer o incremento do valor da nossa iteração utilizamos a função range(inicio, fim) que realiza o somatório de unidade em unidade do valor inicial, no nosso caso 0, até o valor final, no nosso caso 5. Importanto ressaltar que o range não compreende o valor definido no final, se quisessemos incluir no nosso print o número 5 então devemos definir assim: `range(0, 6)`. Também podemos definir de quanto em quanto deve ser a iteração, por exemplo:

```python

for iteracao in range(0, 10, 3):
    print(iteracao)

# output:
# 0
# 3
# 6
# 9
```

No caso do exemplo queremos que seja impresso no console os valores que estejam no intervalo entre 0 e 10 começando de 0 e que seja acrescido de 3.

Também podemos combinar a execução do for loop com condicionais,  como podemos ver no exemplo abaixo.

```python

# Encontros de Segunda, Terça, Quarta, Quinta e sexta.
turnos_encontro = ["manhã", "noite", "manhã", "tarde", "madrugada"]
for iteracao in turnos_encontro:
    if turno == "manhã":
        print("Bom dia!")

    elif turno == "tarde":
        print("Boa Tarde!")

    elif turno == "noite":
        print("Boa noite!")

    else:
        print("Olá!")

# output:
# Bom dia!
# Boa noite!
# Bom dia!
# Boa Tarde!
# Olá!
```

### While loops

O conceito para o While loop é o mesmo do For mas a sua implementação é complementamente diferente. Nesse Loop nós teremos uma definição do tipo "enquanto condiçao faça", vamos dar uma olhada no exemplo.

```python

valor = 0
limite = 10
while valor < limite:
    print(valor)
    valor = valor + 2

## output
# 0
# 2
# 4
# 6
# 8
```

Na estrutura do While nós iremos ter a definição de uma condicional `valor < limite` para determinar enquanto o loop ainda deve acontecer e em qual condição o loop deve ter sua execução terminada. Aliado a condição também precisamos definir previamente um incremento que será utilizado pelo loop, no caso do exemplo `valor`, e esse incremento deve ser acrescido de alguma forma durante a ação.

A condição não precisa necessariamente ser numérica, podemos por exemplo ter apenas uma variável booleana, por exemplo:

```python
turnos_encontro = ["manhã", "noite", "madrugada", "manhã", "tarde"]
eh_madrugada = False
contador = 0
while not eh_madrugada:
    if turnos_encontro[contador] == "madrugada":
        eh_madrugada = True
    else:
        print("Olá!")
        contador += 1

## output
# Olá!
# Olá!
```

Nesse exemplo nós vamos executar a impressão de "Olá!" no console até que a variável eh_madrugada passe a ser verdadeira. Nesse exemplo vemos algumas coisas novas também, como por exemplo o uso de condicionais juntos com o While Loop, o acesso a valores de uma lista e uma nova forma de fazer soma com a mesma variável. Mas essa ainda não é a melhor forma de resolver esse problema, pois e se nunca tiver um encontro na madrugada teremos esse loop executando eternamente? Logo mais esse programa irá lançar um erro no console, vejamos no próximo tópico como podemos melhora-lo

## Break, Pass e Continue

Temos também algumas palavras que podemos incrementar os nossos loops, como por exemplo.

### Break

Podemos utilizar o Break para quebrar um loop de acordo com uma condicional.

```python
turnos_encontro = ["manhã", "noite", "madrugada", "manhã", "tarde"]
contador = 0
while contador < len(turnos_encontro):
    if turnos_encontro[contador] == "madrugada":
        break
    else:
        print("Olá!")
        contador += 1

## output
# Olá!
# Olá!

```

Reescrevendo o nosso programa para fazer um loop com o número de iterações iguais a quantidade de valores definidos na lista `turnos_encontro`. Observe que removemos a variável booleana `eh_madrugada` e substituímos a ação da condicional com uma cláusula **Break** que irá terminar a execução do loop quando a condição for satisfeita. Outra forma de corrigir esse códgo foi de limitar o número de execução, uma vez que os valores da nossa lista de encontros não é infinita.

## Continue

O continue é uma cláusula oposta ao break e quando aplicada sinaliza que o processamento deve continuar o loop pulando a iteração que caiu no caso do `continue`. Vamos olhar um exemplo:

```python

turnos_encontro = ["manhã", "noite", "madrugada", "manhã", "tarde"]
for turno in turnos_encontro:
    if turno == "madrugada":
        continue

    print("Olá!")

## output
# Olá!
# Olá!
# Olá!
# Olá!
```

### Pass

O Pass é uma cláusula que significa nenhuma execução, isso mesmo, ele significa que não queremos definir nenhuma ação em especifica, vamos ver sua estrutura:

```python

for item in range(0, 10, 2):
    if item % 3 == 0:
        print(item)
    else:
        pass

## output
# 0
# 6
```

Nesse exemplo nós utilizamos um for loop para iterar entre os múltiplos de 2 dentro do intervalo 0 e 10 e mandamos o programa imprimir somente aqueles que também são divisiveis por 3. Para todos os outros números simplesmente passamos, nenhuma ação era necessária, e é assim que utilizamos o Pass.
