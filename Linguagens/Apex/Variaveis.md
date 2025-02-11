<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [Variáveis](./Variaveis.md)

# Variáveis

Variáveis são um dos conceitos mais básicos da programação, o programador aloca um espaço da memória para salvar um dado, que posteriormente pode ser utilizado para fazer outras operações ou ser substituido por outro dado.

Aqui é a sintaxe de como se declarar uma variável em Apex.

```apex
String greeting = 'Hello World';
```

Agora alguns pontos a se notar alguns pontos em relação a natureza das variáveis do **Apex**, pois elas fazem o Apex ser classificado como uma linguagem **fortemente tipada** e **estática**.

- **Fortemente tipada** : Significa que ao contrário de linguagens fracamente tipadas como [Python](../Python/Index.md) e [Javascript](../Javascript/Index.md), em Apex nós obrigatoriamente precisamos dizer que tipo de dado a variável receberá (nota-se a palavra chave **String** na declaração do exemplo acima, ou seja, estamos dizendo que a variável será do tipo [String](./String.md)).
  
```apex
    Integer idade = 30; // Tipo inteiro
    String nome = 'João Silva'; // Tipo texto
    Double salario = 5000.75; // Tipo decimal
    Boolean ativo = true; // Tipo booleano
```

- **Estática**: Significa que uma fez atribuído um tipo a uma variável, ela poderá receber dados somente do mesmo tipo. Caso contrário será gerado um erro

```apex
    String message = 'Sou uma mensagem';
    message = 'Sou outra mensagem';
```

## Camel Case

A convenção de nomes de variável em **Apex** é de se adotar o camel case. Não é algo obrigatório, apenas uma convenção. Segue um exemplo de Camel Case.

```apex
souUmaVariavel = "Em Snake Case"
```