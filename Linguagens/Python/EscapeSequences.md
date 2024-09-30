<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Escape Sequences](./EscapeSequences.md)

# Escape Sequences
Podemos passar algumas sequências especiais de caracteres capazes de realizar algumas função dentro de uma string. Em geral,eles são baseados na tabela [ASCII](../Fundamentos/ASCII.md).

|Escape Sequence|Meaning|
|-----|-----|
|\\\ |Backslash (\\)|
|\\' |Single quote (')|
|\\"|Double quote (")|
|\\a|ASCII Bell (BEL)|
|\\b|ASCII Backspace (BS)|
|\\f|ASCII Formfeed (FF)|
|\\n|ASCII Linefeed (LF)|
|\\r|ASCII Carriage Return (CR)|
|\\t|ASCII Horizontal Tab (TAB)|
|\\v|ASCII Vertical Tab (VT)|
|\\000|Character with octal value 000|
|\\xhh|Character with hex value hh|

## **\\\\**: Barra invertida
Como você pode ver todas as sequências de escape começam com a barra invertida(\\), logo, se quisermos mostrar uma barra invertida dentro da string, basta usar a dupla barra.

```python
caminho = "C:\\Users\\Joao\\Documentos"
print(caminho)

""" Saída do print
C:\Users\Joao\Documentos
"""
``` 

## **\\'**: Aspas simples
Strings são definidas por aspas portanto se quisermos colocar um aspas dentro da string, basta usar o caracter de escape.

```python
texto = 'Ele disse: \'Olá!\''
print(texto)

""" Saída do print
Ele disse: 'Olá!'
"""
```
## **\"**: Aspas dupla
```python
texto = "Ela respondeu: \"Bom dia!\""
print(texto)

""" Saída do print
"Bom dia!"
"""
``` 

## **\a**: Caracter de alerta
Emite um som de alerta do sistema.
```python
print("Som de alerta\a")
```

## **\\b**: Backspace
Age igual ao backspace do teclado (a tecla de apagar um caracter).

```python
texto = "ABC\bD"
print(texto)

""" Saída do print
ABD
"""
```

## **\\n**: Nova linha
Provavelmente o mais comum de todos, se queremos específicar que há uma quebra de linha basta adicionar o **\n**.

```python
texto = "Primeira linha\nSegunda linha"
print(texto)

""" Saída do print
Primeira linha
Segunda linha
"""
```

## **\\r**: Caractere de retorno
Joga o que tem atrás do caracter de retorno para frente apagando o que vem antes.
```python
texto = "Hello World\rPython"
print(texto)

"""
Python World
"""
```

## **\\t**: Tabulação
Insere uma tabulação na string.
```python
texto = "Nome\tIdade\tCidade\nJoão\t25\tSão Paulo"
print(texto)

"""
Nome    Idade   Cidade
João    25      São Paulo
"""
```

## **\\0**: ASCII valor octal
Você pode passar um valor octal que o caracter de escape, e ele retornará o valor correspondente da tabela ASCII.
```python
mystring = "Isto é um octal: \044"
print(mystring)

"""
Isto é um octal: $
"""
```

## **\\x**: ASCII valor octal
Você pode passar um valor hexadecimal que o caracter de escape, e ele retornará o valor correspondente da tabela ASCII.
```python
mystring = "Isto é um hexadecimal: \x24"
print(mystring)

"""
Isto é um hexadecimal: $
"""
```