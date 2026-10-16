# ER Comp Simulator

A tool for planning team compositions ("comps") for Eternal Return.

> ⚠️ This is a beta version. You may run into bugs or parts that don't work properly.

[日本語](./README.md) / [English](./README-en.md) / [한국어](./README-ko.md) / [繁體中文](./README-zh-TW.md)

## What you can do

- Register players and manage which characters (subjects) they play
- Register teams (multiple teams are supported)
- Build comps for each team, with an optional RouteID for each character
- Export / import team and player data
- Use the app in Japanese, English, Korean, or Traditional Chinese (searching characters works with names in any language)

## Getting started

1. On first launch, a **language selection screen** appears. Choose your language (you can change it later inside the app).
2. A team with a placeholder name is created for you.
3. Your data is stored next to the app (exe): `ertool.db` (data) and `settings.json` (language and other settings).

The screen is laid out as: **Player area** on the left, the **character list** at the bottom center, and the **Team area** on the right.

---

## Registering players

<img src="./image.png" alt="Screen overview" style="zoom:30%;" />

- Press "Add player" to register a player name and a Dak.gg link.
  - The player name doesn't have to match the Dak.gg name. Use whatever name is easy to recognize.
  - Player names must be unique (case-insensitive).
- You can also add a player who is already registered in another team (players are shared across teams).

### Buttons in the Player area

| Button | What it does |
| --- | --- |
| 💾 Floppy disk | Saves the player data |
| ⚙ Gear | Player settings: delete data, import, etc. |
| 🌐 Globe | Opens Dak.gg in your browser (unavailable if no Dak.gg link is registered) |
| ⤴ Share icon | Exports the player data (for sharing with others) |
| ✕ Cross | Removes this player from the team |

### Assigning characters to a player

- **Drag and drop a character image** from the list at the bottom center into the Player area.
- To remove one, drag it onto the trash bin below.
- Use the filter box to **search characters by name**. A match in any language works (for example, "Ay" finds Aya). Hiragana and katakana are treated the same, and several words separated by spaces must all match.

### Swapping players

- **Drag a Player header (the name bar) onto another Player slot** to move the player there.
- If another player is already in that slot, they are removed from the team, and their assignments are removed from the comps. Press **Ctrl+Z** to undo.
- Dropping onto an empty slot simply moves the player.

---

## Teams

### Controls on the right

- **Team name**: click the team name in the header to edit it directly (Enter to apply, Esc to cancel). Team names may be duplicated.
- **Team combo box**: switch between teams. Use "+" to add a new team.
- **💾 Floppy disk**: saves the team. **At least 3 players (already saved)** are required.
- **⚙ Gear**: team settings, such as deleting the team.
- **⤴ Share icon**: exports the team. The linked players are exported together. Use it to share with others.
- **"+" at the bottom**: adds a comp. Switch between comps with the tabs on the left.

### Putting characters into a comp

- **Drag and drop characters** from the Player area into the comp.
    - Double-click to remove an assignment.
    - For the same player, drag another character to swap it in.
- The three slots of a comp are ordered by the **number of the Player on the left**.
- If you remove a character from a player's pool, it also disappears from the comps.

### RouteID

- Each comp slot has a **RouteID** field (an integer of 1 or more) below the player name.
- It's optional, and the same number can be used in several slots.
- Press Enter or move focus away to apply it.

---

## Saving and undo

- Changes are kept as a draft and are not written to the database until you save. While there are unsaved changes, **"● Unsaved"** is shown.
- **Ctrl+S**: saves the open team and players together (Save all).
- **Ctrl+Z**: undoes the last action (redo is also available).
- Players and teams can also be saved individually.
- If the same data was changed elsewhere first, you'll be asked whether to overwrite it.

## Language

- Switch language any time with the language selector in the app. No restart is needed.
- The translations are based on machine translation, so there may be mistakes.

---

## (For advanced users) Avoiding the "untrusted publisher" warning

A public key is included. Register it in your list of trusted keys.
