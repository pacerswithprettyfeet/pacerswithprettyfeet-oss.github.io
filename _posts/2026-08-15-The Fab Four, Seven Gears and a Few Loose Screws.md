---
layout: post
title: "The Fab Four, Seven Gears and a Few Loose Screws"
comments: true
author: "Atharv Tambade, Aadityan Ganesh and Rishin Madan"
date: 2026-08-15
categories: descriptive test cricket
tags: [Fab Four, batting, gears]
---

<style>
  .fab-four-plot {
    display: block;
    width: 100%;
    border: 0;
    overflow: hidden;
  }

  .plot-headingley { height: 550px; }
  .plot-monasteries, .plot-arsonists { height: 630px; }
  .plot-fingerprint { height: 430px; }
  .plot-average-survival { height: 460px; }
  .plot-major-opposition { height: 470px; }
  .plot-ten-over-phases { height: 490px; }
  .plot-smith-eras { height: 430px; }
  .plot-kohli-careers { height: 680px; }
  .plot-root-handbrake { height: 365px; }
  .plot-root-jogs { height: 420px; }
  .plot-starting-innings { height: 420px; }
  .plot-innings-average { height: 405px; }
  .plot-innings-gears { height: 385px; }
  .plot-peak-partners { height: 320px; }
  .plot-kohli-post-2020 { height: 400px; }
  .plot-root-partners { height: 315px; }

  @media (max-width: 720px) {
    .plot-fingerprint { height: 730px; }
    .plot-average-survival { height: 405px; }
    .plot-major-opposition { height: 535px; }
    .plot-ten-over-phases { height: 500px; }
    .plot-smith-eras { height: 420px; }
    .plot-kohli-careers { height: 960px; }
    .plot-root-handbrake { height: 410px; }
    .plot-root-jogs { height: 450px; }
    .plot-starting-innings { height: 450px; }
    .plot-innings-average { height: 455px; }
    .plot-innings-gears { height: 855px; }
    .plot-peak-partners { height: 250px; }
    .plot-kohli-post-2020 { height: 290px; }
    .plot-root-partners { height: 865px; }
  }
</style>

Not all centuries are made equal. Smith’s Edgbaston 2019 and Pune 2017, Tendulkar’s Sydney 2004, Kohli’s Adelaide 2014: these innings occupy a higher place in cricketing lore than the plenty others that produced similar scorelines. Sometimes we need a lot more context beyond the data to understand what turns a special into a legend. Tendulkar’s 241, for instance, is inseparable from him entirely putting away the cover drive. But some of that context can be recovered simply by tracking how an innings progressed: did the batter counterattack at some stage, wade through a difficult spell, suddenly accelerate once set or cruise at the same tempo from start to finish?

Cricket already talks about these changes in tempo all the time. We have always talked about batters gearing up and down without really defining what that means. Yet we know it when we see it. Pant is at his best batting in fourth gear, rather than being rash in sixth. Pujara and Sibley might be batting out of their skins just to cruise in second. In this article, we formalize this intuitive notion of the gearbox.

We then use the gearbox to go over the careers of the Fab Four. Martin Crowe was perfect in predicting that these four would go on to rule Test cricket for a generation. Beyond being heavy run-scorers, they were all roughly at the same point on the age curve. Despite being spoken of in the same breath so many times over the past decade, nobody would claim that Steve Smith liked to construct an innings the same way Kohli did. The similarities in their careers make them natural candidates for comparison; the obvious differences in how they batted make them perfect candidates for the gearbox.

To build the gearbox, we first need to divide an innings into phases with distinct scoring rates. We use PELT, an off-the-shelf change-point detection algorithm well suited to this purpose. A cruder approach would chop an innings into, say, fixed eight-ball blocks and calculate a strike rate for each. PELT instead lets the innings choose its own boundaries: a new segment begins when the scoring pattern changes enough, regardless of the length of the previous segment. In his legendary Headingley innings, Stokes went from barely scoring at all for his first 80 balls to assaulting Josh Hazlewood towards the end. That is precisely the kind of change in tempo that PELT captures. We calculate each phase’s strike rate and assign it to one of seven gears.

