---
title: "Lethal Company Terminal Commands Guide: Complete Reference (2026)"
description: "Complete terminal command reference for Lethal Company in 2026. Every command including moons, store, bestiary, scan, switch, ping, and hidden commands listed."
date: 2026-05-10
cover:
  image: "/cover-image/lethal-company-terminal-commands/cover.webp"
  alt: "Lethal Company Terminal Commands Guide Cover"
  caption: "Lethal Company Terminal Commands Guide"
lastmod: 2026-05-10
draft: false
tags: ["Lethal Company", "PC Games", "Controls", "Mechanics"]
categories: ["PC Games"]
games: ["Lethal Company"]
---

> *Last updated: May 10, 2026. This guide covers every terminal command in Lethal Company, from basic navigation to hidden secrets. Master the terminal to travel efficiently, buy equipment, and access crucial information.*

## Terminal Basics

The terminal is located at the front of the ship, directly opposite the main door. Press **E** to interact with it. The terminal is your hub for travel, shopping, information, and communication.

### Keyboard Controls

| Key | Function |
|-----|----------|
| **Type** | Enter commands |
| **Enter** | Submit command |
| **Backspace** | Delete character |
| **Up/Down Arrows** | Scroll through command history |
| **Tab** | Auto-complete (partial) |
| **Ctrl+C** | Clear current line |

### Command Syntax

All commands are case-insensitive. Type the command and press Enter. Some commands accept additional parameters separated by spaces.

```
command [parameter1] [parameter2]
```

---

## Complete Command Reference

### Navigation Commands

#### `moons`

Lists all available moons with their travel costs and current weather conditions.

| Syntax | `moons` |
|--------|---------|
| **Output** | List of all 8 moons with cost and weather |
| **Requirements** | None |
| **Use Case** | Planning which moon to visit |

**Example Output:**
```
[PlanetMoonsList]
41-Experimentation (1 day): 0 credits, Weather: Clear
21-Assurance (1 day): 0 credits, Weather: Foggy
56-Vow (1 day): 0 credits, Weather: Stormy
5-Offense (1 day): 50 credits, Weather: Clear
20-March (1 day): 150 credits, Weather: Flooded
85-Rend (1 day): 550 credits, Weather: Snowy
7-Dine (1 day): 600 credits, Weather: Clear
8-Titan (1 day): 700 credits, Weather: Eclipsed
```

**Pro Tip:** Always check weather before traveling. Eclipsed and stormy weather on hard moons should be avoided.

#### `[moon name]`

Travel to a specific moon. Must be followed by `confirm`.

| Syntax | `[moon name]` then `confirm` |
|--------|------------------------------|
| **Full Moon Names** | `Experimentation`, `Assurance`, `Vow`, `Offense`, `March`, `Rend`, `Dine`, `Titan` |
| **Requirements** | Sufficient credits in the ship's account |
| **Use Case** | Initiating travel |

**Travel Sequence:**
```
> experimentation
[PlanetSelected]
41-Experimentation selected.
Type "confirm" to confirm selection.
> confirm
[PlanetConfirmed]
Traveling to 41-Experimentation...
```

**Note:** You can also enter the numerical designation: `41-Experimentation`, `21-Assurance`, `56-Vow`, `5-Offense`, `20-March`, `85-Rend`, `7-Dine`, `8-Titan`.

#### `stop`

Ends the current day. All players must be on the ship.

| Syntax | `stop` |
|--------|--------|
| **Requirements** | All alive players on ship |
| **Use Case** | Ending the day after selling scrap |

```
> stop
[StopCommand]
End shift? (yes/no)
> yes
[DayEnding]
Day ended. Scrap value: 850 credits. Quota: 500 credits.
Quota met! Next quota: 720 credits.
```

**Critical:** Ensure ALL players are on the ship before using `stop`. Anyone outside dies.

---

### Store Commands

#### `store`

Opens the Company Store interface, showing available items for purchase.

| Syntax | `store` or `store [page#]` |
|--------|---------------------------|
| **Requirements** | None |
| **Use Case** | Browsing and buying equipment |

```
> store
[Shop]
Page 1 of 3
┌────────────────────────────┬──────────┬───────┐
│ Item                       │  Price   │Stock  │
├────────────────────────────┼──────────┼───────┤
│ Flashlight                 │   15     │  ✓    │
│ Pro-Flashlight             │   25     │  ✓    │
│ Shovel                     │   30     │  ✓    │
│ Walkie-Talkie              │   12     │  ✓    │
│ Stun Grenade               │   30     │  ✓    │
│ Boombox                    │   60     │  ✗    │
└────────────────────────────┴──────────┴───────┘
Continue browsing? (y/n)
```

#### `buy [item]`

Purchase an item from the store.

| Syntax | `buy [item name]` |
|--------|-------------------|
| **Requirements** | Item must be in stock, sufficient credits |
| **Use Case** | Buying equipment |

```
> buy shovel
[BuyItem]
Purchased Shovel for 30 credits.
1 left in stock.
```

