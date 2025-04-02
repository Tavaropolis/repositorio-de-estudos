<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [try / execpt / finally](./TryExecptFinally.md)

# try / execpt / finally

O `try/except` é um mecanismo para tratar exceções (erros) em [Python](./Index.md), permitindo que o programa continue executando mesmo quando ocorrem problemas. É usado para capturar e lidar com erros de forma controlada.

## Sintaxe básica

O bloco `try/except` é composto por duas partes principais:

1. O bloco `try`: contém o código que pode gerar uma exceção
2. O bloco `except`: contém o código que será executado caso uma exceção ocorra

```python
try:
    # Código que pode gerar uma exceção
    numero = int(input("Digite um número: "))
    resultado = 10 / numero
    print(f"O resultado é: {resultado}")
except:
    # Código que será executado se uma exceção ocorrer
    print("Ocorreu um erro!")
```

## Tratando exceções específicas

Podemos tratar diferentes tipos de exceções de forma específica:

```python
try:
    numero = int(input("Digite um número: "))
    resultado = 10 / numero
    print(f"O resultado é: {resultado}")
except ValueError:
    print("Por favor, digite um número válido!")
except ZeroDivisionError:
    print("Não é possível dividir por zero!")
except Exception as e:
    print(f"Ocorreu um erro inesperado: {e}")
```

## O bloco finally

O bloco `finally` é opcional e será executado sempre, independentemente se uma exceção ocorreu ou não. É útil para realizar ações de limpeza, como fechar arquivos ou conexões:

```python
arquivo = None
try:
    arquivo = open("arquivo.txt", "r")
    conteudo = arquivo.read()
    print(conteudo)
except FileNotFoundError:
    print("Arquivo não encontrado!")
finally:
    if arquivo:
        arquivo.close()
    print("Operação finalizada!")
```

## O bloco else

O bloco `else` é executado apenas se nenhuma exceção ocorrer no bloco `try`:

```python
try:
    numero = int(input("Digite um número: "))
    resultado = 10 / numero
except ValueError:
    print("Por favor, digite um número válido!")
except ZeroDivisionError:
    print("Não é possível dividir por zero!")
else:
    print(f"O resultado é: {resultado}")
finally:
    print("Operação finalizada!")
```

## Levantando exceções

Podemos criar nossas próprias exceções usando a palavra-chave `raise`:

```python
def verificar_idade(idade):
    if idade < 0:
        raise ValueError("A idade não pode ser negativa!")
    if idade > 150:
        raise ValueError("A idade parece ser inválida!")
    return idade

try:
    idade = verificar_idade(-5)
except ValueError as e:
    print(f"Erro: {e}")
```

## Hierarquia de exceções

Todas as exceções em Python herdam da classe `Exception`. Algumas exceções comuns incluem:

- `ValueError`: quando um valor é inválido
- `TypeError`: quando um tipo é inválido
- `IndexError`: quando tentamos acessar um índice que não existe
- `KeyError`: quando tentamos acessar uma chave que não existe em um dicionário
- `FileNotFoundError`: quando tentamos abrir um arquivo que não existe
- `ZeroDivisionError`: quando tentamos dividir por zero

