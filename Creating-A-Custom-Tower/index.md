# Creating a Custom Tower

In this part of the tutorial will teach you how to make a custom tower.

## Making The Tower

First, you must make sure your main class is extending from BloonsMod. Then, make a new class that extends ModTower. It will error saying you need to override some stuff.

### Stuff to add

- Name: Tower name without spaces or any special characters.
- Display name: Tower name with spaces and special characters.
- Tower set: Primary, Military, Magic or Support.
- Base Tower: Tower to copy from. Normally tower name without spaces. If you want to copy tiers, add a dash and then tower tiers. For example: DartMonkey-230.
- Cost - Tower cost as an int
- Description: Tower description
- Top/Middle/Bottom path upgrades: How many upgrades it has for that path. You have to make ModUpgrades for upgrades, so if you want set it to 0.
- Modify Base Tower Model: Changes to the base tower
- Icon: Png without extension. <a href="https://greenphx9.github.io/BTD-6-Modding-Tutorial/Adding-Custom-Images/">Click here for more info.</a>
- Portrait: Png without extension. <a href="https://greenphx9.github.io/BTD-6-Modding-Tutorial/Adding-Custom-Images/">Click here for more info.</a>
- Use 2D Model: Set to true if you want to use a 2d texture.
- Get 2D Texture: Return a png without extension. <a href="https://greenphx9.github.io/BTD-6-Modding-Tutorial/Adding-Custom-Images/">Click here for more info.</a>
- Pixels Per Unit: More is smaller 2d tower, less is bigger 2d tower.

If you do it all correctly, it should work!
