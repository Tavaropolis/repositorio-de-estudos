<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [if Ternário](./ifTernario.md)

# if Ternário

Existe um facilitador para o if quando temos condições muito simples (geralmente onde o dado vai ou ser uma coisa, ou ser outra), esse tipo de if é chamado de **ternário**. 

É preciso tomar um pouco de cuidado já que o **ternário** é um pouco diferente do comum encontrado em outras linguagens.

```python
a = 10
b = 20

# python ternary operator
min = "a é menor" if a < b else "b é menor"

print(min) #a é menor 
```

Podemos inclusive abrir outro ternario dentro de uma das condições, apesar de não ser recomendável.

```python
# python ternary operator
condicao = "Valor" if False else "Outro Valor" if True else "Fim"

print(condicao) #Outro Valor 
```