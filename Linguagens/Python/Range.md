<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [range()](./Range.md)

# range()

**range()** é uma função built-int que gera uma sequência iterável de números. 

A função recebe três argumentos: 
- **start**: o número que deve iniciar a sequência. É um argumento opcional. Se omitido será considerado 0.
- **stop**: o número que deve encerrar a sequência, assim como muitas estruturas ele não é incluido na sequencia. Por exemplo se queremos uma sequência até 5, o stop precisa ser 6. Este parametro é obrigatório
- **step**: De quanto em quanto deve ser contado. também é opcional. O valor padrão é 1.

Simplificando seria portanto range(*start*, *stop*, *step*). Segue exemplos: 

```python
x = range(5) #sequência de 0 a 4

for n in x:
  print(n)
```

```python
x = range(1, 10, 2) #Todos os ímpares de 1 a 10

for i in range(x):
    print(i)
```
```python
x = range(10, 0, -1) #Contagem regressiva 10 a 1

for i in range(x):
    print(i)
```

Por fim um ponto importante a se destacar é que um retorno de range é um **objeto range** e não uma lista. Se você quiser aplicar funções de lista é necessário realizar a conversão.

```python
print(type(range(0,4))) #<class 'range'>
```