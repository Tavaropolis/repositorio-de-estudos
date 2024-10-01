<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Complex](./Complex.md)

# Complex
Números complexos são números compostos de uma parte real e uma parte imaginário. Muito utilizado para resolver casos de raíz negativa. É um coneito de matemática, não necessariamente programação.

![](../../Assets/numeroscomplexos.png)

Para declarar um número complexo em Python utiliza-se o **j** para a parte imaginária. Não é tão comum usar esse tipo de dado, mas é interessante saber que existe.

```python
x = 3+5j
y = 5j
z = -5j

print(type(x)) #Saída <class 'complex'>
print(type(y)) #Saída <class 'complex'>
print(type(z)) #Saída <class 'complex'>
```