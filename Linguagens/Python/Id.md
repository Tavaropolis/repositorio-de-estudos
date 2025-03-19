<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [id()](./Id.md)

# id()

Essa função trabalha um pouco com os conceitos de [orientação a objetos](./Index.md#orientação-a-objetos). Toda vez que criamos um novo dado de um tipo primitivo, o que acontece por debaixo dos panos é que o [python](./Index.md) vai instanciar um objeto daquele tipo. Ou seja quando criamos uma [variável](./Variaveis.md) do tipo [Str](./Str.md), o Python está criando um objeto do tipo Str. 

Cada objeto criado pelo Python recebe um id único. A função **id()**, portanto, é uma função built-in do Python que retorna o valor do id do objeto na memória (Esse valor costuma mudar entre as execuções do script).

```python
salve = "Bom dia"
print(id(salve))
```

Note que objetos imutáveis como Str, o objeto não é alterado quando queremos modificá-lo, por baixo dos panos, o Python apaga o objeto e gere um novo no lugar:

```python
salve = "Bom dia"
print(id(salve))
salve = salve.capitalize()
print(id(salve))
```

É válido dizer que podem haver exeções. O Python utiliza [internings](./Internings.md) para salvar objetos imutáveis simples de mesmo valor na mesma referência de memória, para poupar o espaço gasto na memória. 

```python
a = "hello"
b = "hello"
print(id(a) == id(b))  # True, ambas apontam para o mesmo objeto!
```