<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [null](./Null.md)

# null

**`null`** não é exatamente um tipo em **[Apex](./Index.md)**. Ele é uma forma que o Apex Runtime gerencia objetos declarados mas não inicializados: 

```apex
String texto = null;

System.debug('Texto é null? ' + (texto == null)); // true
```

Todos os tipos em **Apex** podem ser **`null`** até mesmo Objetos criados pelo programador. Porém uma vez como **`null`**, não se pode invocar os métodos e propriedades do tipo original, isso causará um erro de `NullPointerException`.

```apex
String texto = null;

System.debug('Texto é null? ' + (texto == null)); // true
System.debug('Tamanho do texto: ' + texto.length()); // GERA NullPointerException!
```

Outro ponto importante é que o **Apex** guarda metadados do tipo original do dado, ou seja, tipos diferentes de dados, mesmo sendo **`null`** não podem ser atribuídos um ao outro: 

```apex
String nome = null;
Endereco endereco = null;
Integer idade = null;

// Verificando se as variáveis são null
System.debug('Nome é null? ' + (nome == null));         // true
System.debug('Endereco é null? ' + (endereco == null)); // true
System.debug('Idade é null? ' + (idade == null));       // true

// Imprimindo os tipos das variáveis mesmo sendo null
System.debug('Tipo de nome: ' + String.valueOf(nome));       // null (mas Apex sabe que é String)
System.debug('Tipo de endereco: ' + String.valueOf(endereco)); // null (mas Apex sabe que é Endereco)
System.debug('Tipo de idade: ' + String.valueOf(idade));       // null (mas Apex sabe que é Integer)
```