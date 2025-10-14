---
title: "Master Dancer"
weight: 50
draft: false
summary: "A VR experienced which aims to teach the player about Loie Fuller, and to become a Master Dancer"
tags: ["Design"]
---

<video width="640" height="360" controls="">
  <source src="MD demo.mp4" type="video/mp4" />
  Your browser does not support the video tag.
</video>

## Team Size/Time constraint
- Worked as the lead of design in a team of 9, starting in Oct 2024, currently ongoing.

## What I did
- Lead all design decisions, working in several design disciplines such as Mechanics, Technical, UX, QA etc.
- Authored 20+ design documents, including Gameplay Loops, Feature Breakdowns, Asset Lists, etc.
- Worked in Unreal Engine to implement and balance level designs

## Game Overview
- In Master Dancer, you meet the famous dancer Loïe Fuller, the first to integrate technology into modern dance. As a player, you engage in action games to learn her movement principles and, guided by Virtual Loïe, explore her world. You will use modern VR technology to create your own unique dance, becoming a Master Dancer yourself!

## Star Maker
Star maker is one of the minigames meant to teach players dance principles. In this game, players must hit orbs flying at them towards targets in time with the music. The core design pillars of Star Maker are to teach players to do strong, direct movements, have players feel in tune with the music, and to be very forgiving in gameplay.

### Notable Features
- Designed an orb trajectory prediction system so that the orb hits targets when it appears to from the player's perspective. 
- Designed an aim assist feature to make game feel more satisfying. The strength is linearly curved so that wildly inaccurate hit will still be very off, while closer hits will hit the target. Adjusted aim assist strength through multiple playtest sessions.
- Designed a music looping system in order to give players multiple tries, reducing frustrayion while maintaining the musicality of the game.

## Music Roundabout
Music Roundabout (called Music Game while in development) is another minigame meant to teach players dance principles. In this game, players will activate orbs which rotate around them, creating a melody. The core design pillars of Music Roundabout are to teach players twisting motion, as well as a light tapping motion. In addition, players should feel as though they are creating music as they play.

### Notable Features
- Designed an orb charging system where players had to follow the rotating orb with their hand to incentivize players to twist their hips naturally.
- Designed visual indicators for players to know when to activate orbs, even with no sound (Although, sound was of course vital for this minigame).
- Chose to limit the arc of the orb, from traversing in a full circle to a half circle, to prevent players from getting dizzy and tangled in the VR headset's wire.

## Examples of Work

- Mockup/Art Reference for some of the tutorial systems.
<picture>
  <img src="Tutorial Miro.png" width="960" height="540">
</picture>

- Art reference board for the "Hub Room" of the game.
<picture>
  <img src="Hub Room Art Board.png" width="960" height="540">
</picture>

- Flowchart of game loop for Music Roundabout
<picture>
  <img src="Music Game Game Loop.png" width="960" height="540">
</picture>

- Detailed breakdown of Music Roundabout
<embed src="D.d.2. Music Game Overview v2.docx - Google Docs.pdf" type="application/pdf" width="892" height="842"/>

