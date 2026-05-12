---
title: "Lethal Company Communication & Signals Guide: Walkie-Talkie Tips & Team Coordination (2026)"
description: "Lethal Company communication and signals guide: walkie-talkie best practices, monster signal recognition, team coordination tactics, and callout systems for survival."
date: 2026-05-12
cover:
  image: "/cover-image/lethal-communication/cover.webp"
  alt: "Lethal Company Communication & Signals Guide Cover"
  caption: "Lethal Company Communication & Signals Guide"
lastmod: 2026-05-12
draft: false
tags: ["Lethal Company", "PC Games", "Communication", "Co-op", "Strategy Guide", "lethal company walkie talkie", "lethal company team coordination", "lethal company signals"]
categories: ["PC Games"]
games: ["Lethal Company"]
---

> *Last updated: May 12, 2026. All monster behaviors, terminal commands, and equipment mechanics verified against Lethal Company v69 (current stable build as of May 2026).*

## Quick Summary: Communication Essentials

| Element | Details |
|---------|---------|
| **Walkie-Talkie Range** | ~30 meters indoors, ~80 meters outdoors |
| **Channels** | 1–8 shared by all players on the same frequency |
| **Battery Life** | Walkie-Talkie: 2 min continuous, Ship Radio: unlimited |
| **Ship Monitor** | Tracks player life signs, teleporter, ship storage |
| **Key Callouts** | Monster location, scrap count, danger warnings, extraction needed |
| **Best Practice** | Pre-assign roles and radio protocol before entering any facility |

---

## Why Communication Determines Survival

In Lethal Company, poor communication is the number one cause of team wipes. A team with average mechanical skill but excellent communication will consistently outperform a team of skilled players who do not talk. The game deliberately creates information asymmetry — only the player who sees a monster knows it is there — making communication the critical link between individual awareness and team survival.

### The Cost of Silence

| Scenario | With Communication | Without Communication |
|----------|-------------------|----------------------|
| **Bracken (Flowerman) encounter** | Team warned, 1 death max | Entire squad stunned and killed |
| **Thumper trap** | Player announces, team routes around | 2–3 players walk into same trap |
| **Company Cruiser chase** | Team sets up ambush at choke point | Players scatter, individually hunted |
| **Jester winding up** | Observer warns others, no one enters room | 3–4 players killed by pop-out |
| **Maneater (old bird) in fog** | Player with radar warns of approach | Players caught in open, no time to react |

## Walkie-Talkie Mechanics

### How Walkie-Talkies Work

Walkie-Talkies are purchasable from the Terminal for **100 credits** each. They enable voice communication between players who are carrying them, regardless of distance, as long as both players are alive.

| Property | Value |
|----------|-------|
| **Cost** | 100 credits |
| **Quantity Sold** | 2 per Terminal purchase |
| **Effective Range** | Unlimited (as long as both carry one) |
| **Activation** | Hold the walkie-talkie and press the use key |
| **Interference** | Signal degrades in certain facility areas (notably deeper levels) |
| **Durability** | Cannot be destroyed, but can be dropped |

### Walkie-Talkie Best Practices

1. **Every player carries one** — This is non-negotiable. Buy walkie-talkies before every expedition. If budget is tight, prioritize the Scout and the person staying at the ship.
2. **Keep it in your hotbar** — You need to switch to it instantly when danger appears. Do not bury it in your inventory.
3. **Speak in short, clear callouts** — Long monologues block critical warnings. Use the format: *"What + Where + How many."*
4. **Announce before entering rooms** — *"Entering room B2, left hallway"* gives the team awareness of your location if your signal cuts out.

### Walkie-Talkie Protocol