| Gear | Strike rate |
| ---: | ----------: |
| 0 | 0–20 |
| 1 | 20–40 |
| 2 | 40–60 |
| 3 | 60–80 |
| 4 | 80–100 |
| 5 | 100–130 |
| 6 | 130+ |

<iframe
  class="fab-four-plot plot-headingley"
  src="{{ '/assets/plots/Fab fours and Gears/headingley_stokes_segments.html' | relative_url }}"
  loading="lazy"
  title="Gear-by-gear breakdown of Ben Stokes at Headingley"
></iframe>

As a sanity check, the likes of Lahiru Thirimanne, Rahul Dravid, Kraigg Brathwaite and Cheteshwar Pujara are among the batters with the highest fraction of balls in gear zero (among batters with at least 1,500 runs since ball-by-ball data became available). Surprisingly, Guptill and du Plessis also make the list. However, a look at their career strike rates suggests that this might not be much of a stretch: both finished their Test careers with strike rates well below 50.

<iframe
  class="fab-four-plot plot-monasteries"
  src="{{ '/assets/plots/Fab fours and Gears/test_crickets_monasteries.html' | relative_url }}"
  loading="lazy"
  title="Test cricket's monasteries"
></iframe>

At the other end is Adam Gilchrist, who spent almost a quarter of his deliveries in gear 6. Behind him come the usual arsonists: Tim Southee, Ben Duckett (i.e, the inventor of attacking cricket), Harry Brook, Virender Sehwag and Rishabh Pant. Of the top 15 batters by ball share in the sixth gear (at the same 1,500-run cutoff) 13 are openers, wicketkeepers or number eights who try to smoke every single ball for a six. Brook and Travis Head are the only exceptions. Expand the list to 20, and 15 still fit one of those three types.

<iframe
  class="fab-four-plot plot-arsonists"
  src="{{ '/assets/plots/Fab fours and Gears/test_crickets_arsonists.html' | relative_url }}"
  loading="lazy"
  title="Test cricket's arsonists"
></iframe>

## Comparing the Fab Four

The average top-seven Test batter shifts gear once every 15.14 balls. The Fab Four conform almost perfectly to this norm among the lower mortals. Kohli changes gears most frequently, once every 15.07 balls, while Williamson takes the longest, at 15.53. (This is not to suggest that all of Test cricket has the same average segment length: among batters to have faced at least 1,000 balls since ball-by-ball data became available, Haseeb Hameed tops the list at almost 19 balls per segment, while Daniel Vettori changes gears once every two overs.) Smith and Williamson face more than 90 balls per innings, compared with roughly 80 for Root and Kohli. As a result, the former accumulate almost six segments per innings, nearly one more than the latter two.

Viewed from 20,000 feet, these are remarkably similar batters: accumulators who strike at around 50 and score a hell lot of runs. Their gear distributions tell the same story. In each of gears 5 and 6 (the high gears), their ball shares sit within two percentage points of one another. Even after four years of Bazball, Root has spent only 0.6 percentage points more deliveries in gear 6 than Smith.

The differences begin to appear lower down the gearbox. As expected, Williamson and Smith spend the most time in gears 0 and 1. Root, whose superpower is getting off strike almost as soon as he gets on it, spends more time in gear 2 than any of the other three and the least time in gears 0 and 1. Compare their low-gear ball share (gears 0 and 1) with their middle-gear share (gears 2 to 4), and the four arrange themselves into a neat staircase. Williamson spends 14.5 percentage points more of his deliveries in the low gears than in the middle gears; Smith, 9.8; Kohli, 5.7; and Root, only 1.6 (Kohli being closer to Root in spirit than Smith).

<iframe
  class="fab-four-plot plot-fingerprint"
  src="{{ '/assets/plots/Fab fours and Gears/master_gear_fingerprint.html' | relative_url }}"
  loading="lazy"
  title="Fab Four gear-share comparison"
></iframe>

