---
title: "DOORS Sprint Guide — When Walking Beats Sprinting & Stamina Management (2026)"
description: "Stop dying because you sprinted at the wrong time. Learn DOORS sprint stamina drain/regen mechanics, how sprinting attracts Rush, Ambush, and Figure, and a movement decision framework for every floor and encounter."
date: 2026-08-07
lastmod: 2026-08-07
draft: false
author: "Alex Turner"
tags: ["DOORS", "Roblox", "Movement", "Stamina", "Strategy"]
categories: ["Roblox Guides"]
games: ["DOORS"]
cover:
  image: "/cover-image/doors-sprint-stamina/cover.webp"
  alt: "DOORS sprint and stamina management guide cover"
  caption: "Know when to sprint and when to walk"
faq:
  - question: "Does sprinting in DOORS attract entities?"
    answer: "Yes. Sprinting is the loudest movement action in the game. Rush and Ambush are drawn to sprinting players who are still in the open when the screech starts. Figure tracks sprinting footsteps from up to 50 studs away, even during its walk phase. The audio footprint of sprinting is roughly three times larger than walking and ten times larger than crouch-walking."
  - question: "How fast does stamina drain when sprinting in DOORS?"
    answer: "Stamina drains from 100% to 0% in roughly 6 seconds of continuous sprinting. Partial sprinting (tapping shift) extends this to about 10-12 seconds. Stamina regenerates from 0% to 100% in roughly 4 seconds of not sprinting, meaning the regen rate is about 50% faster than the drain rate. This makes burst-sprinting — two seconds on, one second off — the most stamina-efficient movement pattern."
  - question: "Should I sprint during a Seek chase?"
    answer: "Yes, but with control. Seek's speed scales to your position, so sprinting does not outrun it — it only helps you reach turns and exits faster. However, sprinting into debris during a Seek chase causes a stagger animation that costs more time than walking around it. The rule: sprint on clear straightaways, release sprint when navigating debris fields, and never sprint through the maze section. For full chase mechanics, see our Seek chase guide."
  - question: "Can you sprint during Figure encounters?"
    answer: "Only as a last resort when Figure has already detected you and you need to break line of sight. Sprinting during Figure's listen phase is instant death — it detects sprinting footsteps at maximum range. During Figure's walk phase, sprinting extends your detection radius to roughly 50 studs. If Figure has not detected you, never sprint. If it has detected you, sprint to the farthest corner, break line of sight behind two shelf rows, and crouch for 15 seconds."
  - question: "What's the fastest way to move through The Hotel without wasting stamina?"
    answer: "Burst-sprint between doors. Walk into a new room, identify the exit door and nearest closet, then sprint to the exit. This pattern — walk for awareness, sprint for distance — keeps stamina above 50% at all times and ensures you always have a sprint reserve when Rush or Ambush cues play. Walking through rooms also gives you time to read Dupe door numbers and spot Snare traps."
  - question: "Is walking actually faster than sprinting in some situations?"
    answer: "Yes, in three specific cases. First, in high-debris rooms where sprinting triggers staggers that cost more time than walking. Second, during Figure encounters where sprinting triggers detection, forcing you to waste 15+ seconds hiding. Third, in dark rooms with Screech active, where sprinting past the whisper means you miss the 'psst' cue and take damage. In all three cases, walking is the faster path to survival."
---

You sprint down the hallway because the doors look identical. Door 43, door 44, door 45 -- they blur together, and your brain tells you speed equals safety. The faster you clear rooms, the fewer entities spawn. That is the logic, anyway. Then the lights flicker. You are mid-sprint, stamina bar at 20%, and the nearest closet is three doors behind you. Rush arrives before you can turn around.

That death was not caused by Rush. It was caused by the sprint key.

Most DOORS players treat sprinting as the default movement state. Hold shift. Go fast. Save time. The game even gives you a stamina bar, which suggests sprinting is a resource to be managed, not a trap to be avoided. But here is the thing the tutorial never tells you: sprinting is the single most dangerous action you can take in DOORS. It burns your stamina reserve. It broadcasts your position to every audio-tracking entity in the room. And it locks you into a movement rhythm that makes you miss the audio cues that keep you alive.

This guide is about when to press shift and when to let go. Not general movement tips. Not entity counters. The specific mechanics of sprint stamina, the audio consequences of running, and the decision framework that tells you whether to sprint or walk in every situation the game throws at you.

## How Sprint Stamina Actually Works

DOORS does not document its stamina numbers anywhere in the game. The bar sits in the corner of your screen, a thin green line that depletes and refills, and most players never think about it beyond "green means I can sprint." But the numbers matter.

