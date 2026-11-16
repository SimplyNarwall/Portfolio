---
title: "Thoughts on TFT's Design"
date: 2026-11-13
weight: 1
draft: false
summary: "A Unity prototype of a champion pool indicator, plus working notes on Teamfight Tactics' design from a Grandmaster to Challenger player: flexibility, public stats, matchmaking, and more."
tags: ["Design", "TFT", "Unity"]
showTableOfContents: true
---

Some thoughts and open questions about TFT's design, grouped by topic. Most of these come from playing in Grandmaster - Low Challenger, so they lean toward that end of the game. The ideas are all mine; I used Claude to help organize and communicate them clearly.

Below is a quick prototype of one idea, followed by my working notes on TFT's design. The notes are exploratory and not meant to be solid solutions; the prototype is what it looks like when I take one of them further.

## Prototype: pool size indicator

<video src="pool-indicator.mp4" controls muted loop playsinline autoplay preload="metadata" style="width:100%;border-radius:8px"></video>

A quick Unity mockup of one idea from these notes: showing how many copies of a champion are still available. Selecting a champion shows its remaining copies out of the total pool size, and the number updates live as units are rolled, bought, or adjusted. Hovering the number explains what it means for your shop.

### Why show pool counts

Scouting the pool is a real skill in TFT, and showing pool counts would remove part of it. Scouting for items, positioning, and what people are building would still matter just as much, but counting copies would no longer separate experienced players from newer ones.

The bigger reason is newer players. As far as I know, the game never explains why you shouldn't contest other players. Champion pools and pool sizes are core concepts that less involved players should understand, even if they don't have a friend to explain it. Right now you learn it from a guide, a friend, or losing a lot.

**Should players have perfect knowledge of the pool?** This is the real debate. One strong counterargument is that perfect information can be a problem in itself: if everyone knows exactly what's left, everyone tends to make the same rational decisions, and lobbies get more uniform. Experienced players can already scout an approximate pool count, so the question is whether streamlining the new player experience is worth narrowing that gap. Put another way: is counting the pool a skill TFT should be testing?

My view is that while scouting is an important skill, it's equally or more important for newer players to have something to point to when they can never seem to hit their units. Right now, many of them don't even know the pool exists. Pool counts also better inform a player's decision to pivot, which ties into the flexibility discussion below: if pivoting depends on reading the lobby correctly, pool counts make that read easier.

**Details for a deeper dive.** What exactly should count: copies in other players' shops, in your own shop, on boards, on benches? These matter for implementation, but the general idea comes first.

### Design decisions

**A number instead of an icon.** My first idea was an icon marking champions that are currently uncontested. I dropped it for two reasons. Newer players might buy any unit with the icon on it, whether or not it fits their board. And the icon would pop in and out as players reroll and buy, which is visually jarring.

**Updating on a delay.** A ratio is less jarring, but it still changes a lot, especially during rolldowns. A number bouncing up and down draws the eye in a way that isn't wanted, so in the real game it should probably update every second or few seconds rather than on every action. (The mockup updates instantly so the effect is easy to see.)

**Placing it on the info card.** There's a good argument against this: the info card shows information about that specific copy of a champion, while the pool count applies to every copy. I put it there anyway because the card already has a precedent for detailed numbers, and for tooltips you can hover to learn what they mean. Putting counts in the shop instead would mean five constantly changing numbers on screen, which feels like too much visual overload. There aren't many other places for detailed champ info to show up.

## Working notes

Everything below is my working notes: half-formed ideas, open questions, and things I'm still thinking through.

### What do "flexible" and "creative" actually mean?

These words get thrown around all the time, but they're really nebulous. Variety and monotony are much easier to define, so it might help to pin the fuzzier words to things that can actually be measured:

- **Flexibility:** how predictable is a player's final board from their early state? If you can call someone's endgame comp from their opener or first augment, the game isn't very flexible. Another angle: how do players who pivot place compared to players who stick to their line?
- **Variety vs. monotony:** how many distinct endgame boards show up in top 4, and how often does one player end up on the same endgame board across games?
- **Creativity:** maybe the feeling of making a choice the stats wouldn't have recommended, and having it work. Hard to measure without just asking players.

### Line selection, theorycrafting, and endgame boards

At high levels, you usually pick a line and follow it. But I don't think line selection itself is the problem. Your endgame board often gets locked in almost immediately, but the path there is probably the most creative and skill-expressive part of TFT: reading your opener, items, augments, and the lobby, and finding the right route through the midgame.

