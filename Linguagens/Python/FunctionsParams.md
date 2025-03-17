<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Parâmetros posicionais e nomeados](./FunctionsParams.md)

# Parâmetros posicionais e nomeados
Assim como em outras linguagens de programação, as **funções** em Python aceitam parâmetros:

```python
def saudacao_personalizada(nome):
    print(f"Olá, {nome}!")

saudacao_personalizada("Carlos")  # Saída: Olá, Carlos!
```
Podemos definir um valor padrão para o parametro, caso a **função** seja chamada sem ter um argumento passado:

```python
def saudacao(nome="Visitante"):
    print(f"Olá, {nome}!")

saudacao()           # Saída: Olá, Visitante!
saudacao("Ana")      # Saída: Olá, Ana!
```

Ao chamar funções no Python os argumentos podem ser **posicionais ou nomeados**. Os argumentos posicionais, tem de seguir a ordem que eles foram declarados na **função**. Já os nomeados podem serem chamados em qualquer ordem, já que a **função** segue o nome do parâmetro como referência. Segue a comparação: 

```python
def dados_pessoais(nome, idade):
    print(f"Nome: {nome}, Idade: {idade}")

dados_pessoais(idade=25, nome="Lucas")  # Saída: Nome: Lucas, Idade: 25
dados_pessoais("Lucas", 25) #Saída Nome: Lucas, Idade: 25
```

Apesar de o Python aceitar parametros posicionais e nomeados na mesma chamada de **função**, é interessante tomar cuidado ao usar os dois misturados, pois podem acabar gerando erro se mal implementado. A lógica que o interpretador segue é seguindo os posicionais primeiro (**eles precisam estar antes dos nomeados na chamada, se não estiverem irá ser gerado erro**), e depois aplicando os nomeados, independente da ordem que os nomeados estão

```python
def dados_pessoais(nome, idade, sexo):
    print(f"Nome: {nome}, Idade: {idade}, Sexo: {sexo}")

dados_pessoais("Lucas", sexo="Masculino", idade=25)  # Saída: Nome: Lucas, Idade: 25, Sexo: Masculino
```