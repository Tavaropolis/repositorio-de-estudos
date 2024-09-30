<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Type Annotations](./TypeAnnotations.md)

# Type Annotations

Como dito anteriormente, Python é uma linguagem dinâmica e fracamente tipada, ou seja na declaração da variável, não precisamos dizer que tipo de dado aquela variável receberá, além de ser possível, ao longo do código, definir outros tipos de dados para aquela variável. 

Geralmente busca-se evitar atribuir tipos de dados diferentes para uma mesma variável, pois podem causar bugs inexperados. Para esses cenários, o Python possuí um recurso para ajudar chamado de Type Annotations (ou Type Hints). O programador pode dizer quais tipos de dados uma variável deveria receber com um **: tipodavariável**. Importante ressaltar que atribuir um tipo diferente a variável **NÃO** gerará erro. O máximo que pode ocorrer é algumas IDEs mostrarem um aviso na edição do código. 

```python
nome : str = "Fábio"
salario : float = 3000.00

salario = "Fábio" # Não irá gerar erro
```

Além disso, é possível deixar explícito o tipo de dados que dos parametros de uma função, bem como o tipo de retorno, expresssado após o **->**.
```python
def quadrado(base : int, exp : int) -> int:
  return base ** exp
```