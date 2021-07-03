# Welcome to Greenphx's guide to Modding Bloons TD 6!

On this page you will learn how to create Bloons TD 6 mods. Its not hard to make so lets get started!

## Requirements
- Basic C# Knowledge
- Melonloader 0.3 installed, along with Bloons TD 6 Mod Helper. Guide to that here: https://hemisemidemipresent.github.io/btd6-modding-tutorial/
- Any C# IDE
-.Net Framework

## Making a basic mod that launches.

Create a new .NET Framework Class Library. Reference everything inside MelonLoader/Managed, MelonLoader/MelonLoader.dll, and Mods/BloonsTD6 Mod Helper.dll. Make your main class (Class1) either extend BloonsMod or BloonsTD6Mod. You will need to import those two. Above the namespace, add these 2 lines of code:

```
[assembly: MelonInfo(typeof(NAMESPACE.CLASS), "Mod Name", "1.0.0", "Your Name")]
[assembly: MelonGame("Ninja Kiwi", "BloonsTD6")]
```
After that, add this code:
```
        public override void OnApplicationStart()
        {
            base.OnApplicationStart();
            MelonLogger.Msg("Mod Name Loaded");
        }
```
Then compile your code, add it to the Mods folder, and it should in the console, it should say: "Mod Name Loaded". If it does, congratulations, you made your first mod! If you did it correctly, you console should also look similar to this:
![Console](https://github.com/Greenphx9/BTD-6-Modding-Tutorial/raw/gh-pages/ConsoleExample1.png)

## Harmony Patching

Harmony Patching is a very important part of modding. More info here: https://melonwiki.xyz/#/modders/patching

## Modifiying....

<a href="https://greenphx9.github.io/BTD-6-Modding-Tutorial/Modifying-Towers/">Towers</a>

<a href="https://greenphx9.github.io/BTD-6-Modding-Tutorial/Modifying-InGameStuff/">In Game</a>
