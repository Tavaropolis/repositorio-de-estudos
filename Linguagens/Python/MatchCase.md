<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Match Case](./MatchCase.md)

# Match Case

O **Match Case** é um recurso que surgiu a partir da versão 3.10 do Python (portanto não se deve usar em versões mais antigas). Ele é uma estrutura de tomada de decisão, muito similar ao switch case de linguagens como o [Javascript](../Javascript/Index.md), porém com muitos mais recursos.

Segue a síntaxe de um **match case**, utiliza-se a palavra match em uma váriavel, e o case para cada valor possível da variável:

```python
opcao = int(input("Digite o número da opção desejada: "))

match opcao:
    case 1:
        print("Você escolheu falar com o RH. Boa sorte... eles ainda estão de férias.")
    case 2:
        print("Você escolheu suporte técnico. Já tentou desligar e ligar novamente?")
    case 3:
        print("Você escolheu financeiro. Não se preocupe, sua conta será esquecida... por um tempo.")
    case _:
        print("Opção inválida. Por favor, pressione qualquer tecla para continuar reclamando.")
```
Pode se utilizar um caracter coringa com **_**. Ele funciona como um else do if, se nenhuma das condições do case forem atendidas, o valor cairá no **_**.

```python
cor = "vermelho"
match cor:
    case "vermelho":
        print("Pare!")
    case "amarelo":
        print("Atenção!")
    case "verde":
        print("Pode ir!")
    case _:
        print("Cor desconhecida.")
```

O **match case** ainda é capaz de fazer o desempacotamento de tuplas. Ele analizará o número de elementos na tupla, ativar a condição do case, e desempacotar a tupla.

```python
dados = ("Maria", 30)
match dados:
    case (nome, idade):
        print(f"Nome: {nome}, Idade: {idade}")
```

Quando aplicado a dicionários ele analisa as chaves, se o case tiver as mesmas chaves da variável anaisada, ele caíra no bloco de execução.

```python
pessoa = {"nome": "João", "idade": 25}
match pessoa:
    case {"nome": nome, "idade": idade}:
        print(f"{nome} tem {idade} anos.")
    case _:
        print("Estrutura desconhecida.")
```
Por fim, ainda é possível colocar condicionais (if statement) no case, para deixa-lo mais abrangente:

```python
numero = 10

match numero:
    case n if n % 2 == 0:
        print(f"{n} é par!")
    case _:
        print(f"{n} é ímpar!")
```