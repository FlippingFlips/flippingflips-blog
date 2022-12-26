---
author: "Flips-Admin"
title: "🆕 PinGod - Create New PinGod game"
date: 2021-12-03T12:00:07+09:00
description: "How to create a new game from the example BasicGame"
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

## Duplicate BasicGame

- Make a copy of the `BasicGame` directory and rename it to your game name `MyNewGame`
- Inside this folder rename the Godot project and VP directory to similar. `MyNewGameGodot` and `MyNewGameVisualPinball`

## Project Setup

- In your `MyNewGameGodot` directory rename the project files from `BasicGameGodot` to `MyNewGameGodot`.

{{< img src="/images/pingod/dev-basicgame-projectfiles.jpg" title="Rename PinGod Game Project Files" caption="" alt="PinGod project files" width="500px" position="center" >}}

- Use `Visual Studio Code` or similar to `search and replace` text in files rename `BasicGameGodot` to `MyNewGameGodot`

{{< img src="/images/pingod/dev-vscode-rename.jpg" title="Renaming PinGod references in VSCode" caption="" alt="PinGod Godot UI" width="500px" position="center" >}}

- Delete the addons directory inside `MyNewGameGodot` (if there is one), then make a new symbolic link `mklink /D addons "C:\PathToTheAddonFolder\PinGod.VP.Examples\addons\addons"`

{{< img src="/images/pingod/dev-addon-dir.jpg" title="PinGod Addons symbolic link" caption="" alt="PinGod Godot UI" width="500px" position="center" >}}

- Open the project in `Godot` by using the `godot -e` command in project directory.
- In the Project Settings and make sure `PinGodAddOns` is enabled, then build project.
- If it doesn't let you enable it with strange messages, build project first then enable.

{{< img src="/images/pingod/dev-godot-addons-settings.jpg" title="Rename PinGod references in files" caption="" alt="PinGod Godot UI" width="500px" position="center" >}}

- You can set Window size in `Project Settings\Display\Window`
- Optional: Update the `export_presets.cfg` to update the exported executable name.

### Visual Pinball

- Rename the table file to something like `MyNewGame (PinGod) VPX10-6.vpx`
- Open the tables script window in `Visual Pinball` and set the game directory to your `MyNewGameGodot` game path for debugging.