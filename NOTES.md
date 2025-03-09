# Misc. Notes

* 1 Stone Boulder produces 4 Stone Blocks
* 1 Ore Boulder produces 4 Bars of Primary Metal and 0-4 Bars of Secondary
  Metal.
* Use workshop profiles to limit production of goods to certain shops,
  especially the overloaded workshops like Farmers Workshops and Crafts Dwarf
  Shops.
* Use minecart quantum storage pits for food to make stockpiles that force
  dwarves to use certain ingrediants.  This can be combined with workshop
  profiles to cook off annoying ingrediants like Royal Jelly.
* Quick fort just relies on you selecting the tool in the UI now instead of using codes

# Workorder Notes

Dye conditions in work order are:

* Traits: dye
* Items: boxes and bags

I cannot figure out how to make it count stacks of dye.

# Hack Notes

## Custom Script
```
[DFHack]# reveal-des
```

Reveals designated tiles, useful for ignoring damp / warm stone cancellations.

## Paint Rough Wall
```
[DFHack]# tiletypes
tiletypes> paint sp normal
tiletypes> paint sh wall
tiletypes> paint m stone granite
tiletypes> run
tiletypes> q
```

Should see something like:

`Paint: NORMAL STONE WALL INORGANIC:GRANITE CLUSTER`

If it worked properly.  Messing up the material is the easiest thing to do.
The material needs to be all lower case.

## Filling Ponds
At the ground level -1:

1. set to normal wall
```
> paint special NORMAL
> paint shape WALL
> paint material SOIL
```
2. set to inside hidden
```
> paint hidden 1 
> paint skyview 0
```

3. Only replace ponds
```
> filter material POOL
```

4. Filter empty space left over after replacing pools
```
> filter m AIR
```

# Work Order Management

Dedicated sand collection can be accomplished by creating a glass workshop that
does not accept general work orders (in the workshop profile).  It can then be
given a workorder with conditions on number of items with the sand bearing
trait.  I have not reliably figured out conditions for empty cloth bags.


# Military

## Uniforms

The items must appear in this order in the uniform to be layer properly.

### Layout

| Item         | Material | Cost |
| ------------ | -------- | ----:|
| Mail Shirt   | Metal    | 2    |
| Breast Plate | Metal    | 3    |
| Cloak        | Leather  | 1    |
| Helm         | Metal    | 1    |
| Hood         | Leather  | 1    |
| Trousers     | Cloth    | 1    |
| Greaves      | Metal    | 2    |
| Gauntlets    | Metal    | 1    |
| Socks        | Cloth    | 1    |
| High Boots   | Metal    | 1    |
| Shield       | Wood     | 1    |
| Weapon       | Metal    | 1    |
| Backpack     | Leather  | 1    |
| Waterskin    | Leather  | 1    |

### Total Costs

| Material   | Total |
| ---------- | -----:|
| Metal Bars | 11    |
| Leather    | 4     |
| Cloth      | 2     |
| Logs       | 1     |


### Raw Steel Costs

| Material   | Total |
| ---------- | -----:|
| Logs       | 22    |
| Flux       | 22    |
| Iron Ore   |  6    |


# Building Notes

Notes about designs in fort-designs.xcf

Big Circle Wall Costs
---------------------
| Element       | Blocks | Stone |
| ------------- | ------:| -----:|
| Outter Wall   | 128    | 32    |
| Inner Wall    | 112    | 28    |
| Between Walls | 120    | 30    | 
| **Totals**    | 360    | 90    |

Main Stair Costs
----------------
| Element      | Blocks | Stone  |
| ------------ | ------:| ------:|
| Outter Wall  | 40     | 10     |
| Floors       | 61/60 †| 16/15 †|
| **Totals**   | 101    | 26     |

† Subract 1 block for "utility chute"
