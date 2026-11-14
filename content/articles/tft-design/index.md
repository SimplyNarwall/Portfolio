---
title: "Thoughts on TFT's Design"
date: 2026-11-13
weight: 1
draft: false
summary: "Thoughts and open questions on Teamfight Tactics' design, from the perspective of a Grandmaster to Challenger player: line selection, public stats, pool information, matchmaking, and more."
tags: ["Design", "TFT"]
showTableOfContents: true
---

Some thoughts and open questions about TFT's design, grouped by topic. Most of these come from playing in Grandmaster - Low Challenger, so they lean toward that end of the game. The thoughts came entirely from me, but I used Claude to organize and help communicate my ideas more clearly. None of these are meant to be solid solutions. They're my personal thoughts on, and attempts to dissect, things I currently see as problems in TFT.

## What do "flexible" and "creative" actually mean?

These words get thrown around all the time, but they're really nebulous. Variety and monotony are much easier to define, so it might help to pin the fuzzier words to things that can actually be measured:

- **Flexibility:** how predictable is a player's final board from their early state? If you can call someone's endgame comp from their opener or first augment, the game isn't very flexible. Another angle: how do players who pivot place compared to players who stick to their line?
- **Variety vs. monotony:** how many distinct endgame boards show up in top 4, and how often does one player end up on the same endgame board across games?
- **Creativity:** maybe the feeling of making a choice the stats wouldn't have recommended, and having it work. Hard to measure without just asking players.

## Line selection, theorycrafting, and endgame boards

At high levels, you usually pick a line and follow it. But I don't think line selection itself is the problem. How you get to your endgame board is probably the most creative and skill-expressive part of TFT: reading your opener, items, augments, and the lobby, and finding the right path through the midgame. Midgame boards can be really varied and creative. Your endgame board often gets locked in almost immediately, but the path to get there is often very creative.

The problem is where those lines end up. Because stats are public, endgame boards are often the same handful of statistically strongest boards, so even after a creative midgame, the endgame can feel very monotonous. That's why I think line selection/flexibility and theorycrafting are really closely related, maybe even the same problem: the path is creative, but the destination is mostly solved ahead of time.

### Why flexibility matters

Flexibility is where a lot of skill expression comes from. If TFT were 100% rigid, players would just be waiting for the units they need to show up in their shop, which wouldn't be very fun. The more flexible the game is, the more players can make use of any unit in their shop, and the more they can play around bad luck.

There's a limit, though. If every unit were usable from every position, choosing units would feel meaningless, and the same problem would just show up with augments and items instead.

### Committed vs. flexible players

One of the biggest things about high-level TFT is that from stage 2, almost every player knows exactly what everyone else is going to play. Plans can go wrong, and people pivot in and out, but pivoting is generally considered a negative. That's exactly why a successful pivot feels so good. You took what's normally a negative-EV play, made it in the right spot, and it paid off. Your intuition beat the stat distribution.

But that makes me think line selection isn't actually that bad. In the opposite scenario, where pivoting is actually positive EV, everyone would be pivoting unpredictably, making it nearly impossible to play around other players' actions. It would feel more like a volatile stock market. A game where nobody knows what anyone else is doing, with no meta at all, would be chaotic and high variance, and extremely difficult for new players to get into. Some players should optimally have a clearly defined gameplan, and other players should be able to play flexibly around them. The question is how much.

Right now it feels like 7 to 8 players (basically everyone) have their gameplan decided from the start. Maybe it should be closer to 6 or 7. Then:

