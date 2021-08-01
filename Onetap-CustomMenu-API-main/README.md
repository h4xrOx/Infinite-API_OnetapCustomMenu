<a name="-1"></a>

# Infinite.js API

**In Progress** - Feel free to open an Issue if you need Clarrification or have a suggestion 



|Contents|
|--------|
|[Menu](#0)|
|[Configs](#1)|
|[Callbacks](#2)|
|[Events](#3)|
|[Elements](#4)|

---

## <a name="0"></a>Menu

**All menu Element must be called after the API**

[ **Label** ]
Syntax: CreateLabel(label, row)

**Creates** a Label with the specified Label and Row 

```java
CreateLabel("TestLabel", 0)
```

[ **Checkbox** ]
Syntax: CreateCheckbox(label, defaultvalue, row)

**Creates** a Checkbox with the specified Label, Default Value, and Row 

```java
CreateCheckbox("Infinite API", false, 0);
function Checkbox()
{
    if(GetMenuValue("Infinite API"))
    {
        Cheat.Print("Checkbox Enabled");
    }
}

Global.RegisterCallback("Draw", "Checkbox");
```

[ **Get Value** ]
Syntax: GetMenuValue(label)

**Returns** the Value of a Menu Element

```java
CreateCheckbox("Menu Element", false, 0);
function Checkbox()
{
    Cheat.Print("The value of the element is: " + GetMenuValue("Menu Element"));
  
}

Global.RegisterCallback("Draw", "Checkbox");
```

[ **Set Value** ]
Syntax: SetMenuValue(label, value)

**Sets** the Value of a Menu Element

```java
CreateCheckbox("Menu Element", false, 0);
function Checkbox()
{
    SetMenuValue("Menu Element", true);
}

Global.RegisterCallback("Draw", "Checkbox");
```

[ **Set Menu Size** ]
Syntax: SetMenuSize(width, height)

**Sets** the size of the Menu

```java
SetMenuSize(500, 500)
```


[ **Get Menu Size** ]
Syntax: GetMenuSize()

**Returns** the size of the Menu

```java
function GetMenu()
{
    Cheat.Print("Menu Width is " + GetMenuSize()[0] + ", Menu Height is " + GetMenuSize()[1] + "\n")
}

Callback(0, GetMenu);
```


[ **Set Menu Location** ]
Syntax: SetMenuLocation(x, y)

**Sets** the location of the Menu

```java
SetMenuLocation(800,800)
```


[ **Get Menu Location** ]
Syntax: GetMenuLocation()

**returns** the location of the Menu
```java
function GetMenu()
{
    Cheat.Print("Menu X is " + GetMenuLocation()[0] + ", Menu Y is " + GetMenuLocation()[1] + "\n")
}

Callback(0, GetMenu);
```

[ **Set Menu Movable** ]
Syntax: MovableMenu(value)

**Sets** if the Menu is Movable

```java
MovableMenu(false) //cannot move
MovableMenu(true) //can move 
```

[back to Contents](#-1)

---

## <a name="1"></a>Configs
[ **Load Script from Config** ]
Syntax: LoadFromConfig() [ ** must be called at the end of a script** ]

**Loads and Updates** all menu elements from the loaded config

```java
CreateCheckbox("Infinite API", false, 0);

function onDraw()
{



}

Global.RegisterCallback("Draw", "onDraw");


//at end of script
LoadFromConfig()
```

[back to Contents](#-1)

---

## <a name="2"></a>Callbacks

[ **Optimized Callbacks** ]
Syntax: Callback(type, function); [ ** Function to be Invoked not as a string** ]

**Callbacks** the selected function


```java
CreateCheckbox("Draw Rectangle", false, 0);

function onDraw()
{
    if(!GetMenuValue("Draw Rectangle")) { return; }

    Render.Rect(100, 100, 150, 150, [255, 0, 0, 255]);
}

Callback(0, onDraw)

```

[ **Callback Types** ]
```java

0 - Draw
1 - CreateMove

```

[back to Contents](#-1)

---

## <a name="3"></a>Events

[ **Get Event Value** ]
Syntax: [ElementType].GetEvent(EventType)

**Returns** the Value of the Event
```java


function onDraw()
{
    if(menu.GetEvent(Events.MouseDown))
        Cheat.Print("Mouse Down \n")
}

Callback(0, onDraw)

```

[ **Event Types** ]
```java

Events.MouseDown - When Left mouse button is Down
Events.MouseUp - When Left mouse button is Up

```

[back to Contents](#-1)

---


## <a name="4"></a>Elements

[ **Elements** ]
```java

checkbox
menu 

```

[back to Contents](#-1)

---
