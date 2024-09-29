<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Notação Científica](./NotacaoCientifica.md)

# Notação Científica
Uma maneira muito útil de se representar números grandes é através de notação científica. Basicamente você multiplicar o número por 10 elevado a um expoente, simplificando números muito grandes (ou muito pequenos) em uma simples multiplicação.

Em Python, para se utilizar notação científica basta utilizar o **e** no meio do valor númerico, seguido do exponente da notação. Importante notar que todo o resultado de uma notação científica é um [float](./Float.md).

```python
num1 = 1e3  # 1 * 10^3
num2 = 5e-2  # 5 * 10^-2

print("Número 1:", num1) #Saída 1000.0
print("Número 2:", num2) #Saída 0.05
```

É possível formatar um número para ser exibido como notação nas strings, para isso é só sar o **.e**. No exemplo abaixo a saída será 1.00e+04, ou seja 1 * 10^4, exibindo duas casas decimais conforme especificado na [fstring](./Fstring).
```python
num = 10000

# Usar formatação científica em uma String
print(f"Em notação científica: {num:.2e}") #Saída 1.00e+04
```