---
title: "Adding & Removing Recipes"
---


# Adding and Removing Recipes
Before you start Adding or Removing recipes using ProbeJS is highly recomended.

## Adding Recipes
Adding recipes to GTCEu machines with KJS is quite simple, but keep in mind your Item and Fluid Inputs and Outputs are limited by the machine's recipe type.

### Example EBF Recipe

```js title="Electric Blast Furnace"
ServerEvents.recipes(event => 
    {
        event.recipes.gtceu.electric_blast_furnace('test')
            .itemInputs('64x minecraft:dirt', '32x minecraft:cobblestone')
            .inputFluids(Fluid.of('minecraft:water', 1000))
            .circuit(1)
            .itemOutputs('minecraft:diamond')
            .outputFluids(Fluid.of('minecraft:lava', 250))
            .duration(1000000)
            .EUt(120)
    }
)
```

## Removing Recipes
Removing recipes from GTCEu with KJS works exactly the same way as it works when removing recipes for anything else with KJS. 
<br>
!!! warning "Recipe ID's"
    NOTE currently the only way to view the recipe ID's of GTCEu recipes in GTCEu machines is with REI.

```js title="remove.js"
ServerEvents.recipes(event => 
    {
        event.remove(
            [
                {
                    type: 'gtceu:primitive_blast_furnace'
                },
                {
                    input: 'gtceu:iron_plate' 
                },
                {
                    output: 'gtceu:gold_plate'
                },
                {
                    mod: 'minecraft'
                }
            ]
        )
    }
)
```