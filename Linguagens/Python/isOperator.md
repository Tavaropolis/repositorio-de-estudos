<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Python.md) > [is Operator](./isOperator.md)

# is Operator
É preciso tomar um certo cuidado com o comparador de igualdade no Python (==). Seu uso em tipos primitivos é o mesmo da maioria das linguagens de programação, retorna True se os valores são iguais, e False se são diferentes, porém as coias começam a mudar em listas e tipos mais complexos.

Listas costumam trabalhar com referências de memória (isso desde os tempos de C), atribuir uma variável com lista a outra variável, não vai atribuir o valor, e sim a referência da lista na memória. Portanto quando comparamos duas listas, mesmo que elas tenham o mesmo valor, se tiverem referências de memória diferentes, costuma retornar false.

Em Python entretanto ao compararmos duas listas, ele tem a peculiaridade de comparar os valores, e não a referência, portanto gera-se cenários como no código abaixo.

```python
list1 = [1, 2, 3]
list2 = [1, 2, 3]

print(list1 == list2)  # True
```

Caso queremos explicitamente comparar a referência na memória, utilizamos o **is Operator** que retornará True ou False se as duas variáveis compartilham a mesma referência.

```python
list1 = [1, 2, 3]
list2 = [1, 2, 3]

print(list1 is list2)  # False
```