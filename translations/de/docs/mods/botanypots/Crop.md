# Pflanzen

Klassenpfad: `mods.botanypots.Crop`

## Use

Importiere die Klasse mit `import mods.botanypots.Crop;` am Anfang deines Skripts.

## Erstelle eine Pflanze

`Crop.create(id, seed, display, tickRate, categories);`

- `id` &lt;String> Die ID der Pflanze. Dies ist die ID für den Namensraum und muss im Format `namensraum:pfad` sein.
- `seed` <[IIngredient](/vanilla/api/items/IIngredient)> The item used to plant the crop.
- `display` <[MCBlockState](/vanilla/api/blocks/MCBlockState)> The block to display when rendering the crop.
- `tickRate` &lt;int> One of the factors for how long a crop takes to grow.
- `categories` &lt;string[]> An array of soil categories this crop can be grown in.

This can be used to create a new crop. Keep in mind that drops need to be added separately.

```zenscript
Crop.create("examplepack:gold", <item:minecraft:gold_nugget>, <blockstate:minecraft:gold_block>, 3000, 2, ["stone"]);
```

## Remove A Crop

`Crop.remove(id);`

- `id` &lt;string> The id of the crop to remove. Dies ist die ID für den Namensraum und muss im Format `namensraum:pfad` sein.

Removes a crop based on it's id.

```zenscript
Crop.remove("botanypots:crop/wheat");
```

## Set Seed Item

`Crop.setSeed(id, seed);`

- `id` &lt;String> Die ID der Pflanze. Dies ist die ID für den Namensraum und muss im Format `namensraum:pfad` sein.
- `seed` <[IIngredient](/vanilla/api/items/IIngredient)> The item used to plant the crop.

Sets the item used to plant the crop.

```zenscript
Crop.setSeed("botanypots:crop/wheat", <item:minecraft:diamond>);
```

## Set Display Block

`Crop.setDisplay(id, state);`

- `id` &lt;String> Die ID der Pflanze. Dies ist die ID für den Namensraum und muss im Format `namensraum:pfad` sein.
- `display` <[MCBlockState](/vanilla/api/blocks/MCBlockState)> The block to display when rendering the crop.

Sets the block rendered for the crop.

```zenscript
Crop.setDisplay("botanypots:crop/wheat", <blockstate:minecraft:snow_block>);
```

## Set Tick Rate

`Crop.setTickRate(id, tickRate);`

- `id` &lt;String> Die ID der Pflanze. Dies ist die ID für den Namensraum und muss im Format `namensraum:pfad` sein.
- `tickRate` &lt;int> The updated tick rate. One of the factors for how long a crop takes to grow.

Sets the crop tick factor.

```zenscript
Crop.setTickRate("botanypots:crop/wheat", 5000);
```

## Changing Crop Categories

Changes the categories associated with the crop. Categories are used to match the valid soils to the crop.

### Add a Category to a Crop

`Crop.addCategory(id, categoriesToAdd);`

- `id` &lt;String> Die ID der Pflanze. Dies ist die ID für den Namensraum und muss im Format `namensraum:pfad` sein.
- `categoriesToAdd` &lt;string[]> An array of categories to associate with the crop.

```zenscript
Crop.addCategory("botanypots:crop/wheat", ["stone", "snow"]);
```

### Remove a Category From a Crop

`Crop.removeCategory(id, categoriesToRemove);`

- `id` &lt;String> Die ID der Pflanze. Dies ist die ID für den Namensraum und muss im Format `namensraum:pfad` sein.
- `categoriesToRemove` &lt;string[]> An array of categories to dissociate with the crop.

```zenscript
Crop.removeCategory("botanypots:crop/wheat", ["dirt"]);
```

### Clear All Categories From a Crop

`Crop.clearCategories(id);`

- `id` &lt;String> Die ID der Pflanze. Dies ist die ID für den Namensraum und muss im Format `namensraum:pfad` sein.

```zenscript
Crop.clearCategories("botanypots:crop/wheat");
```

## Crop Drops

### Adding Drops

`Crop.addDrop(id, drop, chance, min, max);`

- `id` &lt;string> The id of the crop to add a drop to. Dies ist die ID für den Namensraum und muss im Format `namensraum:pfad` sein.
- `drop` <[IItemStack](/vanilla/api/items/IItemStack)> The item to drop.
- `chance` &lt;float> The chance it drops.
- `min` &lt;int> The min amount of that item to give.
- `max` &lt;int> The max amount of that item to give.

This adds a new potential drop to the crop.

```zenscript
Crop.addDrop("botanypots:crop/wheat", <item:minecraft:diamond>, 0.05, 1, 1);
```

### Removing Drops

`Crop.removeDrop(id, toRemove);`

- `id` &lt;string> The id of the crop to remove a drop from. Dies ist die ID für den Namensraum und muss im Format `namensraum:pfad` sein.
- `toRemove` <[IIngredient](/vanilla/api/items/IIngredient)> The ingredient to match against for removal

Removes any drops that have a matching item.

```zenscript
Crop.removeDrop("botanypots:crop/wheat", <item:minecraft:wheat_seeds>);
```

## Getting All Ids

`Crop.getAllIds();`

- Returns: &lt;string[]> An array of all known crop ids at the time this is ran.

This will give you an array of all the known crop ids at the time.

```zenscript
// Log all ids to the crafttweaker.log file
for cropId in Crop.getAllIds() {
    println(cropId);
}
```

## Removing All Crops

This will completely remove all the crops currently registered. This is useful for if you want to recreate all the data from scratch through scripts.

```zenscript
Crop.removeAll();
```