<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Functions](./Functions.md)

# Funções

**Funções** são blocos de código reutilizáveis que realizam uma tarefa específica. Elas ajudam a organizar e modularizar o código, tornando-o mais legível e eficiente.

## Definir uma função
Para criar uma **função** em [Python](./Index.md), usamos a palavra-chave `def`, seguida pelo nome da **função**, parênteses e dois pontos. O código da **função** é indentado abaixo da definição.

```python
def saudacao():
    print("Olá, mundo!")
```

Após definir uma **função**, você pode chamá-la simplesmente usando seu nome seguido de parênteses.

```python
saudacao()  # Saída: Olá, mundo!
```

## Pârametros e argumentos
Assim como em outras linguagens de programação, as **funções** em Python aceitam pârametros:
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
## Retorno de uma função
Assim como em outras linguagens, podemos usar a palavra reservada `return` para retornar o valor de uma função:

```python
def soma(a, b):
    return a + b

resultado = soma(5, 3)
print(resultado)  # Saída: 8
```

Uma das particularidades do Python é que a **função** pode retornar mais de um valor. Quando passamos dois ou mais valores para serem retornados, a **função** acaba retornando uma [tupla](./Tuple.md) com os dois valores, podendo então ser aplicada a [desempacotação de tupla](./UnpackTuple.md).

É comum encontrarmos casos onde se use o `_` para essas situações. Ele é aplicado no desenpacotamento da tupla e serve para sinalizar que aquele retorno não tem muita importância para nossa aplicação:

```python
def check_status():
    return "Sucesso", "A função funcionou perfeitamente"

_, msg = check_status()
print(msg) #Saída: "A função funcionou perfeitamente"
```

## Número Variável de Argumentos: *args e **kwargs

Podemos passar números variáveis de argumentos de uma **função** através de `*args` e `**kwargs`:

### *args
`*args` é para pârametros posicionais variados. Para criar uma **função** com `*args` basta colocar um `*` antes do nome do parametro. Um `*args` é recebido pela função como uma [tupla](./Tuple.md).

```python
def soma_tudo(*numeros):
    return sum(numeros)

print(soma_tudo(1, 2, 3, 4))  # Saída: 10
```

Você pode combinar `*args` com pârametros posicionais ou pârametros nomeados. **O `*args` não precisa ser o único pârametro na função**:

`*args` com pârametro nomeado em uma função:
```python
def somar_numeros(*numeros, multiplicador=1):
    soma = sum(numeros)
    return soma * multiplicador

# Testando a função
print(somar_numeros(1, 2, 3))  # Saída: 6 (multiplicador padrão = 1)
print(somar_numeros(1, 2, 3, multiplicador=2))  # Saída: 12 (multiplicador = 2)
```

`*args` com parametro posicional **(é necessário que o `*args` seja o último pârametro)**:

```python
def minha_funcao(primeiro, *args):
print("Primeiro argumento:", primeiro)
print("Args:", args)

# Agora o primeiro argumento sempre será posicional
minha_funcao(10, 1, 2, 3)  
# Saída:
# Primeiro argumento: 10
# Args: (1, 2, 3)
```

Juntando `*args`, pârametros opcionais e pârametros nomeados: 

```python
def minha_funcao(primeiro, *args, extra=0):
print("Primeiro argumento:", primeiro)
print("Args:", args)
print("Extra:", extra)

# Chamadas válidas
minha_funcao(10, 1, 2, 3)  # Extra usa o valor padrão (0)
minha_funcao(10, 1, 2, 3, extra=5)  # Extra alterado
```

### **kwargs
Funciona semelhante ao `*args`, porém com a diferença que o `**kwargs` se aplica a quando queremos passar um número variável de pârametros nomeados. Para definir uma **função** com `**kwargs` basta colocar um `**` antes do pârametro na definição. A **função** recebe o `**kwargs` como um [dict](./Dict.md):

```python
def informacoes(**dados):
    for chave, valor in dados.items():
        print(f"{chave}: {valor}")

informacoes(nome="Ana", idade=22, cidade="São Paulo")
# Saída:
# nome: Ana
# idade: 22
# cidade: São Paulo
```
Assim como acontece com os `*args`, o `**kwargs` não precisa ser o único pârametro de uma **função**, ele pode ser combinado com pârametros posicionais, nomeados e até um `*args`:

`**kwargs` com pârametro nomeados, **(é necessário que o `*args` seja o último pârametro)**:
```python
def minha_funcao(extra=0, **kwargs):
    print("Extra:", extra)
    print("Kwargs:", kwargs)

# Chamadas válidas
minha_funcao(a=1, b=2)  # Extra usa o valor padrão (0)
# Saída: Extra: 0 | Kwargs: {'a': 1, 'b': 2}

minha_funcao(extra=10, a=1, b=2)  # Extra modificado
# Saída: Extra: 10 | Kwargs: {'a': 1, 'b': 2}
```

`**kwargs` e pârametros posicionais:

```python
def minha_funcao(primeiro, **kwargs):
    print("Primeiro argumento:", primeiro)
    print("Kwargs:", kwargs)

# Chamadas válidas
minha_funcao(10, a=1, b=2)  
# Saída: Primeiro argumento: 10 | Kwargs: {'a': 1, 'b': 2}

# Chamadas inválidas
minha_funcao(a=1, b=2)  # ERRO: falta o argumento posicional 'primeiro'
```

`**kwargs` com um pârametro nomeado e um `*args`:
```python
def minha_funcao(*args, extra=0, **kwargs):
    print("Args:", args)
    print("Extra:", extra)
    print("Kwargs:", kwargs)

# Chamadas válidas
minha_funcao(1, 2, 3, extra=10, nome="Carlos", idade=25)
# Saída:
# Args: (1, 2, 3)
# Extra: 10
# Kwargs: {'nome': 'Carlos', 'idade': 25}
```