<iframe
  class="fab-four-plot plot-average-survival"
  src="{{ '/assets/plots/Fab fours and Gears/fab_four_average_survival_by_gear.html' | relative_url }}"
  loading="lazy"
  title="Fab Four batting average and balls per dismissal by gear"
></iframe>

Much bigger differences in playing style emerge when we look at their summary statistics in each gear.

### Williamson

Williamson has a higher career average and balls per dismissal than Root and Kohli. The same pattern holds in six of the seven gears (the only exception being gear 6, where Kohli was simply ridiculous). Put differently, Williamson is better than the other two almost uniformly, whether defending, cruising or attacking.

Curiously, Williamson outperforms Kohli and Root even when batting in the high gears. Across gears 5 and 6, he averages 205.5 and is dismissed once every 158.8 balls. In comparison, Kohli averages 177.2 and lasts 139.6 balls per dismissal; Root averages 170.8 and lasts 132.3. His dominance has only become more pronounced since 2020, even as the entire world has been struggling to buy a run during a raging pace-playing pandemic. Williamson lasts 241.8 balls per dismissal in the high gears, at an average of 326. It is not as if he has entirely stopped attacking and these higher numbers are simply a by-product of very selective aggression: his ball share in the high gears has not fallen significantly since 2020.

Williamson’s sheer calibre as an attacking batter felt ridiculous, and we assumed it would be easy to pick apart. The largest hole in his résumé is elite minnow-bashing: he has obvious problems against the stronger teams (South Africa, England, Australia and India), especially away from home. Yet his attacking record against those four teams, home and away, survives scrutiny: he averages 186.6 and lasts 147.8 balls per dismissal. Even away from home, he averages 144 and is dismissed once every 114.2 balls against these major nations. These are better figures than Root’s and Smith’s (granted, this comes from a small sample of only 571 balls; the other three have attacked roughly twice as many balls while touring their corresponding major nations). Only Kohli was better at attacking the stronger teams away from home.

<iframe
  class="fab-four-plot plot-major-opposition"
  src="{{ '/assets/plots/Fab fours and Gears/fab_four_major_opposition_home_away.html' | relative_url }}"
  loading="lazy"
  title="Fab Four high-gear home and away record against major opposition"
></iframe>

Williamson’s problems against stronger opposition stemmed entirely from his weak low gears. The average top-seven batter lasts 69 balls per dismissal in the low gears across all conditions. In South Africa, Australia, England and India, Williamson lasts fewer than 66.

We really do not understand this phenomenon. Our best guess is that Williamson was unusually good at choosing when to accelerate and when to retreat. He spent only 17.4% of his balls in the high gears, the lowest share among the four. However, this is not enormously below Root’s 19.6%, the highest among the Fab Four. When touring the four major countries, Williamson’s high-gear ball share falls further, to 15.9%.

There are not many phases of the game in which Williamson attacks more often than Root or Kohli. Alongside Smith, he was the most defensive batter among the Fab Four. Williamson has a higher share of balls in the high gears than Kohli and Root during overs 21–30, 51–60 and 71–80. In every other ten-over phase, he sits below both and, more often than not, even below Steve Smith. Those three phases could simply be noise. Or it could be that Williamson is usually well set by overs 21–30, while this is roughly when the number fours, Smith and Root, are walking in. During overs 71–80, he could simply be cashing in on the old ball before it is changed.

But there is no smoking gun. Even when Williamson accelerates to reach the high gears, 18.82% of his deliveries produce a four or six, virtually identical to Root’s 18.90%, Smith’s 18.89% and Kohli’s 18.88%. Watching Williamson bat, we can see that he attacked sparingly and was absurdly difficult to dismiss when he did. We cannot explain exactly why.

<iframe
  class="fab-four-plot plot-ten-over-phases"
  src="{{ '/assets/plots/Fab fours and Gears/williamson_missing_smoking_gun.html' | relative_url }}"
  loading="lazy"
  title="Fab Four high-gear ball share by ten-over phase"
></iframe>

### Smith

