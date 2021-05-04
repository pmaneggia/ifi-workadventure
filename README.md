# WorkAdventure Map Starter Kit

Beginning with the WorkAdventure starter kit to build your own map for [WorkAdventure](https://workadventu.re), a new project for the Praktikum in SS 2021.

Tutorial for the starter kit to be found at [https://workadventu.re/map-building](https://workadventu.re/map-building).

To use this map visit https://play.workadventu.re/_/global/pmaneggia.github.io/ifi-workadventure/map.json

## Map Rules
from [https://workadventu.re/map-building/wa-maps]{https://workadventu.re/map-building/wa-maps}

In order to design a map that will be readable by WorkAdventure, you will have to respect some constraints.

In particular, you will need to:

* set a start position for the players -> !!! this means having a layer called "start" with one nut zero position, which is the starting point (and can also define a tile) - my interpretation, not found in the tutorial !!!
* configure the "floor layer" (so that WorkAdventure can correctly display characters above the floor, but under the ceiling)
* eventually, you can place exits that link to other maps -> !!! more to say here !!!

A few things to notice:

* your map can have as many layers as you want
* your map MUST contain a layer named "floorLayer" of type "objectgroup" that represents the layer on which characters will be drawn. Every layer above the "floorLayer" will be displayed on top of the characters.
* the tilesets in your map MUST be embedded. You cannot refer to an external typeset in a TSX file. Click the "embed tileset" button in the tileset tab to embed tileset data.
* your map MUST be exported in JSON format. You need to use a recent version of Tiled to get JSON format export (1.3+)
* WorkAdventure doesn't support object layers and will ignore them
* If you are starting from a blank map, your map MUST be orthogonal and tiles size should be 32x32.

More things that I know so far:

* you can define some tiles as "silent" (value "s") -> no video conference get started there
* you can embed at certain position anything embeddable -> how to?

## BUILDING WALLS AND "COLLIDABLE" AREAS

By default, the characters can traverse any tiles. If you want to prevent your characeter from going through a tile (like a wall or a desktop), you must make this tile "collidable". You can do this by settings the collides property on a given tile.

To make a tile "collidable", you should:

1 select the relevant tileset and switch to "edit" mode
1 right click on a tile of the tileset to select it
1 on the left pane in the custom properties section, right click and select "Add properties":
1 Please add a collides property. The type of the property must be bool.
1 finally, check the checkbox for the collides property

## ENTRIES AND EXITS

https://workadventu.re/map-building/entry-exit