Continuous sprinting drains your stamina bar from full to empty in roughly 6 seconds. That is not a lot of time. If you sprint from one end of a long hotel hallway to the other, you arrive with maybe 10% stamina left. If Rush cues at that exact moment, you cannot sprint to a closet. You walk. And walking to a closet during a Rush cue is a death sentence at any door past 50.

Stamina regeneration is faster than drain, which is the one piece of good news. Going from 0% to 100% takes roughly 4 seconds of not sprinting. That means the regen rate is about 50% faster than the drain rate. This ratio is the foundation of every effective movement strategy in the game: you should never be at zero stamina. Ever. If your bar hits empty, you made a mistake somewhere in the last 6 seconds.

The practical rule: keep your stamina above 50% at all times. That gives you roughly 3 seconds of sprint in an emergency. Three seconds is enough to reach any closet in a standard hotel room. Three seconds is enough to clear a debris field during a Seek chase. Three seconds is the difference between dying to Rush and hearing it pass harmlessly while you sit in a closet.

Burst-sprinting is the technique that makes this sustainable. Sprint for two seconds. Release for one second. Sprint for two seconds. Release for one. This pattern keeps your stamina oscillating between roughly 60% and 90%, which means you always have a reserve and you are still covering ground faster than walking. The two-one rhythm takes practice to internalize, but once it becomes muscle memory, you stop thinking about the stamina bar entirely.

## The Audio Cost of Sprinting

Stamina is not the only currency you spend when you press shift. Sprinting also generates noise. In DOORS, noise is a death sentence.

Every movement action in the game has an audio footprint. Crouch-walking is nearly silent. Walking produces moderate footstep sounds that entities can detect at close range. Sprinting produces loud, rapid footsteps that broadcast your position across an entire room. The detection radius for sprinting footsteps is roughly three times larger than walking and ten times larger than crouch-walking.

This matters because three of the deadliest entities in DOORS track players by sound:

**Rush and Ambush** do not hunt by audio in the same way Figure does, but the game's entity spawn logic is sensitive to player activity. Sprinting through rooms increases the likelihood of triggering entity events. The exact mechanic is not publicly documented, but experienced players consistently report fewer Rush and Ambush spawns when they walk through rooms and sprint only between them. Whether this is a real spawn-rate modifier or simply the fact that walking gives you more time to hear cues early, the outcome is the same: walking players survive more often.

**Figure** is the most obvious case. Figure is blind and navigates entirely by sound. Sprinting near Figure extends your detection radius to roughly 50 studs during its walk phase. During its listen phase, sprinting is detected instantly at any range. The beginner-mistakes guide already covers this briefly, but the deeper point is that sprinting near Figure does not just increase your risk of detection -- it guarantees detection. Sprinting during Figure's listen phase is not a risk. It is a death. The only exception is when Figure has already detected you and you are sprinting to break line of sight, and even then, you are sprinting to survive a mistake, not executing a strategy.

**Screech** is the indirect victim of sprinting. Screech spawns in dark rooms and whispers "psst" before attacking. If you are sprinting through a dark room, your own footstep audio masks the whisper. You miss the cue. Screech bites you. You take damage and panic, which often leads to sprinting into a worse threat. Walking through dark rooms lets you hear the whisper, locate Screech, and neutralize it without taking damage.

The audio cost of sprinting means that every time you press shift, you are making a trade. Speed for safety. Distance for awareness. You need to know which trade is worth making in each situation.

## Failure Analysis: How Panicked Sprinting Kills You

Let me walk through the five most common sprint-related deaths. These are not hypothetical. Every one of them happens hundreds of times a day across DOORS servers.

**Death 1: The empty stamina bar.** You sprint through a hallway because it feels efficient. Stamina hits zero. Rush cues. You walk toward the nearest closet, but the closet is seven steps away and Rush travels the entire map in 3 to 4 seconds. You die with the closet interaction prompt visible on your screen. The fix: never let stamina drop below 50%. If you had walked the last two seconds of that hallway, you would have had sprint available when Rush cued.

**Death 2: The Figure detection chain.** You are in the Library at Room 50. You have placed five books. You get impatient and sprint between shelves to save time. Figure hears you. You sprint away from Figure. Figure hears the sprinting, updates your position, and charges. You sprint again. Figure hears you again. This chain continues until Figure corners you. The fix: walk and crouch-walk at all times near Figure. If detected, sprint to break line of sight, then freeze. Do not keep sprinting after you break line of sight. Figure tracks the last sound it heard. If you stop making sound, Figure stops chasing.

**Death 3: The Ambush closet sprint.** You hear a distorted screech. You sprint to a closet. You wait one pass. You step out. You hear the second pass and sprint back to the closet, but the interaction prompt is slow. Ambush kills you in the open. The fix: if you sprinted to the closet during the Ambush cue, you were already sprinting when you should have been walking. The Ambush cue gives you more time than Rush. You do not need to sprint to the closet. Walk. Save your sprint for the situation where you actually need it.