The problem is where those lines end up. Because stats are public, endgame boards are often the same handful of statistically strongest boards, so even after a creative midgame, the endgame can feel very monotonous. That's why I think line selection/flexibility and theorycrafting are really closely related, maybe even the same problem: the path is creative, but the destination is mostly solved ahead of time.

#### Why flexibility matters

Flexibility is where a lot of skill expression comes from. If TFT were 100% rigid, players would just be waiting for the units they need to show up in their shop, which wouldn't be very fun. The more flexible the game is, the more players can make use of any unit in their shop, and the more they can play around bad luck.

There's a limit, though. If every unit were usable from every position, choosing units would feel meaningless, and the same problem would just show up with augments and items instead.

#### Committed vs. flexible players

From stage 2, almost every high-level player knows exactly what everyone else is going to play. Plans go wrong and people pivot in and out, but pivots are rare and generally avoided. There aren't public stats on pivoting, but across thousands of games at Grandmaster and Challenger, that tells me most top players see it as negative EV. In the right spot, though, pivoting is the positive-EV play, and nothing tells you when you're in that spot. Pivoting there means going against the general consensus and trusting your own intuition, which is exactly why a successful pivot feels so good. I think moments like that are some of the most engaging in TFT.

But that makes me think line selection isn't actually that bad. If pivoting became positive EV in general, a few things would go wrong. Pivots would feel less engaging, since they'd be the expected play instead of a read that beats the odds. Everyone would be pivoting unpredictably, making it nearly impossible to play around other players' actions, so the game would feel more like a volatile stock market: chaotic and high variance. And it would be overwhelming for newer players, who'd have more to consider at more stages of the game. Optimally, some players should have a clearly defined gameplan, and other players should be able to play flexibly around them. The question is how much.

Right now it feels like 7 to 8 players (basically everyone) have their gameplan decided from the start. Maybe it should be closer to 6 or 7. That raises a few questions:

