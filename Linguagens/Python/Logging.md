<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [logging](./Logging.md)

# logging

O logging é o módulo padrão da biblioteca do Python para registro de eventos, muito mais robusto que print() para aplicações reais.

## Arquitetura geral
O logging é construído em torno de quatro peças que trabalham juntas:

- **Logger**: ponto de entrada que a aplicação usa para emitir mensagens.
- **Handler**: decide para onde a mensagem vai (terminal, arquivo, rede, etc.).
- **Formatter**: decide como a mensagem é formatada.
- **Filter**: decide se a mensagem deve ou não ser processada (regras adicionais além do nível).

Segue um exemplo de como configurar cada uma dessas peças individualmente:

```python
# Criando um logger
logger = logging.getLogger("meu_app")
logger.setLevel(logging.DEBUG)

# Handler para console
console_handler = logging.StreamHandler()
console_handler.setLevel(logging.INFO)

# Handler para arquivo
file_handler = logging.FileHandler("debug.log")
file_handler.setLevel(logging.DEBUG)

# Criando um Formatter e adicionando aos handlers
formatter = logging.Formatter('%(levelname)s - %(message)s')
console_handler.setFormatter(formatter)
file_handler.setFormatter(formatter)

# Adicionando handlers ao logger
logger.addHandler(console_handler)
logger.addHandler(file_handler)

logger.info("Log informativo no console e arquivo.")
logger.debug("Log de debug apenas no arquivo.")
```

Porém também é possível configurar tudo dentro de uma mesma função `logging.basicConfig()`: 
```python
import logging

logging.basicConfig(
    level=logging.INFO,
    format='%(asctime)s - %(name)s - %(levelname)s - %(message)s',
    datefmt='%Y-%m-%d %H:%M:%S'
)
logging.info("Mensagem com timestamp e nível formatados.") #Saída: 2026-08-13 14:53:31 - root - INFO - Mensagem com timestamp e nível formatados.
```
## Níveis de log e sua hierarquia numérica
Cada nível tem um valor inteiro associado, o que permite comparações e filtragem.
```python
import logging

print(logging.DEBUG)     # 10
print(logging.INFO)      # 20
print(logging.WARNING)   # 30
print(logging.ERROR)     # 40
print(logging.CRITICAL)  # 50
```

Só são processadas mensagens com nível igual ou superior ao configurado no logger/handler:
```python
import logging

logger = logging.getLogger("minha_app")

logger.setLevel(logging.WARNING)
logger.info("isso não aparece")     # 20 < 30
logger.error("isso aparece")        # 40 >= 30
```

## Salvando Logs em Arquivos
Para persistir os logs, basta definir o argumento `filename` na configuração.

```python
import logging

logging.basicConfig(
    filename='app.log',
    filemode='a', # 'a' para append (adicionar), 'w' para sobrescrever
    level=logging.INFO
)
logging.info("Log registrado em arquivo.")
```

Também é possível configurar um `handler` via `logging.FileHandler()`:

```python
import logging

# Criando um logger
logger = logging.getLogger("meu_app")
logger.setLevel(logging.DEBUG)

# Handler para arquivo
file_handler = logging.FileHandler("debug.log")
file_handler.setLevel(logging.INFO)
logger.addHandler(file_handler)

logger.debug("Log de debug que não vai pro arquivo.")
logger.info("Log informativo no arquivo.")
```