**Death 4: The Seek debris stagger.** You are in a Seek chase. The hallway is cluttered with chairs and broken wood. You hold sprint. You hit a chair. The stagger animation plays for a full second. Seek gains distance. You panic and sprint harder, hitting more debris. Seek catches you. The fix: in Seek chases, sprint on clear straightaways and release sprint when navigating debris. Walking around a chair is faster than sprinting into it and staggering.

**Death 5: The dark room Screech-miss.** You sprint through a dark room to minimize exposure time. Screech whispers. You do not hear it over your own footsteps. Screech bites you for 40 damage. You are now at low health, and the next entity that hits you finishes the run. The fix: walk through dark rooms. The whisper is audible if you are not sprinting. Looking at Screech takes half a second and costs zero health.

## The Movement Decision Framework

Here is the core of this guide. For every situation in DOORS, you need to know whether to sprint or walk. The answer is not always obvious.

### Standard Hotel Rooms (Doors 1-99)

Walk into the room. Identify the exit door. Identify the nearest closet. Then sprint to the exit.

This pattern -- walk for awareness, sprint for distance -- is the foundation of safe hotel navigation. Walking into the room gives you two seconds to read the room. You spot Dupe numbers on the doors. You check for Snare on the floor. You locate the closet position. Then you sprint to the exit with full stamina and full information.

The only exception: if you are in a room with no closets, do not sprint. Walk to the exit and be ready to sprint back to the previous room if Rush cues. Sprinting away from the previous room when you have no closet is gambling with your run.

### The Mines (Doors 101-200)

The Mines change the sprint calculus because the rooms are larger, darker, and more densely packed with hazards. Giggle hangs from the ceiling. Snare covers the floor. Grumble patrols wide areas with audio detection.

The rule for The Mines: walk through rooms, sprint between them. The room interiors are too dangerous for sprinting. You need to watch the ceiling for Giggle, the floor for Snare, and the audio cues for Grumble. Sprinting through a Mines room means you will miss all three. You will step on Snare. You will walk under Giggle. You will sprint into Grumble's detection radius.

Between rooms, sprinting is fine. The corridors connecting Mines rooms are short and generally hazard-free. Sprint them. Enter the next room walking. This burst-walk pattern keeps you alert in the danger zones and fast in the safe zones.

### The Backdoor

The Backdoor is a sprint trap. The rooms are close together, which makes sprinting feel efficient, but the entity spawn rates are higher and the reaction windows are shorter. A-60 and A-120 have faster approach times than Rush and Ambush. If you are sprinting through Backdoor rooms, you will not hear the audio cues until the entity is already on top of you.

The rule: walk through every Backdoor room. Sprint only when you are certain the room is clear and you have identified the nearest hiding spot. The Backdoor punishes speed. It rewards patience. Treat it like a slow, deliberate crawl, not a sprint race.

### The Outdoors

The Outdoors are the one place where sprinting is genuinely your friend. The open terrain means there are fewer walls to block audio, but also fewer hazards to trip over. The main threats in The Outdoors are environmental -- falling rocks, water hazards, Snare patches -- and you can see them coming from a distance.

Sprint between cover points. Identify the next safe position, sprint to it, stop and scan for the next one. The Outdoors reward burst movement. Walk-scan, sprint-move, walk-scan. This rhythm keeps you moving fast while maintaining awareness of the environment.

The one exception: if you hear Grumble footsteps, stop sprinting immediately and crouch-walk. Grumble's audio detection radius is large enough that sprinting anywhere in the same outdoor zone will draw it to your position.

### Figure Encounters (Room 50, Room 100)

Never sprint unless Figure has already detected you.

This is the simplest rule in the framework and the one players break most often. The Library at Room 50 takes 5 to 8 minutes of crouch-walking. That is a long time to resist the sprint key. Players get impatient. They sprint between shelves to save five seconds. Figure hears them. The run ends.

The protocol: crouch-walk at all times. Track Figure's 11-second cycle (walk phase, listen phase, repeat). Move only during the walk phase. Freeze during the listen phase. If Figure detects you, sprint to the farthest corner, break line of sight behind two shelf rows, and crouch for 15 seconds. Do not sprint again after breaking line of sight. Figure tracks the last sound it heard. If you stop making sound, Figure stops chasing.

For the full Figure encounter breakdown, including the 11-second cycle and book-by-book Library strategy, read the [Figure Survival Protocol](/posts/doors/figure-survival-protocol/).

### Seek Chases

Sprint, but with discipline.

Seek chases are the one situation where sprinting is mandatory. Seek's speed scales to stay just behind you, so walking means you fall behind the speed curve and get caught. But sprinting recklessly gets you killed for a different reason: debris stagger.

