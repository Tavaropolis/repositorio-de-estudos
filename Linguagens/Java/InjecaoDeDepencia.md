<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Java](./Index.md) > [Injeção de Dependência](./InjecaoDeDependecia.md)

# Injeção de Dependência
Injeção de depência (as vezes abreviada para DI), trata-se de um padrão de projeto onde a ideia é impedir que classes possam instanciar objetos de outras classes, ao invés disso, o objeto externo deve ser passado via construtor ou algum outro método.

Apesar de a primeira vista parecer simples e não muito prático, é extramente útil para refatorarmos nosso código. Pois assim, bastaria modificar uma classe, ao invés de a classe e todas as outras que a instanciam. 

Exemplo sem Injenção de Dependência. Repare que a classe **Car** instância um objeto **engine**.
```java 
class Car {
    private Engine engine;

    // O Carro cria sua própria dependência (Engine)
    public Car() {
        this.engine = new Engine();  // Carro cria a dependência diretamente
    }

    public void start() {
        engine.run();
    }
}

class Engine {
    public void run() {
        System.out.println("Engine running!");
    }
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();  // O Carro cria a Engine
        car.start();
    }
}

```

Exemplo com aplicação da injenção de dependência. O objeto **engine** está sendo passado via construtor, mas poderia ser via setter ou outro método.
```java
class Car {
    private Engine engine;

    // Injeção de dependência via construtor
    public Car(Engine engine) {
        this.engine = engine;  // A Engine é injetada aqui
    }

    public void start() {
        engine.run();
    }
}

class Engine {
    public void run() {
        System.out.println("Engine running!");
    }
}

public class Main {
    public static void main(String[] args) {
        // Criando a dependência manualmente
        Engine engine = new Engine();  // Criando o motor

        // Injetando a dependência no Carro
        Car car = new Car(engine);  // Passando o motor para o carro

        car.start();  // O carro usa a Engine injetada
    }
}
```