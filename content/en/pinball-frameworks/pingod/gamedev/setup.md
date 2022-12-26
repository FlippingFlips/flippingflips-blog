---
author: "Flips-Admin"
title: "⚙️ PinGod - Installation & Running The BasicGame"
date: 2021-12-03T12:00:06+09:00
description: "Setup and install PinGod"
draft: false
image: /images/pingod/pingod-logo.png
hideToc: false
enableToc: true
enableTocContent: false
author: flips-admin
authorEmoji: 🐎
categories:
- guides
- pingod
tags: 
- beginner
---

---

** Note: These guides aren't required for players to play your game if providing an exported version.

## Godot Setup (Windows)
---

### Download

- Download Godot editor. (Godot is portable - no installation required)
[Godot Download](https://godotengine.org/download). ( Version 3.3 as of this document )

### Additional Godot Setup

- Extract the engine somewhere on your drive `C:\Godot` if on windows for example but can be anywhere.
- Rename the godot executable to `godot` and add to the `Environment paths` on your system
- Now on any command line you can use `godot`

## Download PinGod
---

### Choice 1: Cloning Repo
---

`git clone https://github.com/FlippingFlips/pingod-basicgame`

### Choice 2: Downloading to machine
---

[Download Zip (GitHub)]("https://github.com/FlippingFlips/pingod-basicgame/archive/refs/heads/master.zip")

---

## Load Basic Game into Godot
---

The `BasicGameGodot` project can be loaded into the Godot editor by browsing projects, but it's faster to load into the editor via the file explorer or command line.

The `BasicGameGodot` project can be found in 'BasicGame` directory

### Addons Directory
---

{{< notice warning "This is a success type of notice" >}} Before running games we need to share the `addons` directory with the game. This can be done by making a symbolic link on the command line from the games project directory.
{{< /notice >}}

`mklink /D addons "C:\YourFullPathToTheAddons\PinGod.VP.Examples\addons\addons"`

{{< img src="/images/pingod/dev-addon-dir.jpg" title="PinGod Addons Symbolic Link" caption="" alt="PinGod Addons Symbolic Link" width="300px" position="center" >}}

### Load in editor
---

From the `BasicGameGodot` directory you can run the `godot -e` which will load the `.project` into the editor.

You can also just run the game with the `godot` command from the directory.

## Running BasicGame in Godot
---

Pushing play in the editor or running `godot` in the project directory will load the game display. You can test some default keyboard actions here.

### Keyboard Switches / Actions
---

To start a game add credits, fill up the trough (see keys below) and push start.

Key action / switch mappings can be found in the `Project Settings / InputMap`

#### Standard Switches
---

```
ESC = Exit game window
1 = Start
5 = Credits

Q = Trough1
W = Trough1
E = Trough1
R = Trough1
```

#### Coin door switches
---

```
7 = Exit
8 = Down
9 = Up
0 = Enter (Service Menu)
```

### Using the lamp / switch overlays

#### Enable Overlays
---

Open the scene `res://game/PinGodGame.tscn` and enable the following

{{< img src="/images/pingod/pingod-overlays.jpg" title="Overlay options" caption="" alt="PinGod Overlay options" width="300px" position="center" >}}

#### Using overlays
---

When you run the game now you will be greeted with switches and lamp overlay. Columns and sizes can be adjusted by selecting the scene in the `PinGodGame` scene and selecting the LampMatrix or SwitchOverlay

{{< img src="/images/pingod/pingod-overlays-toggled.jpg" title="Using switch overlay to test game" caption="" alt="PinGod Overlay trough switches" width="300px" position="center" >}}

### Recording the game
---

Switch events can recorded and then played back later on to save you time when testing.

#### Record
---

Enable `Record Game` and give it a name like `res://recordings/add-trough-start-game.record` for example.

Create the file in the recordings folder for it to record to. You can right click the recordings folder in godot and `Open In File Manager`

{{< img src="/images/pingod/pingod-recordings.jpg" title="Record / Playback Options" caption="" alt="PinGod Overlay trough switches" width="300px" position="center" >}}

The name suggests what we will do, run the game in record mode...

- Fill up the trough and start game
- Toggle `Trough4` so it releases a ball, then drain it by swithing it on again and then exit the window

#### Playback
---

Enable playback and run your recording

#### Record/Playback Demo
---

<iframe class="rumble" width="640" height="360" src="https://rumble.com/embed/vggcib/?pub=n1o8b" frameborder="0" allowfullscreen></iframe>

## Running BasicGame Visual Pinball
---

Table can be run from any location on disk inside Visual Pinball. 

{{< img src="/images/pingod/pingod-vp-editor.jpg" title="PinGod BasicGame VP" caption="table editor for the BasicGame" alt="" width="300px" position="center" >}}

The controller will load the game when launched. 

### Controller Setup and scripts
---

- Register the `PinGod.VP controller` with the setup from [Download PinGod.VP/releases](https://github.com/FlippingFlips/pingod-controller-com/releases)
- Add the extra scripts needed from the controller install to `VisualPinball/Scripts`

### Table script Godot game directory
---

Update the tables script to include the path to the `BasicGameGodot` project. This will run the project with the `godot` command.

- `Const GameDirectory = "C:\Yourfilepath\BasicGameGodot"`

{{< notice info >}} This directory change is only needed for debugging as the game executable can be shipped with table to work in the same directory.
{{< /notice >}}

### Play game
---

#### Pre launch Checks
---

In the `Godot` project settings make sure you have the read/write enabled for communication between VP and PinGod.

{{< img src="/images/pingod/pingod-vp-states.jpg" title="PinGod read / write states" caption="" alt="" width="300px" position="center" >}}

{{< notice info >}} The `Godot` editor doesn't have to be running for this but it can be, makes no difference.
{{< /notice >}}

#### In Game / Display
---

After launching and when the game is ready a signal is sent back to visual pinball which will activate the game.

Display can be moved / resized by pushing `F2` on the window.

{{< img src="/images/pingod/pingod-vp-basic-multiball.jpg" title="PinGod Basic Game Visual Pinball" caption="Hit the hole to start a multi ball with ball saves" alt="" width="300px" position="center" >}}

## Building Release Export
---

### Visual Pinball Release
---

In the `BasicGame` table script you can uncomment the release variables. For a release we are presuming the correct name of our export and that it is in the same directory as the table file.

```
Const IsDebug = False
Const GameDirectory = ".\PinGod.BasicGame.exe" 'exported game
```

### PinGodGame Export
---

In the `BasicGameGodot` directory you can run the `_build_export.bat` file. (This just runs a Godot export via a command with `godot --export "Windows Desktop"`)

When you run this file export, it will open godot for a short time, then close when completed.

The exported files can be found in the `BasicGame` directory under `Exported`. 

{{< img src="/images/pingod/pingod-exported.jpg" title="PinGod Release build" caption="Example files from an export copying in VP table" alt="" width="300px" position="center" >}}

## Game Logs
---

Game logs are stored in the machines user directory. The most recent log is named `godot.log`

`AppData\Roaming\Godot\app_userdata\{GameName}`