The rule for Seek chases: sprint on clear straightaways, release sprint in debris fields, and never sprint through the maze section. The maze punishes speed. You need to read the room layout, identify the correct path, and walk through doorways. Sprinting in the maze means you hit walls, miss turns, and loop back into rooms you already cleared.

For the full Seek chase breakdown, including room patterns, speed thresholds, and the three-phase framework, read the [Seek Chase Complete Guide](/posts/doors/seek-chase-complete-guide/).

### Multi-Entity Overlaps

When two or more threats are active simultaneously, sprinting is usually the wrong response. The entity priority system -- Rush before Ambush before Screech before Eyes -- requires you to stop and think, not sprint and hope.

If Rush cues while you are managing a dark room with Screech, sprint to the closet. That is the one acceptable sprint in a multi-entity situation. But once you are in the closet, stop. Wait. Do not sprint out of the closet the moment Rush passes because Ambush might be on its second pass or Screech might still be active. The closet is safe. Stay in it until you have confirmed all threats are clear.

For the full entity priority system and counter-strategies, read the [Entity Defense and Counter Guide](/posts/doors/entity-defense-counter-guide/).

## Counterintuitive Recommendations

These are the things that sound wrong until you try them. They contradict the "hold shift and go fast" instinct that every new DOORS player develops. Test them in a low-stakes run. You will be surprised.

**Walk through dark rooms, not sprint.** Sprinting through a dark room takes two seconds. Walking takes five. The three seconds you save by sprinting are not worth the 40 damage you take from missing Screech's whisper. You cannot outrun Screech. You can only look at it. Walking gives you the audio clarity to hear the whisper and the visual calm to sweep your camera and find the face. Sprinting gives you tunnel vision and a health bar that drops for no apparent reason.

**Let your stamina hit zero intentionally.** This sounds insane. But there is one situation where zero stamina is useful: when you are practicing burst-sprinting. Go into a private server. Sprint until your stamina hits zero. Watch how long it takes to regenerate. Feel how slow you move with no sprint available. Internalize that vulnerability. Players who have never experienced zero stamina in a safe environment will panic when it happens during a live run. Players who know exactly how zero stamina feels will stay calm and walk to the nearest closet without wasting mental energy on the green bar.

**Sprinting to the exit door during a Seek chase is often slower than walking.** The final sprint corridor in a Seek chase is straight, yes. But it is also loaded with falling chandeliers and collapsing floor sections. Sprinting into a chandelier drop zone staggers you. Sprinting onto a collapsing floor section drops you. Walking through the same corridor lets you read the ceiling and floor, dodge the hazards, and reach the exit door with zero staggers. The chandelier stagger costs roughly one second. The floor collapse costs roughly two. Walking around both hazards costs less than one second combined. You do the math.

## Building the Sprint Discipline Habit

Knowing when to sprint is not enough. You need to rewire the instinct that says "hold shift at all times." Here is a training protocol that works.

**Phase 1: Unbind sprint for five runs.** Go into your settings. Unbind the sprint key. Play five runs without sprinting at all. You will die more. That is the point. You are learning how much ground you can cover by walking and how much time you actually have to react to entity cues. Most players are shocked by how far they get without sprinting. The hotel is not as long as it feels when you are sprinting through it.

**Phase 2: Sprint only between rooms.** Rebind sprint. For the next five runs, sprint only between rooms. Walk through every room interior. This teaches the walk-for-awareness, sprint-for-distance rhythm. By the end of five runs, it should feel natural.

**Phase 3: Burst-sprint everywhere.** For the next five runs, use the two-one burst rhythm everywhere. Sprint for two seconds, release for one, repeat. This teaches stamina management at the mechanical level. Your thumb learns the rhythm. Your eyes stop checking the stamina bar.

**Phase 4: Contextual sprinting.** Now you are ready for the full decision framework. Sprint when the situation calls for it. Walk when the situation calls for it. Trust your judgment. You have internalized the mechanics.

## Related Guides

- [Seek Chase Complete Guide](/posts/doors/seek-chase-complete-guide/) -- full chase mechanics, room patterns, and speed thresholds
- [Figure Survival Protocol](/posts/doors/figure-survival-protocol/) -- the 11-second cycle and book-by-book Library strategy
- [Ambush Protocol](/posts/doors/ambush-protocol/) -- how to tell Rush from Ambush by sound
- [Entity Defense and Counter Guide](/posts/doors/entity-defense-counter-guide/) -- entity priority system and item-to-threat matchups
- [Beginner Mistakes Guide](/posts/doors/beginner-mistakes-guide/) -- 10 common deaths and how to fix them
- [The Mines Adaptation Guide](/posts/doors/the-mines-adaptation-guide/) -- movement adjustments for Mines hazards
- [The Backdoor Complete Guide](/posts/doors/the-backdoor-complete-guide/) -- slow-paced survival in the Backdoor