---
title: "Palworld Base Defense That Works While You're Offline — Automated Raid Survival Without Being There (2026)"
description: "Came back to a destroyed base because a raid hit while you were AFK? Here's the automated defense setup that survives raids without you — the exact Pal roster, base layout, and AI settings that work even when you're logged out."
date: 2026-06-16
lastmod: 2026-06-16
draft: false
tags: ["Palworld", "PC Games", "Base Building", "Defense", "Automation", "Survival"]
categories: ["PC Games"]
games: ["Palworld"]
cover:
  image: "/cover-image/palworld-base-defense/cover.webp"
  alt: "Palworld Automated Base Defense — Survive Raids While Offline"
  caption: "AFK-proof your Palworld base with automated defenses"
---

> *Last updated: June 16, 2026. Defense AI behavior, optimal Pal defender roster, base layout principles, and the settings that determine whether your base survives a raid while you're offline.*

## The Scene: You Log In to a Graveyard

You went to bed with a thriving base. Smelting ingots. Breeding Anubis. Fifteen Pals working in perfect harmony. You log in the next morning and — silence. The Palbox is empty. The assembly lines are rubble. Every Pal is incapacitated.

What happened? A raid spawned while you were AFK. Your Pals fought back, but without you directing them, they scattered, targeted the wrong enemies, and got wiped one by one. The raiders destroyed your Palbox last — meaning no Pals could respawn.

**Palworld does not pause when you're offline on a server. Raids can and will hit an unattended base.** But with the right setup, your base can defend itself — consistently, without you.

Here's exactly how to build it.

## How Base Defense AI Actually Works

Before you can build an automated defense, you need to understand what your Pals do when you're not there.

### The Aggro Priority Problem

When a raid spawns and you're not present, Pals follow this priority:

- **1**: Nearest enemy to their work station | Your farmer runs toward the raid instead of your fighter
- **2**: Enemy attacking their bed | Pals scatter to defend individual beds instead of grouping
- **3**: Enemy attacking the Palbox | By the time they target this, half the base is already dead
- **4**: Enemy attacking structures | Production buildings get destroyed while Pals chase random raiders


**The key insight:** Without a player to direct focus fire, Pals fight like a disorganized mob. Your defense setup needs to compensate for this AI limitation.

### What "Defense" Stat Actually Does

- **Attack**: Damage per hit | Still matters — Pals need to kill raiders
- **Defense**: Damage reduction per hit | **Critical** — AFK Pals take more hits because they don't dodge
- **HP**: Total health pool | **Critical** — AFK Pals stand and trade, no kiting
- **Work Speed**: Crafting/building speed | Irrelevant for defense


**The counter-intuitive rule for AFK defenders:** Defense and HP matter MORE than Attack. A Pal with 500 Attack and 2000 HP dies faster than one with 300 Attack and 5000 HP — because AFK Pals don't dodge. They facetank everything.

## The AFK Defense Roster

Not all combat Pals are good defenders. The best AFK defenders share three traits: high HP, AoE attacks, and the "aggressive" combat AI personality.

### S-Tier AFK Defenders

- ****Jormuntide Ignis**** (4500): 820 → Massive AoE fire attacks hit entire raid groups. High HP pool. Stays near base structures because it's also your Kindling worker.
- ****Astegon**** (4200): 850 → Dark/Dragon typing resists most raid types. AoE breath attack. Already at your base mining — doesn't need to be assigned to defense.
- ****Blazamut**** (4300): 800 → Fire AoE + high defense. Also works Kindling/Mining, so it's always on-site.
- ****Frostallion**** (4200): 850 → Legendary stats. Ice AoE freezes raiders in place, buying time. High mount speed means it reaches raiders fast.
- ****Warsect**** (5000): 920 → **Highest HP + Defense combo among non-Legendaries.** Ground-type resists Electric raiders. Tank that buys time for your damage dealers.


### A-Tier AFD Defenders

- ****Paladius**** — Legendary stats, triple-jump helps navigate base terrain
- ****Necromus**** — Dark nuke damage, double-jump mobility
- ****Shadowbeak**** — High Attack, Dark Laser hits multiple targets, fast
- ****Lyleen**** — Heals nearby Pals passively — keeps your defenders alive longer
- ****Orserk**** — Electric AoE, already generating power at your base
- ****Anubis**** — Fast attack speed, already at base crafting — always in position


### The 5-Pal AFK Defense Squad

For a base with 15 Pal slots, dedicate 5 to defense:

- **1** (Warsect): **Tank/Anchor** → 5000 HP, draws aggro, survives long enough for others to kill
- **2** (Jormuntide Ignis): **AoE Damage** → Fire AoE hits the entire raid wave at once
- **3** (Frostallion): **CC/Freeze** → Ice skills freeze raiders, interrupting their attacks
- **4** (Lyleen): **Healer** → Passive healing keeps your tank alive through extended fights
- **5** (Shadowbeak): **Single-Target Burst** → Finishes off the tankiest raider (Mammorest, boss-type)


This composition handles every raid type in the game: the tank holds aggro, the healer sustains, the AoE clears small enemies, the CC locks down dangerous targets, and the burst eliminates the biggest threat.

## Base Layout for Automated Defense

Your base's physical layout determines whether your defenders can actually reach raiders before they destroy your stuff.

### The Fatal Layout (What Gets You Wiped)

```
[Palbox] --- [Production] --- [Farming] --- [Breeding]
                ↑
          Raid spawns here
```

In this layout, raiders spawn next to your production buildings. By the time your defenders cross the base, your assembly lines are already destroyed.

### The Defense-Optimized Layout

