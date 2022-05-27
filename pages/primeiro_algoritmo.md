
# Primeiro algorítmo

Com o ambiente de desenvolvimento pronto já é possível começar a programar. Nessa seção será ensinado como fazer um algoritmo simples em Python utilizando as operações de entrada e saída de dados — conhecidas popularmente pela gíria I/O, que em inglês significa *Input/Output* ou, em português, Entrada/Saída. 

> #### ⚠️ **Observação**: 
> Para começar a escrever algoritmos é preciso criar um arquivo com a extensão da linguagem que se deseja trabalhar. Arquivos com a extensão `.py` indicam que os códigos escritos nele são da linguagem Python. Com o arquivo criado, é só utilizar o *IDE* para abri-lo e começar a codificar. Caso esteja utilizando um ambientes  de desenvolvimento *online*, geralmente, o processo é ainda mais simples, visto quê o arquivo `.py` é criado automaticamente. 

## Saída de dados

Exibir dados com Python é uma tarefa simples. Nesse primeiro exercício, o objetivo é fazer o *output* da frase "Olá Mundo!". Ela é popularmente apresentada para novos programadores quando estão dando os primeiro passos no mundo da programação.

Para conseguir exibir a mensagem, é preciso utilizar o método `print()`. Dentro do parênteses, coloca-se o que deseja exibir no terminal. Assim, para conseguir exibir a frase  "Olá Mundo!", basta escrever :

```python
print("Olá Mundo!")
# output = Olá Mundo!
``` 

Quando o arquivo for executando o algoritmo escrito será interpretado e a mensagem  "Olá Mundo!" aparecerá no terminal. 

## Entrada de dados

Fazendo uma pequena alteração no código é possível fazer o *output* de uma mensagem escrita no teclado ao invés de um texto previamente definido. Para isso basta utilizar o método `input()` e guardar os dados inseridos. Em seguida, é só exibir os dados com o método `print()`, da seguinte forma:

```python
dados = input("Insira algo aqui: ")
print(dados)
```

Ao executar um arquivo com o código a cima, o terminal exibirá a mensagem "Insira algo aqui: " e irá aguardar a entrada de uma mensagem. Por isso, para continuar a execução do código é preciso digitar a mensagem e apertar a tecla `Enter`. Em seguida a variável `dados`  irá guardar a mensagem escrita. Por fim, a variável `dados` é passada para o método `print()`, que faz o *output* da mensagem.
