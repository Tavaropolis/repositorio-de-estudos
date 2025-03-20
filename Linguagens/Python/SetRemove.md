<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [remove()](./SetRemove.md)

# remove()

Uma das formas para remover um item de um [Set](./Set.md) é através da função **`remove()`**. Ela retira um item com base no valor. 

**`remove()` irá gerar um erro caso o valor não exista no Set**. Se você quer uma função similar que não corre risco de ocorrer erro, veja [`discard()`](./SetDiscard.md).

Lembrando que ele é um método de Set, ou seja é necessário ter uma lista instanciada para poder usar. Segue exemplo:

```python
fruits = {"apple", "banana", "cherry"}

fruits.remove("banana") 

print(fruits) #Saída {'apple', 'cherry'}
```