---
layout: post
title: "Writing the Tristan Stubbs Manual"
comments: true
author: "Atharv Tambade and Aadityan Ganesh."
date: 2026-05-22
categories: IPL
tags: []
---

Tristan Stubbs is one of the IPL’s latest mysteries. He is certainly a top-class product, but his instruction manual remains undecipherable. Teams have kept using him for lower-order patch jobs, even though he is clearly too skilled to be fed leftovers. When he comes in late, he looks like a math PhD sitting for a tenth-grade test. Send him in early, and suddenly it feels like the same test has to be answered in Mandarin. Somewhere between those two versions is the real Stubbs: a batter with a complete toolkit who keeps refusing to fully unleash himself, exactly like a finisher-anchor.

The puzzle begins even before he faces a ball. His usual entry points scream a finisher. Before IPL 2026, Stubbs had batted at number five eleven times and number six fifteen times, the two most common slots of his career. Delhi have largely kept him in that same lane this season. In their first ten games, he did not bat once, came in at number six or lower five times, at number five thrice, and at four once, against Rajasthan, where he still only walked out around the 15th over anyway. Teams cannot really be blamed for parking him there. In their defence, finishing is the one role he seems to understand best. But reducing Stubbs to a finisher still feels like a narrow use of a player with this broad a toolkit.

The summary stats do not immediately justify the fuss. Stubbs’s NEB and TSR are both only slightly above par. He is better batting first, where his NEB rises to +2.5; while chasing, it slips to -1.3 (typical South African?). At this level, he looks like yet another useful lower-middle-order batter doing useful lower-middle-order things, not someone worth writing an entire operating manual for. But his aura points go through the roof when we look at the raw numbers.

Stubbs stops looking ordinary when we look at raw average. He averages 47 in the IPL, which is extremely hard to maintain from his usual entry points. Dhoni is the obvious comparison: both have entered at broadly similar stages, mostly between overs 13 and 15, with smaller clusters on either side. The great man averages 39.13. Stubbs clears him on raw average. But Dhoni is a safehouse, with an NEB of 4, while Stubbs is close to zero. That is the first crack in the story. The average says Stubbs is elite at surviving late entries; NEB says he is not actually facing many more balls than expected. Both are true, which is where the curious case of Tristan Stubbs properly begins. 

The not-outs explain the mismatch. Stubbs is ridiculously good at remaining unbeaten every other innings, quite literally. Before IPL 2026, he had batted 30 times in the IPL and remained not out 15 times. This has carried into 2026: in nine outings, he has been unbeaten four times, and one of his five dismissals was a run-out. Dhoni, by comparison, has stayed unbeaten in 42% of his IPL innings. Less anchor-y finishers like Pollard and Pandya remain unbeaten in fewer than 33% of theirs. This gives us the prima facie case: Stubbs is a finisher anchor in the Dhoni mould. The rest of the article tests this claim, and asks whether he should have to be one.

The Dhoni comparison goes well beyond the average. Like Dhoni, Stubbs is highly formulaic in how he builds an innings. The usual pattern is simple: get to around 12 at roughly a run a ball, carry the innings into the final five overs, and then go nuts on the gas. Both are willing to fall badly behind par in the middle overs. Stubbs has a middle-overs TSR of -33.4; Dhoni is not much better at -25.6. In raw terms, that is 115.4 for Stubbs and 100.4 for Dhoni. The difference is that Dhoni survives this phase far more reliably. Stubbs averages only 28.2 between overs 7 and 15. Dhoni averages 49 per dismissal in the same phase, despite averaging less than Stubbs overall. Stubbs has borrowed the Dhoni script, but not quite the Dhoni survival clause. The former has an NEB of 3 in this phase, while the latter has an NEB of 26.1. 

The table that you showed me where it becomes extremely obvious that he is sitting at run a ball for a long long time.
<iframe 
  src="{{ '/assets/plots/Writing the Tristan Stubbs Manual/stubbs_plot1.html'  |relative_url }}" 
  width="100%" 
  height="1300" 
  style="border:none; overflow:hidden;"
></iframe>
IPL 2026 has not been any different. Every Stubbs innings over 20 has followed the same broad shape. Against LSG, he was 32 off 28 while Sameer Rizvi did the heavy lifting. Against CSK, he went from 13 off 12 to 60 off 38 while the batting order collapsed around him.