```
[Defense Line: Walls + Defenders] --- [Open Kill Zone] --- [Production Core] --- [Palbox]
                                          ↑
                                    Raid spawns here
```

**Principles:**

1. **Perimeter wall with one gap** — Raiders pathfind through the gap. They don't attack walls unless blocked. Give them one entrance, and they'll funnel through it.
2. **Kill zone inside the gap** — Place your 5 defender beds and feeding station in a semicircle around the gap entrance. Defenders wake up, walk 5 steps, and they're in combat.
3. **Palbox in the far corner** — If everything else falls, the Palbox is the last thing raiders reach. This buys maximum time for your defenders to respawn (Palbox respawns incapacitated Pals after 10 minutes).
4. **Production behind the defense line** — Crafting stations, farms, and breeding pens go behind your defenders, not in front of them.

### Wall Material Matters

- **Wood** (1000): Levels 1-10 → Useless for AFK — breaks in 3 hits
- **Stone** (5000): Levels 10-25 → Minimum for AFK defense
- **Metal** (15000): Levels 25-40 → Good for mid-game bases
- **Refined Metal** (40000): Levels 40-50 → Required for endgame AFK


**Do not use Wood walls for AFK defense.** They're decorative. A level-30 raid destroys a Wood wall in under 5 seconds. Stone is the minimum viable material.

## Server Settings That Prevent AFK Wipes

If you control the server (dedicated server or single-player with friends), these settings make AFK defense dramatically more reliable:

- **PalDamageRate** (1.0): 1.0 → Keep default — your defenders need to kill things
- **PalStaminaDecreaceRate** (1.0): 0.5 → Pals don't get exhausted mid-fight
- **PalAutoHPRegenRate** (1.0): 2.0 → Defenders heal between raid waves
- **BaseCampWorkerMaxNum** (15): 20 → More slots = more defenders without sacrificing workers
- **DropItemMaxNum** (3000): 5000 → Dead raiders drop loot — more capacity means no despawns


**The single most impactful change:** `PalAutoHPRegenRate` at 2.0. This means your defenders heal to full between raid waves (which are typically 10-30 minutes apart on a server). Without it, a Pal that survived the first wave at 20% HP dies instantly to the second.

## The Feeding Station: Your Secret Weapon

Pals won't fight if they're starving. An empty feeding station means your defenders sit there with 0 SAN, refusing to engage.

- **Berries** (Low): Short → **Useless for AFK** — runs out in 2 hours
- **Salad** (Medium): Medium → Minimum viable for AFK
- **Pizza** (High): Long → Good — lasts 6-8 hours
- **Carbonara** (Very High): Very Long → **Best** — lasts 12+ hours, max SAN
- **Cotton Candy** (Instant SAN): One-time → Emergency only, does not sustain


**The rule:** Fill your feeding station with Carbonara before logging off. Check the quantity — if you have 5 defenders and each eats roughly 1 Carbonara per 2 hours, you need 30 Carbonara for a 12-hour AFK session. Round up to 50 to be safe.

## Real Raid Scenarios and Outcomes

Here's what actually happens with each raid type against an optimized AFK defense:

- **Syndicate Thugs (Lv10-20)** (5-8): All dead in 30 seconds. Zero structure damage. → Some farming plots destroyed.
- **Free Pal Alliance (Lv20-30)** (6-10): All dead in 60 seconds. Minor wall damage. → Production stations destroyed.
- **PIDF Grunts (Lv30-40)** (8-12): All dead, 1-2 defenders at 50% HP. → Half the base destroyed.
- **Legendary Raid (Lv40-50)** (3-5 (high HP)): Most raiders dead, 1-2 defenders incapacitated. Palbox intact. → Total base wipe. Palbox destroyed.


**The PIDF Grunt raid is the most dangerous for AFK bases.** Not because individual enemies are strong, but because there are 12 of them — enough to split your defenders' attention and slip past to your production buildings.

## Common AFK Defense Failures

- **Base destroyed, Pals alive but starving**: Feeding station was empty | Fill with Carbonara, check quantity before logout
- **Pals alive, base destroyed**: No walls funneling raiders | Build perimeter wall with single gap entrance
- **Pals incapacitated, base intact**: Defenders too weak for raid level | Upgrade defender roster, check enemy levels
- **Everything fine but loot despawned**: DropItemMaxNum too low | Increase to 5000 in server settings
- **Random Pal died, rest fine**: That Pal had low HP + no healer support | Add Lyleen to defense squad
- **Wall destroyed, then base destroyed**: Wood walls against Lv30+ raid | Upgrade to Stone or Metal walls


## The AFK Defense Checklist

Before you log off:

- [ ] 5 dedicated defenders assigned (Warsect + J.Ignis + Frostallion + Lyleen + Shadowbeak)
- [ ] Defender beds placed in semicircle at kill zone entrance
- [ ] Feeding station filled with 30+ Carbonara
- [ ] Perimeter wall with single gap (Stone minimum, Metal preferred)
- [ ] Palbox in farthest corner from raid spawn
- [ ] Production buildings behind defense line
- [ ] Server settings: PalAutoHPRegenRate ≥ 2.0

## Related Guides

- [Palworld Beginner Guide](/posts/palworld/beginner-guide/) — Where to build your first base for maximum safety
- [Palworld Base Building Guide](/posts/palworld/base-building-guide/) — Complete base layout optimization
- [Palworld Best Pals Tier List](/posts/palworld/best-pals-tier-list/) — Combat and work Pal rankings
- [Palworld Pal Management Guide](/posts/palworld/pal-management-guide/) — When to keep, condense, or replace your defenders
