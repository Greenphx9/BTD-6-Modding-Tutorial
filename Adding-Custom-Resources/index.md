# Adding Custom Textures and Sprites

This part of the tutorial will teach you how to add Custom textures and sprites.

## Steps
1. Add a png to your project. In Visual Studio you can right click either the project or a folder, press add, them existing item, then find a png you would like to add.
2. Right click the png file and press properties.
3. Change build action to: "Embedded Resource"
4. You're done!

You can use this png as a Sprite, Texture2D, or SpriteReference. If you want to use it in a Mod class, like ModUpgrade or ModTower, you can simply do Get(Sprite, Texture2D, or SpriteReference)(mod, "PNGNameWithoutExtension).
If you want to use it in any other class, do ModContent.Get(Sprite, Texture2D, or SpriteReference)<MainClass>("PNGNameWithoutExtension).