- **Should flexible players be on even footing with committed ones? Better? Worse?** If flexible play is better on average, everyone ends up in a game of chicken, waiting for someone else to lock in first, and at high levels flexibility would simply always be the right choice. I think flexibility should be, at its core, a comeback mechanic: a way to turn a spot that would normally be bad into a decent one, not something that beats a committed line on its own.
- **What would move the ratio?** The cost of changing direction (augment permanence, how permanent items are, how much value you lose selling), the reward for being uncontested (pool sizes, how much contesting hurts), and how much information players have (perfect scouting makes it easy to see who's committed).
- **When should players be forced into an endgame board?** They obviously shouldn't be switching boards every round. Pivoting should probably get more expensive as the game goes on, cheap early and costly late, with natural lock-in points around augments and the stage 4 rolldown. Since players are already committed in stage 2, pivoting is already negative-EV by stage 3, which suggests that curve might be too steep too early.

One tension: part of why pivots feel so rewarding is that they're rare and go against the odds. If pivoting becomes too easy, that feeling of accomplishment goes away too.

### Why lines lock in early

Part of what narrows the destinations is how changeable each piece of your board is:

- **Champions** are the most flexible. You can always roll for more.
- **Items** are mostly set. You usually can't change your components or finished items, though there are a few ways to do it a limited number of times per game. This has gotten much better over time.
- **Augments** are permanent. Once you have them, they're there forever.

Since augments are such a big part of your board's strength and you can't change them, your early augments narrow which endgame boards are realistically open to you, and switching later means ending up weaker than the player who stuck to their line. Suboptimal items do the same thing. If you find a good direction early, the game gets very simple.

One idea is making augments less set in stone, with some limited way to change them. That could make the path more flexible, but it has some problems:

- Returning rewards only really works for combat augments. Augments that give gold or items can't be taken back.
- It might make endgame boards even more similar, since everyone could steer toward the strongest board more easily.

### Theorycrafting and public stats

Playing creatively in the endgame at a high level doesn't really exist anymore. I think it used to, but now endgame boards are more of a stats-mashing contest over who can combine the things with the best numbers, since all the numbers are already out there. It makes the end of the game feel closer to a trivia game than a teambuilding game.

In a game with this many players, no one can out-theorycraft the whole community, and a lot of those players are probably brighter than any one person. The meta gets posted online, and pretty much everyone ends up on the same level of meta knowledge, apart from the very top, where Challenger players have their own intuition or study groups to min-max.

There are still rare chances to get ahead of the curve. At the start of Set 15, I noticed in the first patch that T-Hex was overtuned, before other players did and before it got buffed even more. But moments like that are uncommon. Trait Tracker and Trait Ladder augments might have created more of them, but now there are tools that solve the optimal boards for those too.

A big part of the payoff of creativity is the feeling of discovery, of being a pioneer. That's hard to get when so many eyes are on the same game and the community solves things so quickly. I don't think that's easily solvable in the modern climate.

The other side of this is that players need something to ground them. Not every player wants to theorycraft at all, especially new players, and they shouldn't have to. Being able to see the meta without playing 500 games is really healthy for the playerbase as a whole. The flip side is that if everything is already known, creative players don't get rewarded for their creativity. That's most true at the highest level of play, where things are the most optimized. At lower levels, you can probably get away with a lot more.

I'm not sure what the answer is. One thought: stats sites work because the same choice is worth about the same in every game, so it averages out. Things whose value depends more on the specific game (the lobby, what other people are playing, what's left in the pool) might be harder to solve ahead of time. But that probably means more variance, making the game both more luck based and harder to learn, which is unlikely to be worth the tradeoff.

Related: when I took a few months off TFT, it wasn't because games lacked variety. There's already a ton of variation between games. It was more that I'd learned so much that even with that much variety, games started to feel like going through the motions. Every game eventually gets to that point for a dedicated player, and honestly it's a strength of TFT's design that it took so long.

## Champions left in the pool

Scouting is an important skill in TFT, and showing pool counts would lessen part of it. But the part it removes is mostly counting copies, which is tedious rather than skillful. Scouting for items, positioning, and what people are building would still be vital.

The bigger reason is newer players. As far as I know, the game never explains why you shouldn't contest other players. Champion pools and pool sizes are core concepts that even lower-ranked players should understand, even if they don't have a friend to explain it. Right now you learn it from a guide, a friend, or losing a lot.

**The idea.** A simple ratio on the champion's info card (copies left in the pool out of the total pool size), which already holds a lot of information, plus a tooltip for newer players explaining that the ratio determines how likely they are to find that unit. Keep it general and readable rather than trying to show everything.

**Why not a simpler icon?** I've previously suggested a "wave" icon on champions that are currently very uncontested, but it has problems:

- Newer players might just buy every unit with the icon, whether or not it fits their board.
- As *you* buy the unit, it becomes more contested and the icon disappears, which is confusing. If something like this were used, it would make more sense to base it on how many copies other players hold, not how many are left in the pool.

In general, a simple yes/no signal tends to get followed blindly, while a number makes players think about it.

**Should players have perfect knowledge of the pool?** There's a debate about this. I personally think, why not? The information can already be found by scouting, so hiding it doesn't really test skill, it just takes time. And it better informs a player's decision to pivot, which ties directly into the flexibility discussion above: if pivoting depends on reading the lobby correctly, pool counts make that read easier. The honest counterpoint is that it takes away an edge experienced players currently have.