- **Should flexible players be on even footing with committed ones? Better? Worse?** If flexible play is better on average, everyone ends up in a game of chicken, waiting for someone else to lock in first, and at high levels flexibility would simply always be the right choice. I think flexibility should be, at its core, a comeback mechanic: a way to turn a spot that would normally be bad into a decent one, not something that beats a committed line on its own.
- **What would move the ratio?** The cost of changing direction (augment permanence, how permanent items are, how much value you lose selling), the reward for being uncontested (pool sizes, how much contesting hurts), and how much information players have (perfect scouting makes it easy to see who's committed).
- **When should players be forced into an endgame board?** They obviously shouldn't be switching boards every round. Pivoting should probably get more expensive as the game goes on, cheap early and costly late, with natural lock-in points around augments and the stage 4 rolldown. Since players are already committed in stage 2, pivoting is already negative-EV by stage 3, which suggests that curve might be too steep too early.

#### Why lines lock in early

Part of what narrows the destinations is how changeable each piece of your board is:

- **Champions** are the most flexible. You can always roll for more.
- **Items** are mostly set. You usually can't change your components or finished items, though there are a few ways to do it a limited number of times per game. This has gotten much better over time.
- **Augments** are permanent. Once you have them, they're there forever.

Since augments are such a big part of your board's strength and you can't change them, your early augments narrow which endgame boards are realistically open to you, and switching later means ending up weaker than the player who stuck to their line. Suboptimal items do the same thing. If you find a good direction early, the game gets very simple.

Set 8's hero augments are the clearest example. Taking one meant you had to play that champion, or you'd lose the augment's benefit entirely. That downside was so large that pivoting away was basically impossible, and adding lots of rerolls didn't fix it. It created three problems (among others):

1.  Taking the augment gave you one copy of the champion, but you usually still needed two more to upgrade it, even for "support" hero augments. If you didn't hit them, you were screwed. The reverse was true too: if you played around getting a specific hero augment and then weren't offered it, you were just as screwed.
2.  If hitting was too easy, everyone could force the best comp available.
3.  Some players liked being able to streamline a game around one champion, but not everyone wanted to do it every game. (Later sets improved this by making hero augments not guaranteed every game.)

It still happens in more modern sets. In Set 15, Deadlier Caps was technically a generic augment, but it was so much weaker on other lines that taking it all but locked you into Veigar, or, in a pinch, Lissandra, since Ziggs in a prismatic lobby was nearly impossible without an econ start.

To a lesser degree, this is true of almost every augment. Most comps want some mix of items, econ, or combat augments, and all of those are shaped by choices made in stage 2, so your options narrow as the game goes on. The Ziggs case above shows this: Deadlier Caps is an item augment that should theoretically fit an AP carry like Ziggs, but because Ziggs needed an econ start, clicking an item augment in stage 2 made him too expensive to play. Honestly, that's normal and good: by the endgame, players should have narrowed in on a comp. The problem is that the narrowing is too sharp. Being down even one augment is a huge liability for your final board, and that augment could be the very first one you pick in the game, if you don't have a line selected by early stage 2.

One idea I've toyed with is making augments less set in stone, with some limited way to change them late in the game. To be clear, I don't think it's a good idea as it stands. It would be hard to implement, I haven't thought it through, and it runs into a huge number of issues, for example:

- Returning rewards only really works for combat augments. Augments that give gold or items can't be taken back.
  - On top of that, simply swapping these augments out is a terrible idea. It makes early combat augments feel horrendous, since players who take them go most of the game with fewer resources than everyone else.
- It might make endgame boards even more similar, since everyone could steer toward the strongest board more easily.

Those are just the first few problems that come to mind. Unless every one of them got solved out very thoroughly, I think it would create more problems than it fixes.

#### Theorycrafting and public stats

Playing creatively in the endgame at a high level doesn't really exist anymore. I think it used to, but now endgame boards are more of a stats-mashing contest over who can combine the things with the best numbers, since all the numbers are already out there. It makes the end of the game feel closer to a trivia game than a teambuilding game.

With this many players, no one can out-theorycraft the whole community. The meta gets posted online, and nearly everyone ends up with the same meta knowledge, apart from the very top, where Challenger players rely on their own intuition or study groups to min-max.

There are still rare chances to get ahead of the curve. At the start of Set 15, I noticed in the first patch that T-Hex was overtuned, before other players did and before it got buffed even more. But moments like that are uncommon. Trait Tracker and Trait Ladder augments might have created more of them, but now there are tools that solve the optimal boards for those too.

A big part of the payoff of creativity is the feeling of discovery, of being a pioneer. That's hard to get when so many eyes are on the same game and the community solves things so quickly. I don't think that's easily solvable in the modern climate.

The other side of this is that players need something to ground them. Not every player wants to theorycraft at all, especially new players, and they shouldn't have to. Being able to see the meta without playing 500 games is really healthy for the playerbase as a whole. The flip side is that if everything is already known, creative players don't get rewarded for their creativity. That's most true at the highest level of play, where things are the most optimized. At lower levels, you can probably get away with a lot more.

I'm not sure what the answer is. Stats sites work because the same choice is worth about the same in every game, so it averages out. Choices whose value depends more on the specific game (the lobby, what others are playing, what's left in the pool) would be harder to solve ahead of time, but they'd also add variance, making the game more luck-based and harder to learn. That's probably not worth the tradeoff.

Honestly, some centralization is probably unavoidable. The meta will always settle around a few comps. The obvious way around that is extremely high variance, but then the game becomes a gamblefest in its own right, and having to theorycraft every single game would be too mentally taxing for most players.

So I don't think the goal is to make theorycrafting the norm. Ideally, it would be rewarding, or even optimal, in a small minority of games, maybe 1 in 10. Right now, I can't think of a reason not to play a meta comp in almost any game.

Related: when I took a few months off TFT, it wasn't because games lacked variety. There's already a ton of variation between games. It was more that I'd learned so much that even with that much variety, games started to feel like going through the motions. Every game eventually gets to that point for a dedicated player, and honestly it's a strength of TFT's design that it took so long.

### Scouting and matchmaking

**Matchmaking** is random for good reason. If you knew who you were fighting next, the game would turn into a twitch-reflex contest, which isn't what TFT is trying to be.

I'd even question whether players should have perfect information on enemy boards and positioning. I don't think the end-of-round positioning contest should really be part of the game. The catch is that players currently need to see enemy boards for other reasons: scouting champion counts, and clarity about what they're fighting and losing against, which matters especially for newer players. But if that twitch-reflex repositioning went away, matchmaking could become more predictable and feel fairer.

I don't mean literal round robin, just matchmaking that's more uniform and predictable. It might still feel unfair sometimes, but it would at least feel fairer, especially in the late game, where fight order can be a huge swing in placements.

More uniform matchmaking would also avoid a lot of common frustrations, like lobbies where two players are on long streaks and some players keep running into them while others don't, or endgames where it feels like you got screwed by fighting the same strong player several times in a row.

