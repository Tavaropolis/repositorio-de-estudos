<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Python.md) > [Float](./Float.md)

# Float

Números float, também chamados de ponto flutuante, são números que possuem informações após a vírgula (partes decimais). Importante lembrar que no padrão americano, a vírgula (,) na matemática corresponde ao (.). Veja um exemplo de declaração abaixo.

```python
numero_float = 3.14
print(type(numero_float))  # Saída: <class 'float'>
```
O interpretador Python vai inferir se um número é um int ou um float, no momento da atribuição da variável.

```python
inteiro = 10
numero_float = 3.14

print(type(inteiro))  # Saída: <class 'int'>
print(type(numero_float))  # Saída: <class 'float'>
```

Um truque interessante no Python é que é possível atribuir um float sem passar uma casa decimal, apenas colocando um ponto(.) após o número e o interpretador Python vai inferir que o número é um .0. Segue um exemplo em código

```python
foo = 1.
print(foo) #Saída 1.0
```

## Açúcar Síntatico
Algumas operações matemática vão sempre retornar um float, independente se a conta foi feita com números inteiros ou float.

```python
divisao_real = 5 / 2  # 2.5
print(divisao_real)  # Saída: 2.5
```

Para que a divisão retorne um valor inteiro é preciso utilizar o operador **//**

```python
divisao_inteira = 5 // 2  # 2
print(divisao_inteira)  # Saída: 2
```