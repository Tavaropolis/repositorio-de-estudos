<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [Safe Navigation Operator](./SafeNavigationOperator.md)

# Safe Navigation Operator

O **`Safe Navigation Operator`** é um operador mais recente na linguagem **Apex**. Ele é utilizado quando precisamos utilizar métodos ou propriedades de uma classe que não teve um objeto instânciado. 

Por exemplo, digamos que queremos usar o valor da propriedade **rua** de um objeto **Cliente**. O ideal seria utilizar um [if](./If.md) para verificar se o obejto **Endereco** está com valor (não seja [null](./Null.md)), ou seja se esse Objeto foi instanciado na memória. Se tentarmos acessar a propriedade sem valor receberemos um erro de `NullPointerException`.

O `NullPointerException` ocorre pois como o objeto **Endereco** não foi instanciado ainda, os valores da sua propriedade não existem na memória. Ao tentarmos acessar a propriedade **rua**, como ela não existe na memória, recebemos um erro de ponteiro.

Com o **`Safe Navigation Operator`** não precisamos mais utilizar um **if**, o operador verifica se existe ou não o valor, e retornará null caso ele não esteja inicializado.

Por exemplo:
```apex
public class Cliente {
    public String nome;
    public Endereco endereco;
    
    // Construtor
    public Cliente(String nome, Endereco endereco) {
        this.nome = nome;
        this.endereco = endereco;
    }
}

public class Endereco {
    public String rua;
    
    // Construtor
    public Endereco(String rua) {
        this.rua = rua;
    }
}

public class SafeNavigationExample {
    public static void testarSafeNavigation() {
        // Criando um cliente com endereço
        Cliente cliente1 = new Cliente('João', new Endereco('Rua Principal, 123'));

        // Criando um cliente sem endereço (null)
        Cliente cliente2 = new Cliente('Maria', null);

        // Usando Safe Navigation Operator para acessar a rua do cliente1
        String ruaCliente1 = cliente1?.endereco?.rua;
        System.debug('Rua do Cliente 1: ' + ruaCliente1); // Saída esperada: "Rua Principal, 123"

        // Usando Safe Navigation Operator para acessar a rua do cliente2
        String ruaCliente2 = cliente2?.endereco?.rua;
        System.debug('Rua do Cliente 2: ' + ruaCliente2); // Saída esperada: "null", sem erro
    }
}
```

Para fins de comparação, segue o exemplo de como esse código teria de ser desenvolvido sem o **`Safe Navigation Operator`** :

```apex
public class Cliente {
    public String nome;
    public Endereco endereco;
    
    // Construtor
    public Cliente(String nome, Endereco endereco) {
        this.nome = nome;
        this.endereco = endereco;
    }
}

public class Endereco {
    public String rua;
    
    // Construtor
    public Endereco(String rua) {
        this.rua = rua;
    }
}

public class SafeNavigationExample {
    public static void testarSemSafeNavigation() {
        // Criando um cliente com endereço
        Cliente cliente1 = new Cliente('João', new Endereco('Rua Principal, 123'));

        // Criando um cliente sem endereço (null)
        Cliente cliente2 = new Cliente('Maria', null);

        // Usando IF tradicional para evitar NullPointerException ao acessar ruaCliente1
        String ruaCliente1;
        if (cliente1 != null && cliente1.endereco != null) {
            ruaCliente1 = cliente1.endereco.rua;
        } else {
            ruaCliente1 = null;
        }
        System.debug('Rua do Cliente 1: ' + ruaCliente1); // Saída esperada: "Rua Principal, 123"

        // Usando IF tradicional para evitar NullPointerException ao acessar ruaCliente2
        String ruaCliente2;
        if (cliente2 != null && cliente2.endereco != null) {
            ruaCliente2 = cliente2.endereco.rua;
        } else {
            ruaCliente2 = null;
        }
        System.debug('Rua do Cliente 2: ' + ruaCliente2); // Saída esperada: "null", sem erro
    }
}
```