| Situation | Callout Format | Example |
|-----------|---------------|---------|
| **Monster spotted** | `[Monster name] at [landmark], [direction]` | *"Bracken at the fork, heading north corridor"* |
| **Scrap found** | `[Item type], [weight class], [location]` | *"Large axe, heavy, second floor room"* |
| **Danger warning** | `DANGER at [location], [what to do]` | *"DANGER at entrance, landmine on the right"* |
| **Retreat request** | `Need backup at [location]` | *"Need backup at main hallway, being chased"* |
| **Status update** | `[Items carried] / [Health status]` | *"2 items, both light, health fine"* |

For team role assignments that complement this communication system, see our [Co-op Team Roles Guide](/posts/lethal-company/coop-team-roles-guide/).

## Monster Signal Recognition

Learning to identify monsters by their audio and visual signals is just as important as walkie-talkie communication. Many encounters give you a 2–5 second warning before the monster becomes lethal.

### Audio Signals by Monster

| Monster | Audio Signal | Warning Time | Response |
|---------|-------------|--------------|----------|
| **Bracken (Flowerman)** | No sound until behind you — then a rustling noise | 0–1 seconds | Sprint away immediately; do not look back |
| **Thumper** | Loud mechanical thumping, increasing frequency | 2–3 seconds | Stand still; do not move until thumping stops |
| **Jester** | Musical winding sound (increasing pitch) | 5–10 seconds (full wind) | Leave the room before the box opens |
| **Hoarding Bug** | Skittering sounds, occasional item-drop clink | 3–5 seconds | Kill it quickly or let it flee; it is not worth chasing |
| **Coiler** | Hissing + electrical crackling | 1–2 seconds | Do not approach; use a Stun Grenade if confrontation is necessary |
| **Mouth Dog (Maneater)** | Barking that gets louder as it approaches | 5–8 seconds | Enter a building immediately; it cannot follow indoors |
| **Earth Leviathan** | Low rumbling, ground shake | 3–5 seconds | Stay on the ship; do not be on the moon surface |
| **Girl (Ghost Girl)** | Crying/laughing, lights flicker | 3–5 seconds | Run to a different room; she follows the last player who saw her |
| **Masked** | Human-like voice calling your name | 2–4 seconds | Do not approach; it is not your teammate |

### Visual Signals

| Monster | Visual Signal | What It Means |
|---------|--------------|---------------|
| **Bracken** | Tall, thin flower-like figure in peripheral vision | You are being stalked; keep moving |
| **Thumper** | Red laser scanning the floor | Movement detection active; freeze |
| **Jester** | Jack-in-the-box with visible winding key | Music playing = counting down to attack |
| **Nutcracker** | Glowing eyes in dark hallways, visible flashlight reflection | Line-of-sight based; break line of sight |
| **Centipede** | Small dark shape moving along walls/ceilings | Dropping from above; watch overhead |
| **Blob** | Puddle-like substance on the floor, dark and glossy | Do not step in it; causes blind effect |
| **Forest Giant** | Massive silhouette between trees, glowing eyes | Stay on cleared paths; do not wander into deep forest |

## The Ship as Communication Hub

The ship is your team's base of operations and the center of your communication network.

### Ship Terminal Functions

The ship terminal is accessible via typing commands. It serves as both a management tool and a communication relay.

| Command | Function | Communication Value |
|---------|----------|-------------------|
| `monitors` | Shows player health and location status | Tracks who is alive and who is outside |
| `scan` | Reveals facility layout and scrap locations | Shares map intel with the team |
| `teleporter` | Activates inverse teleporter to bring players back | Emergency extraction callout system |
| `signal` | Plays a signal that all players can hear | Audio beacon for lost teammates |
| `store` | Shows items currently loaded on the ship | Inventory management across the team |

For a complete list of terminal commands, see our [Terminal Commands Guide](/posts/lethal-company/terminal-commands-guide/).

### Using the Ship Monitor Effectively

The `monitors` command is your most important real-time communication tool. It shows:

```
PLAYER STATUS:
Player1 - ALIVE - Inside facility
Player2 - ALIVE - Outside (moon surface)
Player3 - DEAD - [no signal]
Player4 - ALIVE - On ship
```

**Best practices:**

