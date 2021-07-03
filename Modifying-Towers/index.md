### Modifying Towers

This part of the tutorial will teach you how to make basic tower modifications, like changing range, fire rate, etc. First of all, if your extending your main class with BloonsTD6Mod, you can simply type public override On(ModelToChange)Changed. The most important models are: TowerModel, AttackModel, WeaponModel and ProjectileModel. TowerModel controls tower name, the range you can see on the tower, tower upgrades, and much more. AttackModel contains the actual range, WeaponModels, Targetting, and others. Not as useful as TowerModel and WeaponModel. WeaponModel contains fire rate, emission (2 projectiles at once, 3, instant damage, etc), projectile throw position, and others. ProjectileModel is projectile display, pierce, radius, scale and other things.

If you look closely, you will notice that you arent editing TowerModel, AttackModel, etc but you are editing Tower, Attack, etc. You can get the model by doing Name.NameModel. For example: Tower.TowerModel. From there you can edit anything!

## Regularly edited:

### Tower Model
- Tower Display
- Tower Name
- Tower Upgrades
- Tower Range (visual)
- Tower Base ID (Tower Name is Tower Base ID (for example, DartMonkey) + tiers, so Triple Darts would be DartMonkey-030)
### Attack Model
- Attack Range
- Targeting (attack.attackModel.GetBehavior<Target(TargettingName)Model>())
### Weapon Model
- Weapon Rate (Rate with a capital R is the seconds)
- Projectile throw position (x, y and z)
- Weapon Emission (Commonly used emissions are Single Emission Model and Arc Emission Model)
### Projectile Model
- Projectile Pierce
- Projectile Radius (radius that can damage bloons)
- Projectile Scale (projectile display size)
- Projectile Size
- Projectile DamageModel (can be used to change projectile damage, do projectile.projectileModel.GetDamageModel())

For each of these models, you can do ```GetBehavior<T>()```, where T is the model. Common behaviors are Damage Model and Display Model.
        
## Code Examples
        
### Hypersonic Towers
```
        public override void OnWeaponModelChanged(Weapon weapon, Model newModel)
        {
            base.OnWeaponModelChanged(weapon, newModel);
            weapon.weaponModel.Rate = 0.001f;
        }
```
### Infinite Range
```
        public override void OnTowerModelChanged(Tower tower, Model newModel)
        {
            base.OnTowerModelChanged(tower, newModel);
            tower.towerModel.range = 1000f;
        }
        public override void OnAttackModelChanged(Attack attack, Model newModel)
        {
            base.OnAttackModelChanged(attack, newModel);
            attack.attackModel.range = 1000f;
        }
```
### Infinite Pierce
```
        public override void OnProjectileModelChanged(Projectile projectile, Model newModel)
        {
            base.OnProjectileModelChanged(projectile, newModel);
            projectile.projectileModel.pierce = 999999999f;
        }
```
### Infinite Lifespan
```
        public override void OnProjectileModelChanged(Projectile projectile, Model newModel)
        {
            base.OnProjectileModelChanged(projectile, newModel);
            if(projectile.projectileModel.HasBehavior<TravelStraitModel>())
            {
                projectile.projectileModel.GetBehavior<TravelStraitModel>().Lifespan = 5f;
            }
        }
```
### Infinite Damage
```
        public override void OnProjectileModelChanged(Projectile projectile, Model newModel)
        {
            base.OnProjectileModelChanged(projectile, newModel);
            if(projectile.projectileModel.HasBehavior<DamageModel>())
            {
                projectile.projectileModel.GetDamageModel().damage = 999999999f;
                projectile.projectileModel.GetDamageModel().maxDamage = 999999999f;
                projectile.projectileModel.GetDamageModel().CapDamage(999999999f);
            }
        }
```