A list of stuff he has done in this season → setting up base to what he actually scored, in the three/four innings where he came off.
<iframe 
  src="{{ '/assets/plots/Writing the Tristan Stubbs Manual/stubbs_plot2.html'  |relative_url }}" 
  width="100%" 
  height="500" 
  style="border:none; overflow:hidden;"
></iframe>

The obvious explanation would be that Stubbs lacks middle-overs scoring options. Dhoni, for one, really does look like that kind of batter in this phase: 7% more dots than par, 2% fewer jogs, and 5% fewer boundaries. Stubbs sits at the other extreme. Between overs 7 and 15, he takes 10% more jogs than expected, the best in IPL history among batters who have faced at least 100 balls in this phase (yes, even ahead of Kohli and Gill). He takes a single off roughly 56% of the balls he faces here. His problem is not access to the single. He can get one almost on demand. The problem is that he keeps taking it even when the situation dictates more: his +10% effective jogs are dragged down by a -10% effective boundary rate. 

Their interesting dot-to-six spectrum.
<iframe 
  src="{{ '/assets/plots/Writing the Tristan Stubbs Manual/stubbs_plot3.html'  |relative_url }}" 
  width="100%" 
  height="500" 
  style="border:none; overflow:hidden;"
></iframe>

For all the similarities between Stubbs and Dhoni, their middle-overs kryptonites are different. Stubbs gets stuck against pace; Dhoni gets stuck against spin. Against fast bowling between overs 7 and 15, Stubbs has effective dots of +7.6%. He still scores 5.4% more jogs than par, but his effective boundary rate collapses to -13.1%. Dhoni’s equivalent problem is middle-overs spin, where his effective dots, jogs, and boundaries are +8.5%, -3.8%, and -4.7% respectively. But Dhoni’s struggles are more evenly spread: his middle-overs TSR is -27.1 against spin and -22.7 against pace. Stubbs is much more lopsided. Against middle-overs spin, his TSR is a peachy -5.9. Against middle-overs pace, it properly stinks: -59.8. 

Stubbs is still playing his middle-overs anchor role in 2026, at a strike rate of 127.18 (the league strike rate is 147). However, he has solved his pace problem — he is close to par, with a strike rate of 149.2. He has managed to unlock Dhoni territory against the tweakers though — striking below run a ball, at 92.5. This is not a matter of a small sample size either — he has faced 40 balls against the tweakers.

Their interesting dot-to-six spectrum in the middle overs against pace and spin.
<iframe 
  src="{{ '/assets/plots/Writing the Tristan Stubbs Manual/stubbs_plots_dots_jogs_biund_2026.html'  |relative_url }}" 
  width="100%" 
  height="400" 
  style="border:none; overflow:hidden;"
></iframe>

Then comes the whiplash. From being a strike-rotator through the middle-overs, Stubbs becomes one of the best death-overs batters in IPL history. Among batters who have faced at least 150 balls after the 15th over, he has the fifth-highest TSR, behind only Livingstone, AB de Villiers, Gayle, and Pant, and ahead of even Klaasen, Buttler and the mighty Russell. He does this while averaging 87.8 in the phase (the best in this 150 ball group)! Whatever explains the middle-overs confusion, the end-overs version of Stubbs has already arrived. This is the role teams trust him with, and for good reason. With an NEB of 24.5, Stubbs is the ultimate closer any team would want.

Table of leading TSRs, averages and NEB having faced at least 150 balls.
<iframe 
  src="{{ '/assets/plots/Writing the Tristan Stubbs Manual/stubbs_plots_Death_TSR_NEB.html'  |relative_url }}" 
  width="100%" 
  height="500" 
  style="border:none; overflow:hidden;"
></iframe>

The interesting part is not just that Stubbs scores fast at the death. His blueprint is close to science fiction. His two great middle-overs skills, avoiding dots and finding singles, both carry over to the death. He adds boundary-hitting to his portfolio. He faces 12% fewer dots than par (behind only Cameron White), while scoring 6% more jogs and 6% more boundaries. The split between fours and sixes is the key. Almost all the extra boundary-hitting comes from fours. His effective fours percentage is 6% (behind only Shahrukh Khan at 7.2%, and roughly level with SKY), while his effective sixes percentage is just 0.8%. This also helps explain the absurd average: he does not hole out in the deep by looking to clear the fielder. He is on a different tier at putting the ball into every hole that he finds.