- Check `monitors` every 5 minutes during a facility run
- If a player shows as DEAD, immediately inform the team and adjust your strategy
- If a player is ALIVE but not responding on walkie-talkie, they may be in a signal-dead zone or stunned

## Team Coordination Tactics

### The Buddy System

Never enter a facility alone. The buddy system pairs players so that every person has at least one teammate within walkie-talkie range and visual range.

| Pair | Roles | Strategy |
|------|-------|----------|
| **Scout + Carrier** | Scout identifies threats; Carrier collects scrap | Scout goes first, Carrier follows 5 meters behind |
| **Ship Guard + Interior Team** | Ship Guard monitors terminal; Interior Team clears facility | Ship Guard calls out threats and manages teleporter |
| **Rear Guard + Front Team** | Rear Guard watches the exit route; Front Team pushes forward | Prevents ambush from behind |

### Standard Callout System

Establish a consistent callout system before each run. The following conventions work well:

| Callout | Meaning |
|---------|---------|
| **"Contact"** | Monster in sight |
| **"Clear"** | Area checked, safe to proceed |
| **"Hot"** | Active threat, do not approach |
| **"Cold"** | No immediate threats |
| **"Grab"** | Valuable scrap, need help carrying |
| **"Push"** | Advancing to next area |
| **"Pull"** | Retreating to previous area |
| **"Ship"** | Returning to ship / extraction needed |
| **"All in"** | Committing to high-risk, high-reward play |
| **"Bail"** | Abandon mission, everyone retreat now |

### Pre-Run Communication Checklist

Before entering any facility, the team should confirm:

- [ ] All players have walkie-talkies equipped
- [ ] Roles are assigned (Scout, Carrier, Ship Guard)
- [ ] Meeting point established (usually the facility entrance)
- [ ] Emergency extraction plan confirmed (who activates teleporter)
- [ ] Scrap quota discussed (minimum target for the day)
- [ ] Time limit acknowledged (facility closes at a certain hour)

## Equipment for Communication

### Essential Communication Equipment

| Item | Cost | Purpose | Priority |
|------|------|---------|----------|
| **Walkie-Talkie** | 100 credits (2-pack) | Voice communication | Mandatory |
| **Flashlight** | Free (spawn) | Visual signals in dark areas | Mandatory |
| **Stun Grenade** | 60 credits | Emergency monster neutralization + team signal | High |
| **Boombox** | 50 credits | Distraction + audio beacon for lost players | Medium |
| **Radar Booster** | 500 credits | Extended signal range + monster detection | Medium |
| **TZP-Inhalant** | 35 credits | Speed boost for emergency retreats | Situational |

### Using Equipment as Signals

Beyond their primary function, several items can serve as communication tools:

- **Flashlight strobing**: Quick on-off flashes mean "danger ahead." Two flashes mean "all clear."
- **Boombox placement**: Leave a playing boombox at a junction to mark it as safe or as a rally point.
- **Stun Grenade**: If you hear a stun grenade, it means a teammate is in combat — move to their position.
- **Zap Gun**: The electrical sound carries far and can signal that a Coiler or similar electrical threat is active.

For a complete equipment breakdown, check our [Equipment Guide](/posts/lethal-company/equipment-guide/).

## Handling Communication Breakdowns

### When Walkie-Talkies Fail

Walkie-talkies can fail in several scenarios:

| Failure Mode | Cause | Solution |
|-------------|-------|----------|
| **Signal dead zone** | Deep facility areas with thick walls | Move to a stairwell or open area; signal may return |
| **Player dropped walkie-talkie** | Accidentally swapped or dropped | Shout (proximity chat) until you can regroup |
| **Player is stunned** | Bracken attack, Coil-Head stare | Team must locate and revive; walkie-talkie still works |
| **Player is masked** | Replaced by Masked entity | Walkie-talkie calls may be deceptive; verify identity visually |
| **All walkie-talkies broken** | Not possible in current version — they are indestructible | N/A |