**Details for a deeper dive.** What exactly should count: copies in other players' shops, in your own shop, on boards, on benches? These matter for implementation, but the general idea comes first.

## Scouting and matchmaking

**Matchmaking** is random for good reason. If you knew who you were fighting next, the game would turn into a twitch-reflex contest, which isn't what TFT is trying to be.

I'd even wonder whether players should have perfect information on enemy boards and positioning at all. I don't think the end-of-round positioning contest really should be part of the game. The problem is that there are a lot of reasons you need to see enemy boards right now, like scouting champion counts and clarity: players should be able to see what others are using, so they understand what they're fighting and losing against. Hiding that could be especially detrimental to newer players who are still figuring things out. But if that positioning twitch reflex went away, matchmaking could theoretically be more round robin and avoid the feel-bad of matchmaking luck by making it more predictable and "fair".

I don't mean literal round robin, just matchmaking that's more uniform and predictable. It might still feel unfair sometimes, but it would at least feel fairer, especially in the late game, where fight order can be a huge swing in placements.

The two ideas really only work as a pair:

- **Predictable matchmaking on its own** brings back the problem it's trying to solve. If you know who you're fighting next, last-second repositioning against that specific player becomes even stronger.
- **Limited positioning information** is what makes predictable matchmaking work. Knowing your opponent but not their final positioning turns it into a mind game instead of a reflex test.

How much information players get matters a lot. If you can see an opponent's comp and how they've positioned before, but not their final positioning this round, good players can still read and predict, so it stays a skill. If you can't see anything, it's basically a coin flip. Some partial information is probably the sweet spot. Guessing is at least a mental skill test rather than a twitch-reflex one, which feels more in the spirit of TFT.

Some things to work through:

- **Readability.** Less visible information could make the game harder to follow for newer players, and for people watching streams or esports.
- **Eliminations.** Once players are knocked out, any fixed schedule has to adjust, with ghost fights or reshuffling.

## Feeling screwed after a loss

A lot of the time, losing can feel like you couldn't have done anything. Statistically that's obviously not true. There's no perfect player, and probably no perfect game of TFT has ever been played. But it can be really unclear why certain decisions were bad. That's why top players VOD review. Most players won't, and how they feel one second after a game ends is pretty much how they'll feel about that game overall.

