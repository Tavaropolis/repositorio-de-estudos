<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [Inner class / Outter class](./InnerClassOutterClass.md)

# Inner class / Outter class

Além da possibilidade de declarar [classes](./Classes.md) separadamente, podemos ainda declarar uma classe dentro de outra. A classe externa portanto é a `outter class` e a interna é a `inner class`. Cabe ao programador definir se é necessario criar duas classes separadas, ou uma dentro de outra classe, variando do problema que se deseja corrigir.

Segue um exemplo:

```apex
public class Pedido {
    public String cliente;
    public List<ItemPedido> itens = new List<ItemPedido>();

    // Inner class representando um item do pedido
    public class ItemPedido {
        public String nomeProduto;
        public Integer quantidade;
        public Decimal precoUnitario;

        // Construtor da inner class
        public ItemPedido(String nomeProduto, Integer quantidade, Decimal precoUnitario) {
            this.nomeProduto = nomeProduto;
            this.quantidade = quantidade;
            this.precoUnitario = precoUnitario;
        }

        // Método para calcular o valor total do item
        public Decimal getTotal() {
            return quantidade * precoUnitario;
        }
    }

    // Método para adicionar um item ao pedido
    public void adicionarItem(String nomeProduto, Integer quantidade, Decimal precoUnitario) {
        itens.add(new ItemPedido(nomeProduto, quantidade, precoUnitario));
    }

    // Método para calcular o total do pedido
    public Decimal getTotalPedido() {
        Decimal total = 0;
        for (ItemPedido item : itens) {
            total += item.getTotal();
        }
        return total;
    }
}

// Testando a classe
Pedido pedido = new Pedido();
pedido.cliente = 'João da Silva';
pedido.adicionarItem('Notebook', 1, 3000.00);
pedido.adicionarItem('Mouse', 2, 150.00);
System.debug('Total do Pedido: ' + pedido.getTotalPedido()); // Deve imprimir 3300.00
```

É possível instanciar um objeto da `inner class`, porém tem de se instanciar um objeto da `outter class` antes e só então chamar o conector da `inner class` (a menos que a `inner class` seja **static**). 
```apex
public class Pedido {
    public class ItemPedido {
        public String nomeProduto;
        
        public ItemPedido(String nomeProduto) {
            this.nomeProduto = nomeProduto;
        }
    }
}

// Criando a outer class primeiro
Pedido pedido = new Pedido();

// Criando a inner class através da instância da outer class
Pedido.ItemPedido item = pedido.new ItemPedido('Notebook');

System.debug('Produto: ' + item.nomeProduto); // Saída: Produto: Notebook
```

Quando a `inner class` é static, não é necessário instanciar um objeto da `outter class` para utilizá-la.

```apex
public class Pedido {
    public static class ItemPedido {
        public String nomeProduto;
        
        public ItemPedido(String nomeProduto) {
            this.nomeProduto = nomeProduto;
        }
    }
}

// Agora podemos instanciar diretamente a inner class sem criar a outer class
Pedido.ItemPedido item = new Pedido.ItemPedido('Mouse');

System.debug('Produto: ' + item.nomeProduto); // Saída: Produto: Mouse
```