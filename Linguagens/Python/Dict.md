<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Dict](./Dict.md)

# Dict

O **dict** (ou dicionário) é uma estrutura de dados em Python que armazena pares chave-valor de forma eficiente, permitindo acesso rápido aos valores por meio de suas chaves. 

Podemos declarar um novo dicionário através das `{}` e utilizando a estrutura de chave, valor, exatamente se faz com um JSON. Segue exemplo:

```python
dados = {"nome": "Alice", "idade": 25, "cidade": "São Paulo"}
```

Também é possível utilizar o construtor `dict()`, similiar a como podemos fazer com [listas](./List.md) e [sets](./Set.md).

```python
dados = dict(nome="Alice", idade=25, cidade="São Paulo")
```

É ainda possível criar um **dict** vazio com o `{}` sem passar nenhum valor dentro:
```python
my_dict = {}
print(type(my_dict)) #Saída <class 'dict'>
```

## Regras para definir uma chave
As chaves de um **dict** precisam serem hashable, ou seja, é necessário que elas sejam possíveis de serem transformadas em hash com a função [hash()](./Hash.md). Afinal de contas, é isso que o python faz por debaixo dos panos, transforma o valor da chave em um número inteiro único.

Para que um valor seja hashable, ele precisa ser **imutável**. Seguem os tipos:
- [int](./Int.md)
- [float](./Float.md)
- [complex](./Complex.md)
- [bool](./Bool.md)
- [None](./None.md)
- [str](./Str.md)
- [bytes](./Bytes.md)
- [Tuplas](./Tuple.md) (Somente se os elementos internos também forem hasháveis)
- [frozenset](./FrozenSet.md)
- [range](./Range.md)
- Objetos Personalizados

```python
d = {
    42: "Número inteiro",
    3.14: "Número float",
    (1 + 2j): "Número complexo",
    True: "Booleano",
    None: "Valor None",
    "chave": "String",
    b"bytes": "Bytes",
    (1, 2, 3): "Tupla",
    frozenset({1, 2, 3}): "Frozenset",
    range(5): "Range"
}

# Iterando sobre as chaves e valores para imprimir seus tipos
for chave, valor in d.items():
    print(f"Chave: {chave}, Tipo da chave: {type(chave)}")
    print(f"Valor: {valor}, Tipo do valor: {type(valor)}")
    print("-" * 40)  # Separador

"""
Saída:
Chave: 42, Tipo da chave: <class 'int'>
Valor: Número inteiro, Tipo do valor: <class 'str'>
----------------------------------------
Chave: 3.14, Tipo da chave: <class 'float'>
Valor: Número float, Tipo do valor: <class 'str'>
----------------------------------------
Chave: (1+2j), Tipo da chave: <class 'complex'>
Valor: Número complexo, Tipo do valor: <class 'str'>
----------------------------------------
Chave: True, Tipo da chave: <class 'bool'>
Valor: Booleano, Tipo do valor: <class 'str'>
----------------------------------------
Chave: None, Tipo da chave: <class 'NoneType'>
Valor: Valor None, Tipo do valor: <class 'str'>
----------------------------------------
Chave: chave, Tipo da chave: <class 'str'>
Valor: String, Tipo do valor: <class 'str'>
----------------------------------------
Chave: b'bytes', Tipo da chave: <class 'bytes'>
Valor: Bytes, Tipo do valor: <class 'str'>
----------------------------------------
Chave: (1, 2, 3), Tipo da chave: <class 'tuple'>
Valor: Tupla, Tipo do valor: <class 'str'>
----------------------------------------
Chave: frozenset({1, 2, 3}), Tipo da chave: <class 'frozenset'>
Valor: Frozenset, Tipo do valor: <class 'str'>
----------------------------------------
Chave: range(0, 5), Tipo da chave: <class 'range'>
Valor: Range, Tipo do valor: <class 'str'>
----------------------------------------
"""
```