The two ideas really only work as a pair:

- **Predictable matchmaking on its own** brings back the problem it's trying to solve. If you know who you're fighting next, last-second repositioning against that specific player becomes even stronger.
- **Limited positioning information** is what makes predictable matchmaking work. Knowing your opponent but not their final positioning turns it into a mind game instead of a reflex test.

How much information players get matters a lot. If you can see an opponent's comp and how they've positioned before, but not their final positioning this round, good players can still read and predict, so it stays a skill. If you can't see anything, it's basically a coin flip. Some partial information is probably the sweet spot. Guessing is at least a mental skill test rather than a twitch-reflex one, which feels more in the spirit of TFT.

Some things to work through:

- **Readability.** Less visible information could make the game harder to follow for newer players, and for people watching streams or esports.
- **Eliminations.** Once players are knocked out, any fixed schedule has to adjust, with ghost fights or reshuffling.

### Feeling screwed after a loss

A lot of the time, losing can feel like you couldn't have done anything. Statistically that's obviously not true. There's no perfect player, and probably no perfect game of TFT has ever been played. But it can be really unclear why certain decisions were bad. That's why top players VOD review. Most players won't, and how they feel one second after a game ends is pretty much how they'll feel about that game overall.

The main things you can feel screwed by are items, rolldowns, matchmaking (see [Scouting and matchmaking](#scouting-and-matchmaking)), and augments.

**Items** have improved a lot. You only really feel screwed by items maybe 1 in 50 games now, especially since many items can substitute for others, which keeps getting better with every update.

**Rolldowns.** The community's understanding is that shops have some form of bad-luck protection, though how it works isn't public. A past bug let players hit a 3-star Ryze in one shop, which people linked to it. In Set 15, a lot of players, including top players, reported terrible rolldown luck, and a popular theory was a bug in that system, but a dev said there was no such bug. Even I thought something was bugged at the time, just from the volume of reports. If there wasn't a bug, was there something about that set that unintentionally made rolls feel worse?

**Augments** can't be changed, so an early pick that doesn't work out stays with you the whole game (see [Line selection](#line-selection-theorycrafting-and-endgame-boards)).

### Other missing information

A lot of important information isn't directly visible in the game, especially for newer players, though even experienced players would use some of it. Some examples:

- Champions left in the pool (see the [prototype](#prototype-pool-size-indicator) at the top). Right now you have to scout other people's boards and estimate.
- Cashouts for some traits and augments, which you can only find online.
- Damage taken from losing a round (the game may already show this somewhere; I don't remember exactly).
- Probably many others I'm not thinking of.

There's also a lot of data that matters at high levels and basically just lives on websites: artifact stats, emblem stats, augment stats, comp stats, charm stats. Knowing or not knowing these can change a game a lot, and these days it feels less like intuition and more like having looked the numbers up ahead of time, which can feel bad.

I can see why some of this isn't in the game, though. Some of it only really matters to a small number of high-level players, and for the playerbase as a whole it might not seem that important. Adding all of it would clutter the UI and make the game less inviting to newer players. An emblem's average placement on a unit, for example, matters a lot at high levels, but it isn't something you'd expect to see in game.

### Neutral rounds

I recall a dev talking about wanting to remove neutral rounds and why they're still here. If I remember right, one reason is that they give players a breather, which matters. But losing to them feels really bad while winning just feels normal, so the overall experience leans negative. Some questions:

- Is there a reason players should be punished for a board that's too weak here, or is it just filling the gap?
- What would TFT lose if it were just an empty round? Players would probably find the wait boring.
- What if it were a show match? Then players would feel like the outcome didn't matter at all.
  - A show match with real effects is a bigger problem, since stronger boards would get even more tempo and shift the meta a lot.

Neutrals do make winning feel like it matters, even when it's expected most of the time.

### Other observations

**Metas.** This is probably what high-level players talk about most. A meta can get stale or unbalanced, but when people call a meta "bad," they usually mean it isn't very skill expressive: a few outliers should almost always be taken, not getting them means losing most of the time, and even better players have few ways around that luck.

**Lower vs. higher tiers.** There's a big gap between the general playerbase and high-level players. Meta perception is really different, and simpler comps are seen as much stronger at lower tiers (I remember a friend complaining about Yordles when they were mediocre). Level distribution is different too, and a lot of lower-tier players like to force the same comp over and over. Honestly, they should be able to. It shouldn't be optimal at higher ranks, or the game becomes a slot machine. But at what rank should forcing become a detriment?
