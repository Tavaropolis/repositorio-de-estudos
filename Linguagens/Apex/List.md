<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [List](./List.md)

# List

Assim como em outras linguagens de programação, em **Apex** podemos agrupar dados de um mesmo conjunto em uma lista.

Para se declarar uma lista vazia em **Apex** utiliza-se a síntaxe abaixo. Nota-se que precisa-se especificar o tipo de dados que a lista irá receber. Também precisa usar a palavra reservada **new**. Iremos ver mais isso em orientação de Objetos, mas por se tratar de um tipo derivado (não-primitivo) é preciso usar o **new** para instanciar um novo objeto do tipo **List**.

```apex
List<String> fruitList = new List<String>();
```

As listas podem ser iniciadas já com valores: 
```apex
List<String> names = new List<String>{'Alice', 'Bob'};
```

Ainda que você só possa passar dados do mesmo tipo em uma lista, se você definir o tipo como **Object** (que é a classe pai de todas as outras classes) é possível passar dados de tipos diferentes.

```apex
List<Object> randomData = new List<Object>{'Alice', 25, 99.99};
```