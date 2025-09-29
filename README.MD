# Example: Creating a UI with SynapticX Hub Library

Below is a demonstration of how to create a custom UI using the SynapticX Hub Library. This example shows how to initialize the library, add a tab, sections, and common UI elements.

---

## Step 1: Initialize the Library

```lua
local Library = require(path_to_pasted_txt) -- Replace with actual require or loadstring!

local window = Library.new({
    Title = "Example Hub",
    Description = "Demonstration of UI Elements",
    Keybind = Enum.KeyCode.RightControl,
    Logo = "http://www.roblox.com/asset/?id=18810965406",
    Size = UDim2.new(0.1, 445, 0.1, 315),
})
```

---

## Step 2: Create a Tab

```lua
local tab = window:NewTab({
    Title = "Main",
    Description = "Main Features Tab",
    Icon = "rbxassetid://7733964640",
})
```

---

## Step 3: Add Sections

```lua
local leftSection = tab:NewSection({
    Title = "Controls",
    Position = "Left",
    Icon = "rbxassetid://7733993369",
})

local rightSection = tab:NewSection({
    Title = "Settings",
    Position = "Right",
    Icon = "rbxassetid://7733964640",
})
```

---

## Step 4: Add UI Elements

### Toggle

```lua
leftSection:NewToggle({
    Title = "Enable Feature",
    Default = false,
    Callback = function(state)
        print("Feature enabled:", state)
    end,
})
```

### Button

```lua
leftSection:NewButton({
    Title = "Run Action",
    Callback = function()
        print("Action executed!")
    end,
})
```

### Slider

```lua
rightSection:NewSlider({
    Title = "Volume",
    Min = 0,
    Max = 100,
    Default = 50,
    Callback = function(value)
        print("Volume:", value)
    end,
})
```

### Dropdown

```lua
rightSection:NewDropdown({
    Title = "Mode",
    Data = {"Easy", "Normal", "Hard"},
    Default = "Normal",
    Callback = function(selected)
        print("Selected Mode:", selected)
    end,
})
```

### Keybind

```lua
rightSection:NewKeybind({
    Title = "Special Key",
    Default = Enum.KeyCode.Q,
    Callback = function(key)
        print("Keybind set to:", key.Name)
    end,
})
```

### Textbox

```lua
rightSection:NewTextbox({
    Title = "Input Code",
    Default = "",
    FileType = "Lua",
    Callback = function(text)
        print("Textbox input:", text)
    end,
})
```

---

## Step 5: Show a Notification

```lua
local notify = Library.Notification()
notify.new({
    Title = "Welcome!",
    Description = "UI Loaded Successfully.",
    Duration = 3,
    Icon = "rbxassetid://7733993369",
})
```

---

## Step 6: Use the Console

```lua
local console = Library:Console()
console:print("Hello from the Example Hub!")
```

---

**Tips:**  
- Use `window.Keybind` to toggle the UI.
- Add more tabs/sections or customize elements as needed.

---
