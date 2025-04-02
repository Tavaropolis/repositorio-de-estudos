<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md)

>**Tópicos da linguagem Python**

# Básico

## Introdução
- [Executando um script Python](./ExecutandoScript.md)
- [Hello World](./HelloWorld.md)
- [Variáveis](./Variaveis.md)
- [Atribuição Múltipla](./AtribuicaoMultipla.md)
- [Comentários](./Comentarios.md)
  
## Dados Primitivos

### Conceitos básicos
- [Tipos de dados](./TiposDeDados.md)
- [type()](./Type.md)
- [isinstance()](./IsInstance.md)
  
### Números
- [Int](./Int.md)
- [Binário, Octal e Hexadecimal](./BinarioOctalHexadecimal.md)
- [Float](./Float.md)
- [Operadores Aritméticos](./Operadores.md)
- [Operadores de Atribuição](./OperadoresAtribuicao.md)
- [Notação Científica](./NotacaoCientifica.md)
- [Complex](./Complex.md)
  
### Texto
- [Str](./Str.md)
- [Concatenação de Strings](./ConcatString.md)
- [Multiplicação de String](./MultiplicacaoString.md)
- [Escape Sequences](./EscapeSequences.md)
- [Raw Strings](./RawStrings.md)
  
### Booleano
- [Bool](./Bool.md)
- [Truthy e Falsy](./TruthyFalsy.md)
  
## Funções Built-in úteis
- [input()](./Input.md)
- [help()](./Help.md)
- [id()](./Id.md)
  
## Outros conceitos úteis
- [Type Annotations](./TypeAnnotations.md)
- [Type Casting](./TypeCasting.md)
- [Internings](./Internings.md)
  
## Coleções

### Listas  
- [List](./List.md)
- [Acessando a lista](./AcessandoLista.md)
- [in Operator / not in Operator](./innotinOperator.md)
- [len()](./Len.md)
- [List Comprehension](./ListComprehension.md)
  
#### Adicionando a lista
- [append()](./ListAppend.md)
- [insert()](./ListInsert.md)
- [Concatenação de Listas](./ListConcat.md)
- [extend()](./ListExtend.md)
  
#### Removendo da lista
- [remove()](./ListRemove.md)
- [pop()](./ListPop.md)
- [clear()](./ClearList.md)
  
#### Outras funções úteis de lista
- [sort()](./SortList.md)
- [reverse()](./ReverseList.md)
- [count()](./CountList.md)
- [is Operator](./isOperator.md)

### Tuplas
- [Tuple](./Tuple.md)
- [Desempacotamento de Tuplas](./UnpackTuple.md)
- [Concatenação de Tuplas](./ConcatTuple.md)
- [Multiplicação de Tuplas](./MultiplicacaoTuple.md)

#### Outras funções úteis de tuplas
- [count()](./CountTuple.md)
- [index()](./IndexTuple.md)

### Set
- [Set](./Set.md)
- [Set Comprehension](./SetComprehension.md)
- [Removendo duplicados de uma lista com set](./SetListDuplicateRemoval.md)
- [Acessando o set](./SetAcessando.md)

#### Adicionando ao Set
- [add()](./SetAdd.md)
- [update()](./SetUpdate.md)

#### Removendo de um Set
- [remove()](./SetRemove.md)
- [discard()](./SetDiscard.md)
- [clear()](./SetClear.md)
- [del](./SetDel.md)

#### Outros métodos úteis de Set
- [difference()](./SetDifference.md)
- [intersection()](./SetIntersection.md)
- [symmetric_difference()](./SetSymmetricDifference.md)
- [union()](./SetUnion.md)
- [issubset()](./SetIsSubset.md)
- [issuperset()](./SetIsSuperset.md)
  
### Dict
- [Dict](./Dict.md)
- [Acessando o Dict](./DictAcessando.md)
- [get()](./DictGet.md)
- [keys()](./DictKeys.md)
- [values()](./DictValues.md)
- [items()](./DictItems.md)
- [Desempacotamento de Dict](./DictUnpack.md)
- [Dict Comprehension](./DictComprehension.md)
  
#### Removendo de um Dict
- [pop()](./DictPop.md)

### Outros tópicos sobre coleções
- [Shallow Copy e Deep Copy](./ShallowCopyDeepCopy.md)
- [enumerate()](./Enumerate.md)

## Funções
- [Funções](./Functions.md)
- [Parâmetros posicionais e nomeados](./FunctionsParams.md)
- [return](./FunctionsReturn.md)
- [global](./FunctionsGlobal.md)
- [*args](./FunctionsArgs.md)
- [**kwargs](./FunctionsKwargs.md)
- [pass](./FunctionsPass.md)
- [...](./FunctionEllipsis.md)    
- [High Order Functions](./FunctionsHighOrder.md)
- [lambda](./Lambda.md)
  
## Estruturas de Controle
- [if / elif / else](./ifElifElse.md)
- [if Ternário](./IfTernario.md)
- [Match Case](./MatchCase.md)
- [while](./While.md)
- [continue](./Continue.md)
- [break](./Break.md)
- [range()](./Range.md)

## Generators
- [Iterators](./Iterators.md)
- [Generators](./Generators.md)
- [Generator Expression](./GeneratorExpression.md)
- [yield from](./YieldFrom.md)

## Tratamento de Erros
- [try/execpt/finally](./TryExecptFinally.md)

## Orientação a Objetos

### Conceitos básicos
- [Class](./Class.md)
- [pass](./PassClass.md)
- [\_\_init\_\_()](./InitClass.md)
- [self](./SelfClass.md)

# Intermediário

## Módulos
- [import](./Import.md)
- [\_\_all\_\_](AllImport.md)
  
## Outros conceitos úteis
- [Walrus Operator](./WalrusOperator)

# Avançado

## Interpretadores Python
- [Jython](./Jython.md)