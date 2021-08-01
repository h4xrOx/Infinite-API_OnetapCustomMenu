# Infinite-API
https://api.github.com/repos/estkk/Infinite-API

<a name="-1"></a>

# Infinite JavaScript API

**Important** - Feel free to open an Issue if you have a suggestion or need clarrification.



|Contents|
|--------|
|[Menu](#0)|
|[Tab](#1)|
|[Convar](#2)|
|[Netvar](#3)|
|[Classes](#4)|
|[Entity](#5)|
|[Player](#6)|
|[Material](#7)|
|[Event](#8)|
|[Callback](#9)|
|[Memory](#10)|
|[Trace](#11)|
|[Render](#12)|
|[Extra](#13)|
|[Local](#14)|

---

# <a name="0"></a>Menu
---

## Menu.CreateLabel()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Tab | string | Cheat Tabs |
| Child | string | Child of a Tab |
| Label Text | string | Labels Text |
| Help Text | string | Labels Help Text |


```java
Menu.CreateLabel("Configs", "Scripting", "Label", "This is a label")
```

## Menu.CreateSwitch()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Tab | string | Cheat Tabs |
| Child | string | Child of a Tab |
| Label | string | Switch's Label |
| Help Text | string | Switch's Help Text |
| Bindable | bool | Bindable Switch |

```java
Menu.CreateSwitch("Configs", "Scripting", "Switch", "This is a Switch", true)
```

## Menu.CreateCombo()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Tab | string | Cheat Tabs |
| Child | string | Child of a Tab |
| Label | string | Combo Label |
| Elements | string array | Combo elements |
| Help Text | string | Combo Help Text |

```java
Menu.CreateCombo("Configs", "Scripting", "Combobox", ["Element 1", "Element 2"], "This is a combobox")
```

## Menu.CreateMultiCombo()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Tab | string | Cheat Tabs |
| Child | string | Child of a Tab |
| Switch Text | string | MultiCombo Label |
| Elements | string array | MultiCombo elements |
| Help Text | string | MultiCombo Help Text |

```java
Menu.CreateMultiCombo("Configs", "Scripting", "MultiCombobox", ["Element 1", "Element 2"], "This is a multicombobox")
```

## Menu.CreateSlider()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Tab | string | Cheat Tabs |
| Child | string | Child of a Tab |
| Label | string | Slider Label |
| Range | int array | Min and Max |
| Help Text | string | Slider Help Text |

```java
Menu.CreateSlider("Configs", "Scripting", "Slider", [0, 100], "This is a slider from 0 to 100")
```

## Menu.CreateBind()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Tab | string | Cheat Tabs |
| Child | string | Child of a Tab |
| Label | string | Bind Label |
| Help Text | string | Slider Help Text |

```java
Menu.CreateBind("Configs", "Scripting", "Keybind", "This is a keybind")
```

## Menu.CreateList()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Tab | string | Cheat Tabs |
| Child | string | Child of a Tab |
| Label | string | Listbox Label |
| Elements | string array | Listbox element |
| Help Text | string | Listbox Help Text |

```java
Menu.CreateList("Configs", "Scripting", "Listbox", ["Element 1", "Element 2", "Element 3"], "This is a keybind")
```

## Menu.CreateButton()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Tab | string | Cheat Tabs |
| Child | string | Child of a Tab |
| Label | string | Button Label |
| Output | function | function ran on click |

```java

function KeyPress()
{

}

Menu.CreateButton("Configs", "Scripting", "Listbox", KeyPress)
```

## Menu.SetSize()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Size | int array | Width and Height |

```java
Menu.SetSize([100,100])
```


## Menu.GetSize()


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| Size | int array | Width and Height |

```java
size = Menu.GetSize()
```


## Menu.SetLocation()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Location | int array | X and Y |

```java
Menu.SetLocation([100,100])
```


## Menu.GetLocation()


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| Location | int array | X and Y |


```java
location = Menu.GetLocation()
```

## Menu.GetValue()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Tab | string | Cheat Tabs |
| Child | string | Child of a Tab |
| Name | string | label of element |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| Value | any | Value of the element |

```java
Menu.CreateSwitch("Configs", "Scripting", "Switch", "This is a Switch", true)
location = Menu.GetValue("Configs", "Scripting", "Switch")
```

## Menu.SetValue()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Tab | string | Cheat Tabs |
| Child | string | Child of a Tab |
| Name | string | label of element |
| Value | any | label of element |


```java
Menu.CreateSwitch("Configs", "Scripting", "Switch", "This is a Switch", true)
Menu.SetValue("Configs", "Scripting", "Switch", true)
```

## Menu.SetVisibility()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Tab | string | Cheat Tabs |
| Child | string | Child of a Tab |
| Name | string | label of element |
| Visible | bool | visibility |


```java
Menu.CreateSwitch("Configs", "Scripting", "Switch", "This is a Switch", true)
Menu.SetVisibility("Configs", "Scripting", "Switch", 0)
```

## Menu.GetBind()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Tab | string | Cheat Tabs |
| Child | string | Child of a Tab |
| Name | string | label of bind |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| Bind | array | Bind info |

### Bind Info:

| Name | Type | Description |
| :--- | :--- | :--- |
| Active | bool | is bind active |
| Type | int | bind type |

```java
Menu.CreateBind("Configs", "Scripting", "Keybind", "This is a keybind")
bindinfo = Menu.GetBind("Configs", "Scripting", "Keybind")
Event.Log("bind is " + bindinfo[0] + " bind type is " + bindinfo[1])
```

## Menu.Update()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Element | function | Element to Update |


```java
Menu.CreateSwitch("Configs", "Scripting", "Switch", "This is a Switch", true)
Menu.Update(Menu.CreateSwitch("Configs", "Scripting", "Switch", "This switch has new Info", true))
```


[back to Contents](#-1)
---
# <a name="1"></a>Tab
---

## Tab.Create()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Tab | string | Tab Name |


```java
Tab.Create("New Rage")
```


## Tab.CreateChild()


### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Tab | string | Tab Name |


```java
Tab.Create("New Rage")
Tab.CreateChild("Rage Child")
```


[back to Contents](#-1)
---
# <a name="2"></a>Convar
---

## Convar.Get()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Name | string | Convar Name |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| Value | any | Convar's Value |


```java
Convar.Get("r_aspectratio")
```

## Convar.Set()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Name | string | Convar Name |
| Value | any | Convar Value |


```java
Convar.Get("r_aspectratio", 1.33)
```

[back to Contents](#-1)
---
# <a name="3"></a> Netvar

## Netvar.GetOffset()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Table | string | Table |
| Name | string | Name |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| Value | any | offset value |


```java
Netvar.GetOffset("DT_BaseEntity", "m_vecMins")
```

## Netvar.SetProp()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |
| Table | string | Prop Table |
| Name | string | Prop Name |
| Value | any | New Value |

```java
local = Local.GetPlayer()
Netvar.SetProp(local, "CBasePlayer", "m_flPoseParameter", [0,0,1])
```

## Netvar.GetProp()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |
| Table | string | Prop Table |
| Name | string | Prop Name |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| Value | any | Property Value |


```java
local = Local.GetPlayer()
pos = Netvar.GetProp(local, "CBasePlayer", "m_flPoseParameter")
```


[back to Contents](#-1)
---
# <a name="4"></a>Classes
---

# Global Variables

## Classes.GlobalVariables()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| index | int | variable Index |

### Variables:

| Name | Type | Description |
| :--- | :--- | :--- |
| realtime | float | absolute time |
| fps | int | returns frames per second |
| tickcount | int | returns tickcount |
| tick interval | int | intervals per tick |

```java
fps = Classes.GlobalVariables(2)
```

# CBaseWeapon

## Weapon.GetActiveWeapon()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| Weapon | weapon | Active Weapon |


```java
local = Local.GetPlayer()
activeweapon = Weapon.GetActiveWeapon(local)
```

## Weapon.IsGrenade()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| weapon | weapon | weapon |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| grenade | bool | is grenade |


```java
local = Local.GetPlayer()
activeweapon = Weapon.GetActiveWeapon(local)
isgrenade = Weapon.IsGrenade(activeweapon)
```

## Weapon.IsKnife()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| weapon | weapon | weapon |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| Knife | bool | is knife |


```java
local = Local.GetPlayer()
activeweapon = Weapon.GetActiveWeapon(local)
isknife = Weapon.IsKnife(activeweapon)
```

## Weapon.GetSpread()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| weapon | weapon | weapon |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| spread | int | weapon spread |


```java
local = Local.GetPlayer()
activeweapon = Weapon.GetActiveWeapon(local)
spread = Weapon.GetSpread(activeweapon)
```

## Weapon.GetInnacuracy()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| weapon | weapon | weapon |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| innacuracy | int | weapon innacuracy |


```java
local = Local.GetPlayer()
activeweapon = Weapon.GetActiveWeapon(local)
innacuracy = Weapon.GetInnacuracy(activeweapon)
```

## Weapon.GetWeaponSpeed()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| weapon | weapon | weapon |
| alt | bool | alt speed |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| speed | int | velocity |


```java
local = Local.GetPlayer()
activeweapon = Weapon.GetActiveWeapon(local)
speed = Weapon.GetWeaponSpeed(activeweapon, false)
scopedspeed = Weapon.GetWeaponSpeed(activeweapon, true)
```

## Weapon.GetClassID()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| weapon | weapon | weapon |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| id | int | class ID |


```java
local = Local.GetPlayer()
activeweapon = Weapon.GetActiveWeapon(local)
classid = Weapon.GetClassID(activeweapon)
```

## Weapon.GetWeaponID()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| weapon | weapon | weapon |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| weaponID | int | weapon's ID |


```java
local = Local.GetPlayer()
activeweapon = Weapon.GetActiveWeapon(local)
id = Weapon.GetWeaponID(activeweapon)
if(id == 7)
{
  Event.Log("your weapon is a AK47")
}
```

## Weapon.GetAmmo()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| player | entity | player |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| ammo | int | ammount of bullets |


```java
local = Local.GetPlayer()
ammo = Weapon.GetAmmo(local)
```

## Weapon.GetMaxAmmo()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| weapon | weapon | weapon |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| max ammo | int | max ammount of ammo |


```java
local = Local.GetPlayer()
activeweapon = Weapon.GetActiveWeapon(local)
max ammo = Weapon.GetMaxAmmo(activeweapon)
```

[back to Contents](#-1)
---
# <a name="5"></a>Entity
---

## Entity.GetList()

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| List | entity array | Entity list |


```java
List = Entity.GetList()
```

## Entity.GetEnemies()


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| List | entity array | Enemies |


```java
Enemies = Entity.GetEnemies()
```

## Entity.IsDormant()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| dormancy | bool | is dormant |


```java
dormancy = Entity.IsDormant(Entity.GetList()[4])
```

## Entity.IsBot()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| bot | bool | is bot |


```java
bot = Entity.IsBot(Local.GetPlayer())
```

## Entity.GetName()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| name | string | name |


```java
name = Entity.GetName(Local.GetPlayer())
```

## Entity.GetFromClassID()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| class id | int | class id |


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |


```java
Entity.GetFromClassID(128)
```

## Entity.GetClassID()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| class id | int | id |


```java
cid = Entity.GetClassID(Local.GetPlayer())
```

## Entity.IsAlive()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| alive | bool | is alive |


```java
alive = Entity.IsAlive(Local.GetPlayer())
```

## Entity.GetFromUserID()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| id | int | userid |


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |


```java
bot = Entity.GetFromUserID(userid)
```

## Entity.GetSteamID()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| steam id | string | steam id |


```java
steam = Entity.GetSteamID(Local.GetPlayer())
```

## Entity.GetOrigin()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| location | vec3d | Origin |


```java
origin = Entity.GetOrigin(Local.GetPlayer())
```

## Entity.GetBoundingBox()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| box | Vec2D | RenderBox |


```java
bb = Entity.GetBoundingBox(Local.GetPlayer())
```

## Entity.OverrideMaterial()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |
| material | material | material |


```java
l = Local.GetPlayer()
Entity.OverrideMaterial(i, material)
```
[back to Contents](#-1)
---
# <a name="6"></a>Player

## Player.GetPicture()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| steamid | int | player steam id |


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| picture | picture | picture |


```java
profile = Player.GetPicture(Entity.GetSteamID(Local.GetPlayer()))
```

## Player.GetMatrix()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| maxtrix | int array | maxtrix |


```java
maxtrix = Player.GetMatrix(Local.GetPlayer())
```

## Player.GetAnim()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| anim | int | anim |


```java
maxtrix = Player.GetAnim(Local.GetPlayer())
```

## Player.GetDrawInfo()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity | entity | entity |


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| DrawInfo_t | int array | drawinfo |


```java
maxtrix = Player.GetDrawInfo(Local.GetPlayer())
```



## Player.RenderModel()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| modelname | modelname | modelname |
| drawinfo | int array | drawinfo |
| matrix | int array | matrix |
| animation | animation | animation |
| material | material | material |

**leave material blank if none**

```java
Player.RenderModel("Special Agent Ava", drawinfo_t, hitchamsmatrx, playeranim, glowchams)
```



[back to Contents](#-1)
---
# <a name="7"></a>Material
---

## Material.Refresh()

**reloads materials**

```java
Material.Refresh()
```


## Material.Create()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| name | string | materialname |


```java
Material.Create("Glow")
```


## Material.GetIndex()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| name | string | materialname |


### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| index | int | material index |


```java
Material.GetIndex("Glow")
```

## Material.Update()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Index | int | material index |
| keyname | string | key name |
| keyvalue | string | keyvalue |

**does not refresh the material**

```java
Material.Update(Material.Get("Glow"), "$baseTexture", "vgui/white")
```

[back to Contents](#-1)
---
# <a name="14"></a>Local
---

## Local.SetName()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| name | string | new name |


```java
Local.SetName("Infinite.tech P")
```

## Local.SetClantag()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| name | string | clantag name |
| clantag | string | clantag on scoreboard |

```java
Local.SetClantag("Best Cheat Infinite", "Infinite.tech")
```

## Local.GetPlayer()

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| player | entity | local player |

```java
Local.GetPlayer()
```

## Local.GetLatency()

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| latency | int | ping |

```java
Local.GetLatency()
```

## Local.GetViewAngles()

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| viewangles | int array | ping |

```java
Local.GetViewAngles()
```

## Local.SetViewAngles()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| viewangles | int array | ping |

```java
Local.SetViewAngles([50,50])
```

[back to Contents](#-1)
---
# <a name="9"></a>Event
---

## Event.Log()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| input | string | string to log |

```java
Event.Log("hi")
```

[back to Contents](#-1)
---
# <a name="8"></a>Callback
---

## Callback.Add()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| callback | string | callback name |
| callbackee | function | function to callback |

```java
function OnCreateMove()
{


}

Callback.Add("CreateMove", OnCreateMove)
```

[back to Contents](#-1)
---
# <a name="10"></a>Memory
---


## Memory.Enable()

```java
function memory()
{
  Animstate = Player.GetAnim(Local.GetPlayer())
  Velocity = Memory.Read(Animstate + 0x114)
}

Memory.Enable()

Callback.Add("Memory", memory)
```

## Memory.Read()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| location | int | pointer |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| memory | any | value in memory |


```java
function memory()
{
  Animstate = Player.GetAnim(Local.GetPlayer())
  Velocity = Memory.Read(Animstate + 0x114)
}

Memory.Enable()

Callback.Add("Memory", memory)
```

## Memory.Write()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| location | int | pointer |
| value | any | new value |

```java
function memory()
{
  Animstate = Player.GetAnim(Local.GetPlayer())
  Memory.Write(Animstate + 0x114, 100)
}

Memory.Enable()

Callback.Add("Memory", memory)
```

## Memory.GetSignature()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| handle | int | handle |
| signature | string | signature |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| pointer | int | pointer |

```java
function memory()
{
  Memory.GetSignature(handle, signature)
}

Memory.Enable()

Callback.Add("Memory", memory)
```

## Memory.GetHandle()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| dll name | string | handle name |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| handle | int | handle |

```java
function memory()
{
  Memory.GetHandle("engine.dll")
}

Memory.Enable()

Callback.Add("Memory", memory)
```

[back to Contents](#-1)
---
# <a name="11"></a>Trace
---

## Trace.Line()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| start | vector | line start |
| end | vector | line end |
| skipped entity | entity | skip entity |
| mask | int | mask |
| type | int | line type |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| TraceInfo_t | int array | result |

### TraceInfo_t:

| Name | Type | Description |
| :--- | :--- | :--- |
| entity index | entity | entity |
| fraction | int | fraction result |


### Fraction:

| Name | Value | Description |
| :--- | :--- | :--- |
| Hit | 0.1 | Hit Something |
| Hit | 0.5 | Hit half way |
| Clear | 1 | No Hit |

### TraceType_t:

| Name | Value | Description |
| :--- | :--- | :--- |
| TRACE_EVERYTHING | 0 | trace all |
| TRACE_WORLD | 1 | world only |
| TRACE_ENTITY | 2 | entities only |

### Masks: 

```
        CONTENTS_SOLID                    0x1
        CONTENTS_WINDOW                       0x2
        CONTENTS_AUX                      0x4
        CONTENTS_GRATE                      0x8
        CONTENTS_SLIME                      0x10
        CONTENTS_WATER                      0x20
        CONTENTS_BLOCKLOS                  0x40
        CONTENTS_OPAQUE                      0x80
        CONTENTS_TESTFOGVOLUME              0x100
        CONTENTS_UNUSED                      0x200
        CONTENTS_BLOCKLIGHT                  0x400
        CONTENTS_TEAM1                      0x800
        CONTENTS_TEAM2                      0x1000
        CONTENTS_IGNORE_NODRAW_OPAQUE     0x2000
        CONTENTS_MOVEABLE                  0x4000
        CONTENTS_AREAPORTAL                  0x8000
        CONTENTS_PLAYERCLIP                  0x10000
        CONTENTS_MONSTERCLIP              0x20000
        CONTENTS_ORIGIN                      0x1000000
        CONTENTS_MONSTER                  0x2000000
        CONTENTS_DEBRIS                      0x4000000
        CONTENTS_DETAIL                      0x8000000
        CONTENTS_TRANSLUCENT              0x10000000
        CONTENTS_LADDER                      0x20000000
        CONTENTS_HITBOX                      0x40000000
```

```java
info = Trace.Line(Start, End, 0, 0x1, 1);
```

[back to Contents](#-1)
---
# <a name="12"></a>Render
---

## Render.Circle()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| location | vec2 | location |
| radius | int | radius |
| color | vec3 | color |
| thickness | int | thickness |

```java
Render.Circle([100,100], 30, [255,255,255,255], 4)
```

## Render.CircleFilled()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| location | vec2 | location |
| radius | int | radius |
| color | vec3 | color |

```java
Render.Circle([100,100], 30, [255,255,255,255])
```


## Render.String()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| location | vec2 | location |
| text | string | text |
| color | vec3 | color |
| font | font | font |

```java
font = Render.CreateFont("CoolFont.ttf")
Render.String([100,100],"hi",[255,255,255,255],font)
```

## Render.CreateFont()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| location | vec2 | location |
| text | string | text |
| color | vec3 | color |
| font | font | font |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| font | handle | font |

```java
font = Render.CreateFont("CoolFont.ttf")
Render.String([100,100],"hi",[255,255,255,255],font)
```



## Render.Rectangle()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| location | vec2 | location |
| wh | vec2 | width and height |
| color | vec3 | color |
| thickness | int | thickness |

```java
Render.Circle([100,100], [50,50], [255,255,255,255], 4)
```

## Render.RectangleFilled()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| location | vec2 | location |
| wh | vec2 | width and height |
| color | vec3 | color |

```java
Render.Circle([100,100], [50,50], [255,255,255,255])
```


## Render.Texture()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| Shape | function | Shape of texture |
| texture | text | texture |

```java
pfp = Player.GetPicture(Entity.GetSteamID(Local.GetPlayer()))
Render.Texture(Render.RectangleFilled([100,100],[100,100],[255,255,255,255]), pfp)
```

## Render.CreateTexture()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| directory | string | location |

**Supports PNG and JPEG only**

```java
picture = Render.CreateTexture("C:\Textures\picture.png")
```

## Render.WorldToScreen()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| vector | vec3 | location |

### Returns:

| Name | Type | Description |
| :--- | :--- | :--- |
| vector | vec2 | location |

```java
world = Entity.GetOrigin(Local.GetPlayer())
screen = Render.WorldToScreen(world)
```


[back to Contents](#-1)
---
# <a name="13"></a>Extras
---

## Doubletap.OverrideShift()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| shift | int | doubletap shift |

**Clamped to processticks - 2**

```java
Doubletap.OverrideShift(16)
```

## Doubletap.OverrideTolerance()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| shift | int | doubletap tolerance |

**Clamped to 2**

```java
Doubletap.OverrideTolerance(1)
```

## Doubletap.Teleport()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| enable | bool | doubletap teleport |

```java
Doubletap.Teleport(true)
```

## Processing.OverrideProcessedTicks()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| shift | int | processed ticks |

```java
Processing.OverrideProcessedTicks(22)
Doubletap.OverrideTolerance(20)
```

## Antiaim.OverrideDesync()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| desync | int array | real fake and lowerbody |

```java
Antiaim.OverrideDesync([-20,0,120]) //-20 real, 0 fakem 120 lowerbody
```

## Antiaim.OverrideYaw()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| yaw | int | yaw |

```java
Antiaim.OverrideYaw(-180)
```

## Antiaim.OverrideDirection()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| inverted | bool | is inverted |

```java
Antiaim.OverrideDirection(true)
```

## Resolver.Override()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| overriden | bool | is overriden |

```java
Resolver.Override(true)
```

## Resolver.SetGoalFeetYaw()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| curplayer | entity | player |
| goalfeetyaw | int | new goalfeetyaw |

```java
Resolver.Override(true)
e = Players.GetList()
Resolver.SetGoalFeetYaw(e[3], -40)
```

## Resolver.GetGoalFeetYaw()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| curplayer | entity | player |

```java
Resolver.Override(true)
Resolver.SetGoalFeetYaw(e[3], Resolver.SetGoalFeetYaw(e[3]))
```

## Ragebot.ForceSafety()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| curplayer | entity | player |

```java
Ragebot.ForceSafety(player)
```

## Ragebot.ForceBaim()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| curplayer | entity | player |

```java
Ragebot.ForceBaim(player)
```

## Ragebot.ForceHitbox()

### Parameters:

| Name | Type | Description |
| :--- | :--- | :--- |
| curplayer | entity | player |
| hitbox | vector | hitboxes |

```java
Ragebot.ForceHitbox(player, [0])
```



[back to Contents](#-1)
---

