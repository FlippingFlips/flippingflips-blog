---
author: "Flips-Admin"
title: "🎬 PinGod - Scenes: MainScene.tscn"
date: 2021-12-03T12:00:10+09:00
description: "More about the Main scene"
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
- scenes
---

---

## Scene Information

This scene is the first to be loaded as a display. This scene is never removed from the game but adds / removes your modes

{{< img src="/images/pingod/pingod-mainscene.tscn.jpg" title="Game/MainScene.tscn" caption="Added in favorites for quick acess" alt="" width="500px" position="center" >}}

---

## Modes

### Attract (Mode)

This is an editable scene which you can find in `modes/common/attract`

Standard attract mode to show `high scores` and `PUSH START`. 

When pushing start in this mode (if the Trough is ready) it will remove the attract mode and add the `Game.tscn`

---

## Pause Control

A layer to show when the game is paused. Visibilty is set to false by default and a signal will display when needed.

---
