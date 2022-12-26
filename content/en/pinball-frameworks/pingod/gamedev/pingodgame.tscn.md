---
author: "Flips-Admin"
title: "🎬 PinGod - Scenes: PinGodGame.tscn"
date: 2021-12-03T12:00:09+09:00
description: "More about the PinGogGame scene"
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
---

---

## Scene Information

This scene is autoloaded with a game and you should add this scene as a favorite in Godots favorites scene tree for quicker access.

`game/PinGodGame.tscn`

{{< img src="/images/pingod/godot-pingodgame-tscn.jpg" title="Adding a favorite in Godot" caption="This gives you a quick way of getting to the main variables in the game" alt="" width="500px" position="center" >}}

Switches and Options are mentioned in the [Machine Configuration](/en/pinball-frameworks/pingod/gamedev/machine-items/#machine-items)

---

## Debug Display Overlays

### Lamp Overlay Enabled

This enables the `LampMatrix` in the DevOverlays. Options are available on the `LampMatrix` to change coloumns and count.

`addons\PinGodGame\Overlays\Lamps\LampMatrix.tscn`

### Switch Overlay Enabled

This enables the `SwitchOverlay` in the DevOverlays. Options are available on the `SwitchOverlay` to change coloumns.

`addons\PinGodGame\Settings\SwitchOverlay.tscn`

Switches can be clicked on screen.


---