Steve Smith, in contrast, has no clue how to attack. In the high gears, he averages 118.6 and lasts 92.3 balls per dismissal, compared with 110.2 and 84.6 for the average top-seven batter. For context, Root and Kohli both clear 130 balls per dismissal and, of course, Williamson is even better. Nor is there some country where an attacking Smith suddenly turns into Adam Gilchrist. His best numbers come in Sri Lanka (where basically the entire Australian team looks like Don Bradman) where he lasts 137 balls per dismissal. At home, England and India, the corresponding numbers fall to 109.1, 60.4 and 57.3 respectively.

Smith’s superpowers lie in the lower gears. The quintessential 2010s Test memory consists of Smith blocking 40 balls straight from Neil Wagner and, when not blocking, scratching a single off an inside edge down to deep square leg. The gears capture this perfectly. Smith averages a whopping 53.8 in gear 1. Across gears 0 and 1, he is dismissed once every 132.3 balls, almost twice the top-seven baseline. Williamson ranks second among the Fab Four, and even he is a distant 98.8. In *The Art of Batting*, Jarrod Kimber writes that Smith simply loves to bat and is at his best when he can, well... simply bat. And he does that best when there is absolutely no hurry to hit the ball anywhere off the square.

More remarkably, this is the one part of Smith’s game that age has not managed to kill. At his peak, between 2014 and 2019, he lasted 148.3 balls per dismissal in the low gears (remember the “best since Bradman” claims?). Since 2020, that has fallen to 116.1. He is just a regular great player now. The bigger decline came in the middle gears, where his balls per dismissal fell from 125.1 to 74.8. And, returning to the point about Smith’s skill issue attacking, his numbers in the high gears were pretty stray even at his peak: he lasted only 97 balls per dismissal there.

<iframe
  class="fab-four-plot plot-smith-eras"
  src="{{ '/assets/plots/Fab fours and Gears/smith_immortality_mortality.html' | relative_url }}"
  loading="lazy"
  title="Steve Smith balls per dismissal by grouped gears across two eras"
></iframe>

### Kohli

Kohli’s story is the polar opposite of Steve Smith’s. His problem was defending. He was dismissed once every 73.9 balls in the two low gears, compared with 69.2 for the average top-seven batter. Kohli makes the top 50 batters in *The Art of Batting* almost entirely on the back of his ridiculous peak between 2014 and 2019. Yet even at the height of his powers, he lasted only 72.4 balls per dismissal in the low gears. You have to go all the way back to 2013 to find his best body of work defensively, when he survived 179.3 balls per dismissal. From 2020 onward, that number fell to an even more dismal 59.4. This decline also coincided with the pace-playing pandemic, when basically everyone kept getting out while defending. Still, the top-seven baseline over this period was 62.6.

His peak, on the other hand, was built around the middle and high gears. If watching Smith felt like a stray innings that had simply forgotten to end, Kohli was extremely intentional, always looking to stamp his authority. He would not allow bowlers to settle on that channel outside off, disrupting them with his trademark checked cover drive. All of this suggests a career built around the middle and high gears, and the data backs it up.

Between 2014 and 2019, Kohli spent 42.6% of his balls in the middle gears, roughly ten percentage points more than he did before or after. Those extra balls came almost entirely from the low gears, where the fraction of balls fell by roughly 15 percentage points (for context, outside his peak, he spent around half his deliveries in gears 0 or 1). He lasted 114.3 balls per dismissal and averaged 73.9 in the middle gears. He was not particularly far behind Smith (in god mode) at 125.1 and 79.6 respectively. Smith was slightly harder to dislodge there, but Kohli basically camped in the middle gears, spending six percentage points more of his deliveries there than Smith. His loss of form since 2020 can almost entirely be attributed to the middle gears: that number falls to a paltry 54.4 balls per dismissal towards the tail end of his career.

<iframe
  class="fab-four-plot plot-kohli-careers"
  src="{{ '/assets/plots/Fab fours and Gears/kohli_three_careers.html' | relative_url }}"
  loading="lazy"
  title="Virat Kohli across three career phases"
></iframe>

