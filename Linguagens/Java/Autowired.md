<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Java](./Index.md) > [@Autowired](./InjecaoDeDependecia.md)

# @Autowired
@Autowired é uma das anotações mais comuns do **Spring**, ela é utilizada para realizar injeção de dependências de forma automática. Ou seja ao invés de o programador explícitamente declarar um novo objeto dentro de uma classe, o Spring consegue gerenciar isso automáticamente e sede a instância de um objeto fora da classe, na chamada do método. Ou seja, diminuindo a aclopação.

**@Autowired** declarado no construtor
```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Component;

@Component
public class Carro {
    private final Motor motor;

    @Autowired
    public Carro(Motor motor) {
        this.motor = motor;
    }

    public void mostrarInfo() {
        System.out.println("Carro com motor: " + motor.getTipo());
    }
}
```

**@Autowired** declarado no método Setter

```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Component;

@Component
public class Carro {
    private Motor motor;

    @Autowired
    public void setMotor(Motor motor) {
        this.motor = motor;
    }

    public void mostrarInfo() {
        System.out.println("Carro com motor: " + motor.getTipo());
    }
}
```

**@Autowired** declarado em uma propriedade da classe
```java
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Component;

@Component
public class Carro {
    @Autowired
    private Motor motor;

    public void mostrarInfo() {
        System.out.println("Carro com motor: " + motor.getTipo());
    }
}
```