---
author: "Flips-Admin"
title: "⚙️ PinGod - Machine and Game Configuration"
date: 2021-12-03T12:00:08+09:00
description: "Configuration for PinGod machine and global game variables"
draft: false
image: /images/pingod/pingod-logo.png
hideToc: false
enableToc: true
enableTocContent: false
author: HorsePin
authorEmoji: 🐎
categories:
- guides
- pingod
tags: 
- beginner
- coil
- lamp
- leds
- switch
---

---

## Machine Configuration

{{< img src="/images/pingod/pingod-basic-machineconfig.jpg" title="PinGod PinGodGame.tscn Scene" caption="" alt="" width="500px" position="center" >}}

---

### Machine Items

In the `PinGodGame.tscn` scenes inspector in Godot you can edit the machines `Coils, Switches, Lamps, Leds` from the interface but you can just as easily edit this file in text editor and add items there.

When the game is loaded the items will be added to the machine. They can be accessed inside the `Machine.cs` or use the Games helper methods with the item name.

{{< img src="/images/pingod/pingodgame-machine-items.jpg" title="Machine Items" caption="When adding from the UI select `String` and `Int` for the value." alt="" width="500px" position="center" >}}

** There are some defaults which would be on every machine that shouldn't be removed. `flippers, coin door, plunger_lane, tilts`

### Coils

#### Default Coils

Inside `game/PinGodGame.tscn` in a text editor, you can add them here if you find it faster than godot inspector.

```
_coils = {
"auto_plunger": 3,
"died": 0, //Sends a game dead coil (for simulators)
"disable_shows": 33,
"flippers": 2,
"lampshow_1": 34,
"lampshow_2": 35,
"mball_saucer": 4,
"trough": 1
}
```

---

### Lamps

#### Default Lamps

```
_lamps = {
}

```

---

### Leds

#### Default Leds

```
_leds = {
"shoot_again": 1
}

```

---

### Switches

Switch numbers added to the collection need an action in Godot to work. For example `sw27`. These can be found in the Godot `Input Map` in project settings.

These will be added automatically from your switches below, the only time you would make one manually is to assign a keyboard shortcut to it.

{{< img src="/images/pingod/godot-input-actions.jpg" title="Godot Machine Switches" caption="Switches need a Godot action, you can also assign keyboard for testing" alt="" width="500px" position="center" >}}

Below are the fefault switches for BasicGame. These were copied by opening the `PinGodGame.tscn` in a text editor, you can add them here if you find it faster than godot inspector.

```
_switches = {
"coin1": 1,
"coin2": 2,
"coin3": 3,
"down": 5,
"enter": 7,
"exit": 4,
"flipper_l": 11,
"flipper_r": 9,
"inlane_l": 22,
"inlane_r": 23,
"mball_saucer": 27,
"outlane_l": 21,
"outlane_r": 24,
"plunger_lane": 20,
"slam_tilt": 16,
"sling_l": 25,
"sling_r": 26,
"start": 19,
"tilt": 17,
"trough_1": 81,
"trough_2": 82,
"trough_3": 83,
"trough_4": 84,
"up": 6
}
```

---

### Ball Trough

Settings for the ball trough script. The default with the `BasicGame` is `4 switches` for `4 balls` but this can be changed to a single ball or more

- Trough Switches - An array of switch names that are in the trough to track and launch balls for the player
- Trough Solenoid - name of the `coil` that represents the `solenoid` which pulses balls from the trough
- Plunger Lane Switch - Name of switch for the trough to check a ball isn't already in shooter lane
- Auto Plunge Solenoid - name of the solenoid (if available in machine)

### Ball Search

• Enabled
• Ball Search coils to pulse (usually saucers, scoops not the trough)
• Search stop switches = Switches that stop the search
• Search wait time = Time to wait before pulsing coils

---

## Game Configuration

### Ball Save

- Ball Save Lamp = Name of lamp from lamp collection
- Ball Save Led  = Name of led from led collection
- Ball Save Seconds = Amount of default ball saving time
- Ball Save Multiball Seconds = Amount of default ball saving time
- Numbers of Balls to Save
- Early Save Switches = Collection of early save switches. Example: When ball save is on and player hits an outlane

---

## Visual Pinball Sync Configuration

- Write Machine States = On/Off
- Read Machine States = On/Off
- Write Machine States Delay = Value to delay writing states (default 10)

---