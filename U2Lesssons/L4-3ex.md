# Lesson 4-3 Exercise

In this Exercise we will be working on creating and placing tiles on a tilemap, creating rule tiles, and random tiles. Open up the "Lesson 3" scene.
## Exercise 4.3.1
---

Our first exercise will be to create a tile palette with some tiles. First, make sure your Tile Palette tab is opened. There should already be an "Example Palette" already there. Go to the **Assets>Sprite>TileSprites** folder and drag and drop some of the sprite to make tiles. 

1. Make sure that you attach a `TileMap Collider 2D` component onto Example (This will allow your tile map to have collision)
## Exercise 4.3.2
---

Next, we will create Rules tile for ground.

1. **First, go into the project folder, then right click inside, go to "Create>2D>Tiles>Rule Tiles".**
2. Name this tile "Ground Tile". Select the tile

3. The first option there should be a default sprite value. Set that to **platformPack_tile001**.
    1. Can also be other tiles that are similar, just remember to be consistent when adding sprites to make sure they match.

4. Leave "Default GameObject" to None and "Default Collider" to Sprite.

5. Go to the "Tiling Rules" list. When adding rules, think of these as "if-statements".

    1. Click the plus-sign and add empty 3 rules to make the tile react to other tiles.

    2. The first rule will be when the tile is not the top tile. This means there is at least another tile above this one.
        * In the gird, make sure the top center has a green arrow (click on it until an arrow pointing up appears).
        * For the sprite, choose **platformPack_tile004**.
        * All other settings can be the same.

    3. The second rule will be for a floating platform, so no tiles above or below it.
        * In the gird, make sure both the top center and bottom center have a red "X" (click on it until the "X" appears).
        * For the sprite, choose **platformPack_tile025**.

    4. The last rule will be for when it is the top tile, so no tiles above it.
        * In the gird, make sure the top center has a red X (click on it until a Red X appears).
        * For the sprite, choose **platformPack_tile001**.

6. Once completed, drag and drop the asset into the tile palette. With this, you will now be able to paint the ground without needing to switch.

## Exercise 4.3.3
---


For this next tile, we will create Random tile for wall.

1. Like the ground, create a rule tile, and name it "Wall Tile".

2. For the "Default Sprite", choose **platformPack_tile028**. All other defaults remain the same.

3. Instead of creating multiple rule, we will only need one.

4. For the single rule, change the `output` option to "Random". Since we will now use an array of random sprites, we will not need to set the sprite next to the gird.
    The `Noise` and `Shuffle` values can remain the same, though you are free to change them to your liking.

5. Set the `size` value to 7. This defines the number of sprites, which are:
    * **platformPack_tile007**
    * **platformPack_tile008**
    * **platformPack_tile019**
    * **platformPack_tile020**
    * **platformPack_tile028**
    * **platformPack_tile035**
    * **platformPack_tile041**

6. After you are finished with this, you can drag and drop the tile asset to the palette and start using it. 

## Exercise 4.3.4
---

Create a scene called "Level 1" and use the tiles the you have made. You can use non-tile sprites for decor or if there is a specific placement you want for the sprite.