And unlike Smith, Kohli could remain in the high gears for more than five minutes without getting dismissed. During his peak, he spent 20.4% of his balls there. The combination of his middle and high gears is basically Bazball Root territory! He lasted 136.4 balls per dismissal in the high gears. His sixth gear is simply ridiculous. He faced 1,268 balls there, was dismissed four times and averaged 486. That is one dismissal every 317 balls. Unlike the middle gears, the high gears did not entirely desert him later in his career. From 2020 onward, he still attacked around 17% of all deliveries. His balls per dismissal fell to 117.8, a significant decline from his peak but still more than good enough for any other mortal batter. He spent 9.8% and 12.6% of his balls in gear 6 in 2023 and 2024, respectively, without being dismissed there once.

### Root

In the 2010s, Joe Root was basically Williamson Lite. Their gear distributions were nearly identical: Williamson spent 48.5% of his balls in the low gears, 33.7% in the middle and 17.9% in the high gears; Root’s corresponding shares were 45.6%, 35.5% and 18.9%. Williamson averaged more in every gear except gear 6, while their dot, jog and boundary percentages within each gear were remarkably similar.

Then Root basically became good at cricket, and England discovered Bazball. His monster 2021 came before Bazball, when he still spent 41% of his deliveries in the low gears. Then came the upgrade. His MO fundamentally changed with Bazball: it became almost impossible to keep him on strike for two balls straight. Since 2022, his high-gear share has risen only modestly, from 18.9% to 21.5%. However, the share of balls he spends in the low gears has collapsed from 44.4% to 32.5%, with almost all of that share migrating into the middle gears, from 36.7% to 46%.

<iframe
  class="fab-four-plot plot-root-handbrake"
  src="{{ '/assets/plots/Fab fours and Gears/root_bazball_handbrake.html' | relative_url }}"
  loading="lazy"
  title="Joe Root's gear distribution across three career phases"
></iframe>

Root’s reinvention has been built more on taking jogs than on finding new ways to score boundaries. The pattern resembles Kohli in the 2010s, which, sadly for Joe Root PR, means you could argue that he went from Williamson Lite to Kohli Lite. His total share of jogs rose from 23.2% to 30.3%; peak Kohli, for comparison, managed 26.4%. His boundary percentage, however, has increased by only 0.35 percentage points. Since 2020, Root has recorded the highest jog percentage among the Fab Four in every single gear. In *The Art of Batting*, Jarrod mentions Root’s ability to nudge the ball into a gap anywhere between cover and third man.

<iframe
  class="fab-four-plot plot-root-jogs"
  src="{{ '/assets/plots/Fab fours and Gears/root_jog_economy.html' | relative_url }}"
  loading="lazy"
  title="Joe Root's jog percentage by gear before and after Bazball"
></iframe>

The shape of his innings has consequently been turned upside down. Since 2022, gear 2 has been Root’s most common gear, followed by gears 3, 1 and 0. For a typical batter, the highest concentration of balls is in gear 0, with the share declining as the gears rise. All of the Fab Four conform to this pattern, including Root over the course of his full career. Kohli at his peak comes close to breaking the trend, but even he faced marginally more balls in the lower gears: 18.8%, 18.2%, 17.2% and 16% in gears 0, 1, 2 and 3, respectively.

The new avatar of Joe Root is truly set up to counter the wobble ball: score as many runs as possible before the ball with your name on it arrives. While Root does not spend more time in the high gears after Bazball, they have become considerably safer. His high-gear balls per dismissal rose from 121.3 before Bazball to 165.1 after.

Weirdly enough, weaponizing the middle gears has somehow made them riskier. His balls per dismissal in the middle gears fell from 78.8 to 69.2. Part of this could simply be that he is less choosy about which balls to attack in order to sustain a middle-gear scoring rate, so good spells that would once have pushed him into gears 0 and 1 are now being milked at four runs an over. However, his balls per dismissal in the low gears have fallen from over 90 to 77.3. Once again, this could have little to do with Root and simply reflect the pace-playing pandemic.

With the wobble ball and Bazball almost perfectly coinciding with his rise, we do not know how to separate the effects of Root simply hitting his peak from those of him choosing to change the way he plays. Test cricket, very selfishly, declined to provide a control group.

