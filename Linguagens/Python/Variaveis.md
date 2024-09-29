<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Variáveis](./Variaveis.md)

# Variáveis

Variáveis são um dos conceitos mais básicos da programação, o programador aloca um espaço da memória para salvar um dado, que posteriormente pode ser utilizado para fazer outras operações ou ser substituido por outro dado.

Aqui é a sintaxe de como se declarar uma variável em Python.

```python
variavel = "Eu sou uma variável"
```

Agora alguns pontos a se notar alguns pontos em relação a natureza das variáveis do Python, pois elas fazem o Python ser classificado como uma linguagem **fracamente tipada** e **dinâmica**. 

- **Fracamente tipada** : Significa que ao contrário de linguagens fortemente tipadas como C e Java, em Python não precisamos dizer que tipo de dado a variável receberá (não se preocupe, vou falar mais sobre tipos mais tarde).
  
```python
# Inicialmente um inteiro
variavel = 10
print(type(variavel))  # <class 'int'>

# Agora uma string
variavel = "Olá, mundo!"
print(type(variavel))  # <class 'str'>
```
  
- **Dinâmica**: Significa que a variável é definida em tempo de execução e não em tempo de compilação, ou seja, uma mesma variável pode receber tipos diferentes de dados.

```python
x = 5        # x é um inteiro
x = "Olá"    # agora x é uma string
```

## Regras de nome de variáveis
Existem algumas regras que se deve seguir na hora de se nomear uma variável no Python:

- O nome da variável deve começar com uma letra ou underline (_).
- O nome da variável não pode começar com número.
- O nome da variável só pode ter letras, números e underline (_).
- Nomes de variáveis são case-sensitive (diferencia minúsculo e maiúsculo.)
- O nome da variável não pode conter palavras reservadas do Python.

## Snake Case
A convenção de nomes de variável é de se adotar o snake case. Não é algo obrigatório, apenas uma convenção. Segue um exemplo de Snake Case.

```python
sou_uma varavel = "Em Snake Case"
```