Stats for everything mentioned above — TSR in the death, dot-to-six spectrum, the leaderboard in dots and fours. Show numbers for Dhoni as well here.
His percentage of dots, jogs, fours and sixes this year.
<iframe 
  src="{{ '/assets/plots/Writing the Tristan Stubbs Manual/stubbs_plots_TSR_death.html'  |relative_url }}" 
  width="100%" 
  height="1700" 
  style="border:none; overflow:hidden;"
></iframe>


That is why the finisher-anchor case is almost open-and-shut, but also why it feels too small. Stubbs’s death-overs game is not built around blind slogging; it is built on low-risk scoring that already forms the backbone of his middle-overs play. That gives us reason to ask whether he can access his death-overs gear before the fifteenth over. Of course, he is not going to average 87.8 if he plays this way across different phases of the game. But if the method translates as it promises, Delhi get something far more useful than a specialist closer: a batter who can start hurting teams well before the final five. The next question, then, is simple: can Stubbs access faster gears earlier, or does he need to chew through a few balls before the engine starts? 

To test this, we start with his cluster-wise TSR. Stubbs’s first eight balls are ugly: with a TSR of -38.1. Then the numbers snap back hard. Between balls 9 and 16, his TSR jumps to +30, with a raw strike rate of 223. At first glance, the fix looks simple: absorb the first eight balls and Stubbs becomes dangerous. But that reading is too neat. The second cluster looks explosive largely because it often arrives in the death overs. When balls 9 and above overlap with the middle overs, his TSR is still a depressing -11.7. In other words, his misery seems tied more to the middle-overs than to innings progression. 

Table with his clusterwise TSR.
<iframe 
  src="{{ '/assets/plots/Writing the Tristan Stubbs Manual/stubbs_plot_clusterwise_TSR.html'  |relative_url }}" 
  width="100%" 
  height="400" 
  style="border:none; overflow:hidden;"
></iframe>

For that matter, Stubbs does not even seem to need his first eight balls when he walks in after the 15th over. His first-eight-ball TSR in those innings is +30.3 (a raw strike rate of 206). Enter earlier, though, and the same window collapses: -51.9 when he comes in between overs 10 and 12, and -70 between overs 13 and 15. This is not the profile of a batter who is inherently slow to start. These are the right ingredients for an ultimate anchor — except for his adamance.

Stubbs seems to be at his best when he knows exactly what he is supposed to do.  When Stubbs walks in between overs 10 and 12, his innings TSR is +26.42. When he enters after the 15th over, it is +32. The trouble is with the in-between phase. Before IPL 2026, he had entered between overs 13 and 15 in 11 of his 30 IPL innings, but his TSR there drops to -13.17. That may just be sample-size noise. But that could also be Stubbs caught in two minds: too late to build an innings, too early to switch to his death-overs four-hitting mode.

As the Good Areas team have pointed out (link), teams have fundamentally changed how they structure T20 innings. Death overs strike rates peaked in 2024 and 2025 at 175, but has dropped back to 160s as has been the norm between 2018 and 2023. But, the powerplays and middle overs are barely recognizable — rising all the way from 120s in 2022 (the last season without impact subs) to 160.2 and 147 respectively. Batters are trying to break games open from the powerplay itself, and the old non-aggression treaty between batters and bowlers in the middle overs barely exists anymore.

Insert a table with the phasewise strikerates in the IPL since 2018. I have attached the full numbers in a table at the end of the article for your reference. Put a disclaimer that the data is till the PBKS v DC game on the 11th.
<iframe 
  src="{{ '/assets/plots/Writing the Tristan Stubbs Manual/stubbs_plot_phase_sr.html'  |relative_url }}" 
  width="100%" 
  height="600" 
  style="border:none; overflow:hidden;"
></iframe>

That makes Stubbs particularly interesting. He already has the finishing game; the question is whether he can bring enough of it forward. The sport has moved into its 2026 build, while Stubbs is still spending too much of the innings running the older finisher-anchor script. He is slightly overdue for the version update. The tools are already there; Delhi can queue the download, but Stubbs still has to install it.








