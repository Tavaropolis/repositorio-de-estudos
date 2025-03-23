<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [del](./SetDel.md)

# del

`del` é uma palavra reservada que pode ser usada dentro de muitos contextos. Em [set](./Set.md) ela pode ser utilizada para remover um conjunto da memória, efetivamente deletando o set.

```python
thisset = {"apple", "banana", "cherry"}

del thisset

print(thisset) #Irá gerar pois o Set não existe mais na memória
```

O que o [python](./Index.md) faz por debaixo na verdade é remover a referência de memória ([variável](./Variaveis.md)) que está sendo passada para o `del`. Se existem outras variáveis apontando para o mesmo objeto, ele continua exitindo através das outras variáveis. 

Quando nenhuma variável aponta mais para aquele objeto, dizemos que o [refcounting](./RefCounting.md) dele chegou a zero, ele está completamente inacessível no código. Quando isso ocorre o python utiliza o seu [garbage collector](./GarbageCollector.md) efetivamente apaga esse objeto perdido, liberando espaço na memória.

```python
set_1 = {"apple", "banana", "cherry"}
set_2 = set_1

print(set_2 is set_1) #set_1 e set_2 compartilham a mesma referência de memória do objeto set

del set_1 #Removendo a referência de set_1

print(set_2) #A referência de set_2 ainda continua existindo
```