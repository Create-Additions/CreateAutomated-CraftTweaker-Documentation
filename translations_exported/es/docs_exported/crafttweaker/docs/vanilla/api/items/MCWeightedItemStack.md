# MCWeightedItemStack

Una pila de ítems con una oportunidad, usualmente usada para las salidas de recetas.

 Cuidado, si la pila que fue usada para crear el WeightedStack era mutable, ¡entonces el setter de tamaño también mutará la pila original!

## Importing the class

It might be required for you to import the package if you encounter any issues (like casting an Array), so better be safe than sorry and add the import at the very top of the file.
```zenscript
import crafttweaker.api.item.MCWeightedItemStack;
```


## Implemented Interfaces
MCWeightedItemStack implements the following interfaces. That means all methods defined in these interfaces are also available in MCWeightedItemStack

- [CommandStringDisplayable](/vanilla/api/brackets/CommandStringDisplayable)

## Constructors

Manually creates the weightedItemStack. <br />  Usually you can use the operator or `.weight(weight)` method of IItemStack, though
```zenscript
new MCWeightedItemStack(itemStack as IItemStack, weight as double) as MCWeightedItemStack
new MCWeightedItemStack(<item:minecraft:bedrock>, 0.5D);
```
| Parameter       | Type                                        | Description                             |
| --------------- | ------------------------------------------- | --------------------------------------- |
| pila de objetos | [IItemStack](/vanilla/api/items/IItemStack) | La Pila                                 |
| weight          | double                                      | La oportunidad, entre 0 (0%) y 1 (100%) |



## Methods

:::group{name=weight}

Creates a new Weighted Stack with the given weight

Returns: A new WeightedItemStack  
Return Type: [MCWeightedItemStack](/vanilla/api/items/MCWeightedItemStack)

```zenscript
// MCWeightedItemStack.weight(newWeight as double) as MCWeightedItemStack

<item:minecraft:bedrock>.weight(0.5D).weight(0.75D);
```

| Parameter  | Type   | Description   |
| ---------- | ------ | ------------- |
| nuevo peso | double | El porcentaje |


:::


## Operadores

:::group{name=MOD}

Creates a new Weighted Stack with the given percentage

```zenscript
myMCWeightedItemStack % newWeight as int
<item:minecraft:bedrock>.weight(0.5D) % 75
```

:::

:::group{name=MUL}

Sets the itemStack's amount. <br />   <br />  If the original Stack was mutable, also mutates the original stack's size.

```zenscript
myMCWeightedItemStack * newAmount as int
<item:minecraft:bedrock>.weight(0.5D) * 5
```

:::


## Properties

| Nombre | Type                                        | Has Getter | Has Setter | Description                               |
| ------ | ------------------------------------------- | ---------- | ---------- | ----------------------------------------- |
| stack  | [IItemStack](/vanilla/api/items/IItemStack) | true       | false      | Gets the original (unweighted) stack      |
| weight | double                                      | true       | false      | Gets the weight (usually between 0 and 1) |