The aggregate gear stats establish the broad outlines. We can go even further: concretely, we ask how each of the four starts an innings, how their approach changes across the four innings of a Test match, and what happens when they bat alongside the top order, the lower middle order or the tail.

## Starting an innings

Three of the Fab Four begin their innings roughly as we would expect. Williamson treats the Kiwi “steady the ship, captain” chant as a constitutional duty, starting 39.0% of his innings in gear 0, compared with 34.0% for the average top-seven batter. Kohli leans slightly the other way, beginning there only 31.4% of the time. Root lives up to his reputation for immediately getting off strike: he starts 35.3% of his innings in gear 3 or higher. Root is therefore more likely to begin an innings at a strike rate above 60 than the average top-seven batter is to begin one below 20.

Smudger is the most fascinating, or perhaps the most erratic, among them all. He is more likely to attack right off the get-go than Kohli and Williamson, and maybe even Root. He begins 14.5% of his innings in gears 5 or 6, compared with Root’s 11.7%. Include gear 4 and Smith’s share rises to 20.0%, only marginally behind Root’s 20.7%. At the opposite extreme, Smith starts in gear 0 less often than any of the four, at 23.2%. His most common starting gear is actually gear 1, at 25.9%. Steve Smith starting an innings seems to be a very different creature from the one batting beyond 20 balls.

<iframe
  class="fab-four-plot plot-starting-innings"
  src="{{ '/assets/plots/Fab fours and Gears/starting_an_innings.html' | relative_url }}"
  loading="lazy"
  title="First-segment gear distributions for the Fab Four"
></iframe>

Looking at Smith’s ball share across gears by ten-over phases makes this apparent chaos look more deliberate. This could be Smith’s problem-solving at full tilt. Between overs 1 and 10, Smith spends 19.2% of his balls in the high gears, 6.2 percentage points clear of Kohli in second place. This includes both his usual appearances after two quick wickets and the great opening experiment. He likes to counterattack when the ball is new and moving, forcing the bowler to keep searching for different lines and lengths. The pattern returns with the second new ball. Between overs 81 and 90, Smith spends 21.2% of his deliveries in the high gears, almost level with Root at 22.3% and comfortably ahead of Kohli and Williamson. Once the ball softens, he goes back to his best: hitting snooze till the cows come home, or in this case, until the second new ball.

## Across the four innings

Kohli and Smith clock very different numbers across the four innings of a match. We know Kohli has basically solved run chases in limited-overs cricket. Having a target in front of him seems to help in Test cricket too. He averages 45.7 in the first innings, rising to 61.8 in the second (the best raw average among the Fab Four). The same pattern, although less dramatic, appears in the last two innings of the match: he averages 36.0 in the third innings and 42.4 in the fourth.

As with his life overall, his improvement in the second innings comes broadly on the back of being a machine in the middle gears. His gear distribution remains roughly the same across innings; it just becomes impossible to dismiss him in the middle gears in the second innings. He lasts 86 balls per dismissal there in the first innings, compared with 116.9 in the second.

The fourth innings, on the other hand, is built around the high gears. Kohli spends 21.6% of his deliveries there, compared with 17% in the first innings. His response to a fourth-innings run chase on a deteriorating wicket is debilitating the bowler. He lasts over 200 balls per dismissal in the high gears in the fourth innings, more than 50 balls longer than in the first innings and 80 more than in the third.

Smith’s insomnia, on the other hand, actively causes his game to deteriorate as the match progresses. He averages an absurdly good 81.3 in the first innings and an absurdly stupid 30 in the fourth, comfortably the lowest among the Fab Four. Despite this weird deficiency, his gear distribution is remarkably similar in the first and fourth innings. The choices he makes about tempo are roughly the same; he just becomes worse at both attacking and defending. And unlike Virat, and basically all of Bazball, he does not have the ability to compensate for shorter stays by attacking more effectively.

<iframe
  class="fab-four-plot plot-innings-average"
  src="{{ '/assets/plots/Fab fours and Gears/across_innings_1_4.html' | relative_url }}"
  loading="lazy"
  title="Fab Four batting average across innings one to four"
