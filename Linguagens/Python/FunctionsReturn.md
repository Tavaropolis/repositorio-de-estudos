<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [return](./FunctionsReturn.md)

# return
Assim como em outras linguagens, podemos usar a palavra reservada `return` para retornar o valor de uma função:

```python
def soma(a, b):
    return a + b

resultado = soma(5, 3)
print(resultado)  # Saída: 8
```

Por padrão em Python, se a **função** não tiver um `return`, ela retornará `None`:

```python
def minha_funcao():
    ...

print(minha_funcao()) #Saída None
``` 

Uma das particularidades do Python é que a **função** pode retornar mais de um valor. Quando passamos dois ou mais valores para serem retornados, a **função** acaba retornando uma [tupla](./Tuple.md) com os dois valores, podendo então ser aplicada a [desempacotação de tupla](./UnpackTuple.md).

É comum encontrarmos casos onde se use o `_` para essas situações. Ele é aplicado no desenpacotamento da tupla e serve para sinalizar que aquele retorno não tem muita importância para nossa aplicação:

```python
def check_status():
    return "Sucesso", "A função funcionou perfeitamente"

_, msg = check_status()
print(msg) #Saída: "A função funcionou perfeitamente"
```