<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [print()](./Print.md)

# print()

- [sep](#sep)
- [end](#end)
- [flush](#flush)

A função **print()** é uma função built-in do Python e uma das suas ferramentas mais fundamentais e versáteis. No nível mais simples, **print()** aceita um ou mais argumentos e os exibe no console, separados por um espaço, seguidos por uma quebra de linha.

```python
print("Olá, mundo!")
```

O **print()** aceita vários argumentos numa mesma chamada, incluíndo [variáveis](./Variaveis.md).
```python
nome = "Gabriel"
print("Olá,", nome, "!") # Saída: Olá, Gabriel !
```

## sep
Por padrão, o **print()** separa múltiplos argumentos com um espaço. O parâmetro `sep` permite definir qualquer caractere ou string como separador.

```python
# Separador personalizado
print("python", "é", "incrível", sep="-") # Saída: python-é-incrível

# Exemplo prático: formatação de data
print("13", "08", "2026", sep="/") # Saída: 13/08/2026
```

## end
O **print()** termina automaticamente com um caractere de nova linha (\n). O parâmetro `end`  permite alterar esse comportamento, sendo útil para imprimir na mesma linha ou adicionar sufixos personalizados.

```python
# Imprimindo na mesma linha
print("Carregando", end="...")
print("Concluído!")
# Saída: Carregando...Concluído!

# Útil em loops
for i in range(3):
    print(i, end=" | ")
# Saída: 0 | 1 | 2 |
```

## flush
Em sistemas que utilizam buffering (armazenamento temporário em memória antes de exibir na tela), a saída pode não aparecer imediatamente. O argumento `flush=True` força a escrita imediata.

```python
import time

# Sem flush, a contagem poderia aparecer toda de uma vez
for i in range(3, 0, -1):
    print(i, end="...", flush=True)
    time.sleep(1)
print("Fogo!")
```
