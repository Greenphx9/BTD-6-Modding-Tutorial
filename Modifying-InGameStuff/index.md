# Modifying In-Game stuff

In this section of the tutorial, you will learn how to modify what happens in-game. There are a bunch of mod helper and Melonloader hooks. The most useful are: OnUpdate(), OnKeyDown(),
OnCashAdded().

You can use these hooks to change InGame settings, like adding cash, adding lives, subtracting cash, subtracting lives, popping all bloons, etc.

## Important/Useful/Regularly used 
- if(InGame.instance != null && InGame.instance.bridge != null) (makes the code only work while in-game)
- InGame.instance.AddCash(amount)
- InGame.instance.bridge.simulation.RemoveCash(cash, from(Simulation.CashType), cashIndex(0), source(Simulation.CashSource))
- InGame.instance.AddHealth(amount) && InGame.instance.AddMaxHealth(amount)
- InGame.instance.bridge.simulation.SetHealth(amount)
- InGame.instance.bridge.ClearBloons()
- InGame.instance.SellTower(TowerToSimulation tower) (You can get the tower from InGame.instance.GetAllTowerToSim())
- InGame.instance.bridge.ResetAbilityCooldowns(bool includeOwnedByOtherClients (coop))
## Code Examples

### Add Cash when F1 Pressed
```
        public override void OnKeyDown(KeyCode keyCode)
        {
            base.OnKeyDown(keyCode);
            if(keyCode == KeyCode.F1)
            {
                InGame.instance.AddCash(amount: 100);
            }
        }
```
### Remove Cash when F1 Pressed
```
        public override void OnKeyDown(KeyCode keyCode)
        {
            base.OnKeyDown(keyCode);
            if(keyCode == KeyCode.F1)
            {
                InGame.instance.bridge.simulation.RemoveCash(c: 100, Simulation.CashType.Normal, 0, Simulation.CashSource.Normal);
            }
        }
```
### Reset Abilities every frame
```
        public override void OnUpdate()
        {
            base.OnUpdate();
            if(InGame.instance != null && InGame.instance.bridge != null)
            {
                InGame.instance.bridge.ResetAbilityCooldowns(includeOwnedByOtherClients: false);
            }
        }
```
### Bonus end of round cash
```
        public override void OnRoundEnd()
        {
            base.OnRoundEnd();
            InGame.instance.AddCash(amount: 1000);
        }
```