**Multi-Buy:** You can buy multiple items at once:
```
> buy flashlight
> buy flashlight
> buy walkie-talkie
```

#### `info [item]`

Shows detailed information about a store item.

| Syntax | `info [item name]` |
|--------|-------------------|
| **Requirements** | None |
| **Use Case** | Learning about an item before purchase |

```
> info pro-flashlight
[ItemInfo]
Pro-Flashlight
Price: 25
A heavy-duty flashlight with extended battery life
and a wider beam. Essential for dark environments.
```

---

### Selling Commands

#### `sell [item]`

Sell a specific scrap item that is on the ship.

| Syntax | `sell [item name]` or `sell [item1] [item2]` |
|--------|----------------------------------------------|
| **Requirements** | The scrap item must be physically on the ship |
| **Use Case** | Converting scrap to credits for quota |

```
> sell gold bar
[SellItem]
Sold Gold Bar for 142 credits.
Total quota value: 142 / 500
```

#### `sell all`

Sells ALL scrap items currently on the ship.

| Syntax | `sell all` |
|--------|------------|
| **Requirements** | Scrap items on the ship |
| **Use Case** | Quick selling at end of day |

```
> sell all
[SellAll]
Sold 8 items for a total of 634 credits.
Total quota value: 634 / 500
```

**Warning:** There is no confirmation for `sell all`. Make sure you do not want to keep any items (like a shotgun for defense) before using this.

---

### Information Commands

#### `bestiary`

Opens the bestiary, which shows information about monsters that players have scanned.

| Syntax | `bestiary` |
|--------|------------|
| **Requirements** | At least one monster must have been scanned with Q |
| **Use Case** | Reviewing monster behavior and lore |

```
> bestiary
[Bestiary]
Scanned Entities:
1. Bracken
2. Coil-Head
3. Thumper
4. Hoarding Bug
5. Snare Flea

View details: bestiary [number]
```

#### `bestiary [#]`

View detailed information about a specific scanned entity.

```
> bestiary 1
[BestiaryEntry]
Bracken - Class: Territorial
A tall, pale humanoid that stalks players through
industrial facilities. It becomes aggressive if
maintained eye contact for too long.
Strategy: Look away and back away slowly.
Danger Level: High
```

#### `scan`

Displays a summary of all scanned scrap items currently on the ship.

| Syntax | `scan` |
|--------|--------|
| **Requirements** | Items on ship must have been scanned |
| **Use Case** | Checking total scrap value before selling |

```
> scan
[ShipInventory]
Items on ship (scanned):
- Gold Bar (142 cr)
- V-Type Engine (95 cr)
- Cash Register (110 cr)
- Ring (34 cr)
Total value: 381 credits
```

---

### Communication Commands

#### `switch [player]`

Switches the ship monitor camera to follow a specific player.

| Syntax | `switch [player name]` |
|--------|------------------------|
| **Requirements** | Player must exist on the current moon |
| **Use Case** | Operator tracking a specific teammate |

```
> switch jun
[SwitchCamera]
Camera switched to Jun.
```

**Player Names:** Use the player's in-game name as it appears in the top-left corner.

#### `view monitor`

Displays the ship monitor feed as text.

| Syntax | `view monitor` |
|--------|----------------|
| **Requirements** | None |
| **Use Case** | Quick radar check from terminal |

```
> view monitor
[Monitor]
External cameras active.
4 crew members detected.
1 unknown entity detected (north-east).
```

#### `ping [radar booster]`

Pings a specific Radar Booster, creating a sound that attracts monsters.

| Syntax | `ping [radar booster name]` |
|--------|------------------------------|
| **Requirements** | A deployed Radar Booster |
| **Use Case** | Luring monsters away from teammates |

```
> ping radar booster
[Ping]
Radar Booster ping sent.
```

**Radar Booster Naming:** When you deploy a Radar Booster, it is automatically named. You can ping it by its name or just "radar booster" if only one is deployed.

#### `transmit [message]`

Sends a text message through the signal translator. The message appears in the chat for all players.

| Syntax | `transmit [your message]` |
|--------|---------------------------|
| **Requirements** | None |
| **Use Case** | Text communication with team (useful if mic is broken) |

```
> transmit coming back with scrap
[Transmit]
Message sent: "coming back with scrap"
```

---

### Gameplay Commands

#### `ping`

Pings the current player's location on the ship radar.

| Syntax | `ping` |
|--------|--------|
| **Requirements** | None |
| **Use Case** | Marking your position for the operator |

---

## Hidden and Secret Commands

These commands are not documented in the game but have been discovered by the community.

#### `sigurd`

Displays Sigurd's lore logs — hidden story entries that reveal the game's backstory.

| Syntax | `sigurd` |
|--------|----------|
| **Requirements** | Must be entered on the ship terminal |
| **Use Case** | Lore exploration |

```
> sigurd
[SigurdLogs]
Entries found:
1. "Day 1 - First assignment"
2. "Day 4 - Something's wrong"
3. "Day 7 - The Company"
4. "Day 12 - They know"
5. "Day 15 - The truth"

View: sigurd [number]
```

