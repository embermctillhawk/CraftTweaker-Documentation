# ByteData



This class was added by a mod with mod-id `crafttweaker`. So you need to have this mod installed if you want to use this feature.

## Diese Klasse importieren
It might be required for you to import the package if you encounter any issues (like casting an Array), so better be safe than sorry and add the import.
```zenscript
crafttweaker.api.data.ByteData
```

## Implemented Interfaces
ByteData implements the following interfaces. That means any method available to them can also be used on this class.
- [crafttweaker.api.data.IData](/vanilla/api/data/IData)
- [crafttweaker.api.data.INumberData](/vanilla/api/data/INumberData)

## Constructors
```zenscript
new crafttweaker.api.data.ByteData(internal as byte);
```
| Parameter | Type | Beschreibung            |
| --------- | ---- | ----------------------- |
| internal  | byte | No description provided |



## Methoden
### asList

Gets a List<IData> representation of this IData, returns null on anything but [crafttweaker.api.data.ListData](/vanilla/api/data/ListData).

 Returns: `null if this IData is not a list.`

Retourentyp: Liste&lt;[crafttweaker.api.data.IData](/vanilla/api/data/IData)&gt;

```zenscript
4.asList();
```

### asMap

Gets a Map<String, IData> representation of this IData, returns null on anything but [crafttweaker.api.data.MapData](/vanilla/api/data/MapData).

 Returns: `null if this IData is not a map.`

Rückgabetyp: [craftweaker.api.data.IData](/vanilla/api/data/IData)[String]

```zenscript
4.asMap();
```

### asString

Gets the String representation of this IData

 Returns: `String that represents this IData (value and type).`

Return type: String

```zenscript
4.asString();
```

### contains

Checks if this IData contains another IData, mainly used in subclasses of [crafttweaker.api.data.ICollectionData](/vanilla/api/data/ICollectionData), is the same as an equals check on other IData types

 Gibt an: `wahr wenn die angegebenen IDaten in dieser IData enthalten sind`

Return type: boolean

```zenscript
4.enthalten(Daten als crafttweaker.api.data.IData);
4.enthalten("Anzeigen");
```

| Parameter | Type                                                   | Beschreibung                     |
| --------- | ------------------------------------------------------ | -------------------------------- |
| data      | [crafttweaker.api.data.IData](/vanilla/api/data/IData) | data to check if it is contained |


### copy

Makes a copy of this IData.

 IData is immutable by default, use this to create a proper copy of the object.

 Returns: `a copy of this IData.`

Rückgabetyp: [craftweaker.api.data.IData](/vanilla/api/data/IData)

```zenscript
4.copy();
```

### getId

Gets the ID of the internal NBT tag.

 Used to determine what NBT type is stored (in a list for example)

 Returns: `ID of the NBT tag that this data represents.`

Rückgabetyp: Byte

```zenscript
4.getId();
```

### getString

Gets the String representation of the internal INBT tag

 Returns: `String that represents the internal INBT of this IData.`

Return type: String

```zenscript
4.getString();
```


