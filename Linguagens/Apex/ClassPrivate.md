<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [private](./ClassPrivate.md)

# private 

Modificadores de acesso, são palavras reservadas que podemos aplicar a propridades e métodos de uma classe. Eles vão definir quem tem poder acesso a essas propriedades e métodos.

O `private` só pode ser acessado dentro da sua própria classe. Para acessar de fora da classe é necessário definir métodos publicos comumente chamada do `getter` (quando queremos acessar) e `setter` (quando queremos alterar).

Por padrão, se nenhuma modificador de acesso for declarado, o **Apex** entenderá que é um `private`

```apex
public class Produto {
    private String nome = 'Teclado';

    private void exibirNome() {
        System.debug('Produto: ' + nome);
    }

    // Métodos públicos para acessar a propriedade privada
    public String getNome() {
        return nome;
    }

    public void setNome(String novoNome) {
        this.nome = novoNome;
    }

    public void chamarMetodoPrivado() {
        exibirNome();
    }
}

// Criando o objeto
Produto p = new Produto();

// System.debug(p.nome); // ❌ ERRO! 'nome' é privado.
System.debug(p.getNome()); // ✅ Correto: Teclado
p.setNome('Monitor');
System.debug(p.getNome()); // ✅ Monitor

p.chamarMetodoPrivado(); // ✅ Produto: Monitor
```

Em casos onde envolve [Inner e outter classes](./InnerClassOutterClass.md)