**Note:** Sigurd logs are numbered and some may require finding specific items or achieving certain milestones to unlock. There are 15 total lore logs in the game.

#### `sigurd [#]`

Read a specific Sigurd log entry.

```
> sigurd 1
[SigurdLog]
"Day 1 - First assignment
They gave me a ship and a quota. Said it would be easy.
Just pick up scrap from abandoned facilities, they said.
Nothing to worry about, they said.
I've been watching the radar. Something is moving out there.
Something big."
```

#### `history`

Shows your recent terminal command history.

| Syntax | `history` |
|--------|-----------|
| **Use Case** | Reviewing recent commands |

#### `help`

Displays the help screen with available commands.

| Syntax | `help` |
|--------|--------|
| **Use Case** | Quick command reference |

```
> help
[Help]
Available commands:
- moons: List available moons
- store: Open the store
- bestiary: View scanned entities
- scan: Scan ship inventory
- sell: Sell scrap items
- buy: Purchase from store
- info: Item information
- switch: Switch camera view
- ping: Ping radar booster
- transmit: Send message
- view: View monitor
- help: Show this menu
- sigurd: Lore logs (hidden)
```

---

## Terminal Efficiency Guide

### Typing Speed Tips

| Technique | Benefit |
|-----------|---------|
| Use Tab for auto-complete | Saves keystrokes |
| Arrow Up for command history | Reuse previous commands |
| Short names work | "exp" may work for "experimentation" |
| Batch commands | Buy all items before leaving |

### Common Workflows

**Starting a Day:**
```
> moons                 ← Check weather
> store                 ← Buy needed equipment
> [moon name]           ← Select destination
> confirm               ← Travel
```

**Ending a Day:**
```
> scan                  ← Check inventory
> sell all              ← Sell everything
> stop                  ← End the day
> yes                   ← Confirm
```

**Quick Save (during day):**
```
> scan                  ← Quick value check
```

### Operator Workflow

| Priority | Command | When |
|----------|---------|------|
| 1 | `switch [player]` | Player enters facility |
| 2 | `view monitor` | Quick radar check |
| 3 | `ping [booster]` | Monster near teammate |
| 4 | `transmit [msg]` | No voice chat available |

---

## Complete Quick Reference Table

| Command | Syntax | Purpose |
|---------|--------|---------|
| Help | `help` | Show available commands |
| List Moons | `moons` | Show all moons with cost and weather |
| Travel | `[moon]` + `confirm` | Travel to a moon |
| Store | `store` | Browse shop items |
| Buy | `buy [item]` | Purchase equipment |
| Item Info | `info [item]` | View item details |
| Sell | `sell [item]` | Sell specific scrap |
| Sell All | `sell all` | Sell all scrap on ship |
| Scan | `scan` | Show scrap on ship |
| Bestiary | `bestiary` | View monster info |
| Switch Camera | `switch [player]` | Track a player |
| View Monitor | `view monitor` | Radar text output |
| Ping | `ping [booster]` | Ping radar booster |
| Transmit | `transmit [msg]` | Send text message |
| End Day | `stop` | End the current day |
| Lore | `sigurd` | View lore logs |
| History | `history` | Command history |

---

## Common Mistakes

| Mistake | Why It Happens | Fix |
|---------|---------------|-----|
| Typing `sell all` accidentally | No confirmation prompt | Only use it when ready |
| Forgetting `confirm` | Travel not initiated | Always type confirm after moon name |
| Misspelling moon names | Case-insensitive but spelling matters | Use Tab autocomplete |
| Buying without checking stock | Some items not available daily | Browse shop first |
| Selling items wanted for defense | Shotgun sold accidentally | Manually sell specific items |

---

## Conclusion

The terminal is the most important tool in Lethal Company. It controls where you go, what you buy, and how you communicate. Mastering terminal commands reduces the time spent on administrative tasks and lets you focus on survival and scrap collection.

The hidden `sigurd` command adds a layer of lore for players interested in the game's story — be sure to read all 15 logs for the full narrative. For competitive players, terminal efficiency (knowing commands by heart, using autocomplete, and batching operations) shaves valuable seconds off each day.

---

### Related Guides

- [Lethal Company Advanced Strategies Guide](/posts/lethal-company/advanced-strategies-guide/)
- [Lethal Company Beginner Guide: Survive Your First Quota](/posts/lethal-company/beginner-guide/)
- [Lethal Company Co-op Team Roles Guide](/posts/lethal-company/coop-team-roles-guide/)
- [Lethal Company Equipment Guide: Best Items and Loadouts](/posts/lethal-company/equipment-guide/)
- [Lethal Company Monster Bestiary: Every Entity Explained](/posts/lethal-company/monster-bestiary/)
- [Lethal Company Moons Guide: Complete Moon Rankings](/posts/lethal-company/moon-guide/)
- [Lethal Company Scrap and Loot Guide: Complete Item Database](/posts/lethal-company/scrap-and-loot-guide/)