></iframe>

<iframe
  class="fab-four-plot plot-innings-gears"
  src="{{ '/assets/plots/Fab fours and Gears/innings_gear_explorer.html' | relative_url }}"
  loading="lazy"
  title="Steve Smith and Virat Kohli by innings, gear group and metric"
></iframe>

The above points to a really neat irony. Smith has a reputation for changing his batting technique midway through an innings if he thinks doing so will better suit the pitch. At least over the last few years of his career, plenty of people have been crying over Kohli’s rigidity. Yet Kohli appears far more comfortable moving up and down the gearbox to tackle a deteriorating pitch, while Smith has been unable to problem-solve his way out of it.

## Preferences with batting partners

Both Kohli and Smith did their best work between 2014 and 2019. But when it came to finding the right partners to do it with, each had his own type.

Kohli kept things conventional: he preferred to lead from the front and was nowhere near as effective with the lower middle order. With other top-five batters at the crease, he averaged 94.8 in the middle gears and lasted 147.7 balls per dismissal. Smith managed 75.9 and 117.6, respectively. In the high gears, comparing Kohli (especially at his peak) with Smith is not even the right conversation to have: Kohli survived 155.1 balls per dismissal, compared with 115 for Smith. He even outshone Williamson, whose efficiency when attacking was basically the entire first part of this article. In contrast, Kohli’s preferred middle gears simply collapsed when batting with numbers 6 through 8: he averaged only 43 and lasted 65.5 balls per dismissal.

Steve Smith somehow became even more Steve Smith alongside Nos. 6 to 8. In gear 0, he was dismissed once in 646 balls, and across gears 1 to 3 he lasted roughly 200 balls per dismissal. Across the middle gears, he averaged 97.6 and lasted 162.6 balls per dismissal; Williamson was a distant second at 69.3 and 113.7. Curiously, Smith even lasted longer in the high gears alongside Nos. 6 to 8 than Kohli did. This says more about Kohli being bad, at 101 balls per dismissal, than about Smith suddenly learning how to attack, at 113.

Excluding Kohli and Smith, India’s other top-five batters averaged 41.4, while Australia’s averaged 42.6. Kohli was therefore not being handed a uniquely durable top order with which to pile up runs, nor was Smith constantly being catapulted towards Nos. 6 to 8 by Australian collapses. Australia’s lower middle was actually weaker, averaging 24.6 compared with India’s 31.9. So one could argue that Smith collected cheap contextual not-outs whenever the lower middle folded. That is not the case either. Smith and Kohli batted with Nos. 6 to 8 in almost exactly the same fraction of their innings, 34.3% and 34.6%, respectively. Once there, Smith averaged 105.3 and faced 82.5 balls per innings; Kohli managed 48.3 and 55.1. Smith did not meet the lower middle more often compared to Kohli. He simply turned those encounters into long-term relationships more often than not.

Kohli re-enters the conversation from the back, batting with the tail. He spent 45.5% of those deliveries in the high gears, comfortably ahead of Root at 34.8% and Smith at 26.5% (Williamson faced fewer than 100 balls with the tail during this period, so we leave him out). Even operating in the high gears for almost every other delivery did not make Kohli particularly dismissible: he lasted 163 balls per dismissal and averaged 214. Another 35.8% of his deliveries came in the middle gears, where he survived 128 balls per dismissal, leaving only 18.7% in the bottom two. This was less a man shepherding the tail than one taking the entire mission upon himself. Smith, naturally, still spent more than one delivery in three in the low gears. He took his sweet time even with Nathan Lyon at the other end.

<iframe
  class="fab-four-plot plot-peak-partners"
  src="{{ '/assets/plots/Fab fours and Gears/peak_partner_story.html' | relative_url }}"
  loading="lazy"
  title="Fab Four partner patterns during 2014-19"
></iframe>

Come 2020, with the pace-playing pandemic and the great spinning Indian tracks, Kohli’s preferences changed entirely. From being the best among the Fab Four in the middle gears when batting with other top-five batters, he fell to the bottom, averaging 30 and lasting barely 50 balls per dismissal. He was still fine alongside Nos. 6 to 8, averaging 53 and surviving 84.8 balls per dismissal. The high gears tell a similar story.

