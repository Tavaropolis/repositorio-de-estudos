<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Jython](./Jython.md)

# Jython

Além do interpretador padrão do Python, o [`CPython`](./CPython.md), as pessoas foram criando outros interpretadores para serem utilizados em projetos/situações mais específicas. O **`Jython`** é um desses interpretadores python alternativos.

O ciclo normal de compilação do `Cpython`, o código fonte escrito em um arquivo `.py` para bytecode python, gerando um arquivo `.pyc` como resultado. O interpretador então lê esse arquivo `.pyc` e faz com que os comandos sejam executados. Ou seja se tivermos o código compilado do python, é possível executá-lo em qualquer sistema operacional, contando que a máquina tenha o interpretador.

A diferença entre o `Cpython` e o `Jython` é que o `Jython` ao invés de compilar o código para `.pyc`, ele será compilado para `.class` podendo ser executado na [Java Virtual Machine](../Java/JVM.md). Ou seja, com o `Jython` é possível executar scripts java, dentro de um interpretador Python. Mas ainda assim, o `Jyhon` consegue diferenciar os códigos python e executa-los separadamente ao java. Podemos então ter códigos python e Java sendo executados a partir de um mesmo script.

**Porém o `Jython` só consegue interpretar códigos Python 2**

Segue o exemplo:

```python
from java.lang import System # Java import
import javax.swing as libswing

print('Running on Java version: ' + System.getProperty('java.version'))
print('Unix time from Java: ' + str(System.currentTimeMillis()))
 
pnumero = libswing.JOptionPane.showInputDialog("Digite um Numero Inteiro: ") 
snumero = libswing.JOptionPane.showInputDialog("Digite um Numero Inteiro: ") 
soma = int(pnumero) + int(snumero) 
libswing.JOptionPane.showMessageDialog(None, "A soma dos numeros:  %d " % soma)
```

## Instalação

Para instalar o `Jython` tem de se baixar o interpretador no site oficial: [https://www.jython.org/](https://www.jython.org/)

Também é necessário adionar o caminho do executável para o PATH do Windows.

Uma vez tudo tendo sido configurado. Basta executar um arquivo python chamando o `Jython`
```shell
jynthon nomedoarquivo.py
```