### Proximity Chat as Backup

When walkie-talkies are unavailable, Lethal Company's proximity chat becomes your primary communication method. Proximity chat has a range of approximately **15 meters**.

- **Shouting increases range** by about 50% but also attracts nearby monsters
- **Use proximity chat strategically** — only shout when the threat level justifies the noise risk
- **Combine with flashlight signals** for silent communication when monsters are nearby

## Weather Effects on Communication

Weather conditions on different moons can significantly impact your communication strategy.

| Weather | Effect on Communication | Strategy Adjustment |
|---------|----------------------|-------------------|
| **Clear** | Normal walkie-talkie range | Standard protocol |
| **Foggy** | Reduced visibility, audio carries further | Rely more on audio signals; walkie-talkie range unchanged |
| **Rainy** | Rain noise masks audio signals | Walkie-talkie becomes critical; do not rely on proximity audio |
| **Stormy** | Lightning flashes provide momentary visibility; thunder masks sounds | Use flashlight signals aggressively; walkie-talkie only reliable method |
| **Eclipsed** | Extreme darkness; monsters are more active | Maximum communication discipline; check monitors every 2 minutes |

For detailed moon weather patterns, see our [Weather & Conditions Guide](/posts/lethal-company/weather-and-conditions-guide/).

## Advanced Communication Strategies

### The Relay System

On large maps, a single walkie-talkie chain may not reach from the ship to the deepest rooms. The relay system solves this:

1. **Player 1** (Ship Guard) stays at the ship with a walkie-talkie
2. **Player 2** (Relay) positions halfway between ship and facility entrance
3. **Player 3** (Scout) goes deep into the facility
4. **Player 4** (Carrier) works with the Scout

Player 2 relays messages between the Ship Guard and the Scout team. This extends your effective communication range across the entire map.

### Silent Communication During Stealth

When monsters are sensitive to sound (Bracken, Nutcracker, Mouth Dog), use these silent signals:

| Signal | Meaning |
|--------|---------|
| **Crouch stand-up (once)** | Monster nearby, stay quiet |
| **Crouch stand-up (twice)** | Monster left, area clear |
| **Pointing direction** | Move that way |
| **Shaking head** | Do not go that way |
| **Dropping and picking up an item** | "Look at this scrap" |

### Dealing with Public Lobbies

When playing with random players in public lobbies, communication challenges multiply:

- **Assume no one has a microphone** — Use the terminal `signal` command as a universal attention-getter
- **Lead by example** — Start making callouts yourself; others often follow
- **Use the ship monitor aggressively** — Check `monitors` frequently and announce status changes
- **Be patient with new players** — Explain the callout system once; do not spam warnings

## Common Communication Mistakes

| Mistake | Consequence | Fix |
|---------|------------|-----|
| **Talking over each other** | Critical warnings get lost | One person speaks at a time during combat |
| **Vague callouts** ("Something's here!") | Team cannot respond appropriately | Always name the monster and its location |
| **Ignoring the ship monitor** | Missing teammate deaths | Check monitors every 5 minutes minimum |
| **Running without announcing** | Team loses track of your position | Announce movement before leaving the group |
| **Hogging the walkie-talkie** | Blocks emergency communications | Keep transmissions under 5 seconds during active runs |
| **Not confirming receipt** | Sender does not know if message was heard | Acknowledge with "Copy" or "Heard" after each callout |

## Related Guides

- [Co-op Team Roles Guide](/posts/lethal-company/coop-team-roles-guide/) — Optimal 4-player team composition and role assignments
- [Terminal Commands Guide](/posts/lethal-company/terminal-commands-guide/) — Complete list of ship terminal commands and their uses
- [Equipment Guide](/posts/lethal-company/equipment-guide/) — Every item in the game, costs, and optimal usage
- [Weather & Conditions Guide](/posts/lethal-company/weather-and-conditions-guide/) — How weather affects gameplay and strategy on different moons