We conjecture that much of this came down to the ball’s altered ageing curve in the wobble-seam era. Wobble seam keeps the ball harder for longer than conventional swing, extending the phase in which Kohli had to survive lateral movement. Even at his peak, Kohli was more comfortable against high-end pace than a moving ball; as he aged, protection from the hard, moving ball became increasingly important. Forget protecting him by delaying his entry: India’s top order stopped making runs altogether. Excluding Kohli, its other top-five batters averaged only 31.4 during this period. He entered before the 20th over in almost 70% of his innings, up from 47% at his peak. At home, Axar and Ashwin could still amass runs once the ball softened; but batting in the top order had become a Sisyphean task.

The poor man tried everything he could to fight the decline. First, he attempted to survive his way through it: his low-gear ball share rose to 54.0% in 2021 and 61.6% in 2022. Then he tried attacking his way out of it, with his high-gear share jumping to 21.0% in 2023 and a frankly unhinged 27.5% in 2024. These were, and still are, dark times for batting.

<iframe
  class="fab-four-plot plot-kohli-post-2020"
  src="{{ '/assets/plots/Fab fours and Gears/kohli_post_2020_gear_shares.html' | relative_url }}"
  loading="lazy"
  title="Virat Kohli's gear shares from 2021 to 2024"
></iframe>

Unlike Smith and Kohli, Root was largely agnostic about whether his partner came from the top or the lower middle. We split his career into three phases: 2014–19 (when everyone knew Root was a fantastic player, except he wasn’t), 2020–21 (when he almost scored 15,000 runs per calendar year) and Bazball. Only during 2020–21 did he show any real preference for top-order company.

Between 2014 and 2019, Root lasted 85.6 balls per dismissal with top-five batters, rising only slightly to 89.3 alongside Nos. 6 to 8. His gear distributions were similarly close: roughly 42% low, 36% middle and 21% high in both situations. Even his survival rates in the low and middle gears were almost identical. The only substantial difference was in the high gears, where he lasted 108.2 high-gear balls per dismissal with the top order and 133.2 with the lower middle. This relative indifference returned under Bazball, only with Root operating further up the gearbox: regardless of his partner: roughly 32% of his balls have come in the low gears, 46% in the middle and 21% in the high gears.

<iframe
  class="fab-four-plot plot-root-partners"
  src="{{ '/assets/plots/Fab fours and Gears/root_alleged_partners.html' | relative_url }}"
  loading="lazy"
  title="Joe Root's gear distribution by partner group across three eras"
></iframe>

The Fab Four are thought of as the same batter generated four times, partly because of all the romanticization of them as the sexy run-scorers for their respective countries (and whatever Steve Smith did). Discourse comparing and contrasting the greatest batters of any generation is only natural. Some differences are obvious. Root’s Bazball acceleration could be seen in his strike rate alone. Even people who do not believe in stats could probably feel it in the bottom of their hearts, given how diligently the English dressing room has informed us that Bazball fundamentally changed cricket. Other differences were universally understood but harder to support with conventional statistics: Kohli wanted to dominate an innings; Smith wanted to bat until the heat death of the universe. Breaking their scoring patterns into gears puts numbers behind those vibe checks. Smith’s superpower lived in the low gears, Kohli’s peak in the middle and high gears, and Root’s reinvention in learning to find gear two without really needing gears zero and one.

There are troves and troves of similarly deranged cricketing vibes. Jarrod Kimber talks about how Pant and Stokes decide that a ball must be defended and defend it come what may, or decide that it must disappear for six and attempt murder regardless of where it pitches. When batting with the tail, Stokes can pick a bowler and an end, then keep pressing the six button until the fielding side unplugs the controller. Tracking the progression of an innings gives us a way to test these claims instead of merely nodding along because they sound right. Gears are one way to give cricket’s vibes an audit trail. There are enough deranged cricketing vibes to support an entire branch of stats and analysis.
