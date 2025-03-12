<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [public](./ClassPublic.md)

# public 

Modificadores de acesso, são palavras reservadas que podemos aplicar a propridades e métodos de uma classe. Eles vão definir quem tem poder acesso a essas propriedades e métodos.

O `public`

```apex
public class Produto {
    public String nome = 'Notebook';

    public void exibirNome() {
        System.debug('Produto: ' + nome);
    }
}

// Acessando a propriedade e método public
Produto p = new Produto();
System.debug(p.nome); // Saída: Notebook
p.exibirNome();       // Saída: Produto: Notebook
```