The main things you can feel screwed by are items, rolldowns, matchmaking (see [Scouting and matchmaking](#scouting-and-matchmaking)), and augments.

**Items** have improved a lot. You only really feel screwed by items maybe 1 in 50 games now, and I think they've been handled really well, especially since many items can be played in place of others, something that's been getting better and better with every update.

**Rolldowns.** The community's understanding is that shops have some kind of pity or bad-luck protection, though how it works isn't public. There was a bug a while back that let players hit a 3-star Ryze in one shop, which people linked to it. In one set (I forget which), a lot of players, including top players, were talking about terrible rolldown luck, and a popular theory was a bug in that system, but a dev said there was no such bug. If that's true, I wonder what caused the sudden wave of bad-luck reports. Honestly, even I thought that something was bugged at the time just due to the volume of reports. Was there something about that set that unintentionally made rolls feel worse?

**Augments** can't be changed, so an early pick that doesn't work out stays with you the whole game (see [Line selection](#line-selection-theorycrafting-and-endgame-boards)).

## Other missing information

A lot of important information isn't directly visible in the game, especially for newer players, though even experienced players would use some of it. Some examples:

- Champions left in the pool (see the section above). Right now you have to scout other people's boards and estimate.
- Cashouts for some traits and augments. Can be found online, but not ingame.
- Damage taken from losing a round. I'm not sure about this one; I think the game might already show it somewhere, but I don't exactly recall.
- Probably many others I'm not thinking of.

There's also a lot of data that matters at high levels and basically just lives on websites: artifact stats, emblem stats, augment stats, comp stats, charm stats. Knowing or not knowing these can change a game a lot, and these days it feels less like intuition and more like having looked the numbers up ahead of time, which can feel bad.

I can see why some of this isn't in the game, though. Some of it only really matters to a small number of high-level players, and for the playerbase as a whole it might not seem that important. Adding all of it would clutter the UI and make the game less inviting to newer players. An emblem's average placement on a unit, for example, matters a lot at high levels, but it isn't something you'd expect to see in game.

## Stage by stage

**Opener.** Rule of thumb: match pairs and build the strongest board you can at any given time. Some players go for econ, but I find that pretty greedy and perform better just having a stronger board. I'd only make econ with no pairs and no strong early units worth keeping.

**First augment.** Depends on the meta, but usually econ or hero/lock-in augments. If you find a good direction early, the game gets very simple.

**Stage 2.** Strongest board, even if I'm not streaking. HP is very important, and I think streaking is a little overrated, though if you reach the end of the stage on a streak you obviously want to keep it. Levels usually within the range of 3/4/5. Level 6 on a hard-forced win streak is rare, and I think it's usually a mistake.

**Carousel.** It has a nice comeback mechanic built in, since weaker players pick first. TFT has gotten a lot better about items in general: there's still variance, but the item system is balanced well enough that most players can work around it in most games. I recall a dev specifically stating they wanted to remove it due to the twitch reflex nature of picking your item, and it has been removed a few times but always came back.

**Neutral rounds.** I recall seeing a dev speak on how they wanted to remove Neutral rounds, and their reasoning as to why they're still here. My memory is a little fuzzy, but one reason I recall is that they give players a breather, which is important. But losing to them feels really bad, while winning just feels like the norm. The good outcome feels normal and the bad one feels bad, so the overall experience ends up negative. Some quick thoughts/questions/reflections:

- Is there a reason players should be punished for a board that's too weak here, or is it just filling the gap?
- What would TFT lose if it were just an empty round? Players would probably find the wait boring.
- What if it were a show match? Then players would feel like the outcome didn't matter at all.
  - A show match with real effects is a bigger problem, since stronger boards would get even more tempo and shift the meta a lot.

Neutrals do make winning feel like it matters, even when it's expected most of the time.

**Stage 3.** Level 5 on 1-cost reroll, 6 to 7 otherwise. Feels like cruise control: what you have at the start of the stage is likely what you'll play the whole stage. That might be fine, since the later stages are intense. I usually use this time to scout and figure out my endgame plan.

**Stage 4.** Level 6 on 1 or 2-cost reroll, level 7 on 3-cost reroll, 8 otherwise. The meat and potatoes of the game and probably the stage people talk about most. Your board is expected to be locked in, big rolldowns happen, and you get your final augment. Most people would call this the climax of a TFT game. Does it have to be? I think it's in a fine spot as is.

**Stage 5 to endgame.** If your board isn't online here, you're done. Some win-streaking fast 9 boards come online at this stage and will finish you off if you aren't already out.

## Other thoughts

**Metas.** This is probably what high-level players talk about most. A meta can get stale or unbalanced, but when people call a meta "bad," they usually mean it isn't very skill expressive: a few outliers should almost always be taken, not getting them means losing most of the time, and even better players have few ways around that luck.

**Lower vs. higher tiers.** There's a big gap between the general playerbase and high-level players. Meta perception is really different, and simpler comps are seen as much stronger at lower tiers (I remember a friend complaining about Yordles when they were mediocre). Level distribution is different too, and a lot of lower-tier players like to force the same comp over and over. Honestly, they should be able to. It shouldn't be viable at higher ranks, or the game becomes a slot machine. But at what rank should forcing stop being viable?

**Retention.** The meta and bug issues are mostly about retaining players rather than gaining new ones. Part of me wonders how important retention is, since a game can be really fun for a while and then fall off, and that's fine. But as a company, it's clearly important. I think Riot has caught onto this by making the early patches of a set higher variance and more fun, then more balanced and geared toward returning players later. Of course, that assumes they know how a patch will play out ahead of time, which they can't fully.

**New player experience.** I suspect it's what Riot worries about most. There's a lot going on, more than a classic tutorial could teach intuitively, so it can be hard to get into, though TFT has gotten much better about this over time. It's been a long time since I was a new player, and even my friends are mostly Platinum to Diamond now, so I don't have much insight here.

**Engine bugs.** There are a lot right now, and they affect players at every level, but I assume they're already known and being worked on.

### Things I haven't thought much about

- Positioning (never been my strength, and it feels nebulous to me)
- Game length, which I think Riot has been trying to shorten recently.
- Combat readability (not really a visuals kind of guy)
- Other game modes. Haven't played them much personally, so I couldn't really say. I do find Tocker's Trials pretty interesting though, but it's missing a lot of replayability for something so short, so it's clearly in its early stages.
