# clawd-cat-nap.svg

A cozy, healing scene: a small grey cat is curled up asleep on top of Clawd's head, and Clawd stands perfectly still and content — happy ^^ eyes, pink cheeks, slow breathing — gently patting the cat with one arm while Zzz float up from the cat and two tiny hearts drift by. 4.8s loop; nothing in it moves fast.

## Body
Standard torso 11x7 at (2,6), #DE886D, four 1x2 legs at (3,13)/(5,13)/(9,13)/(11,13) planted outside the breathing group. Torso, face, cat and both arms sit in a `breathe` group (2.4s scale(1,1)↔scale(1.015,0.985), origin at the torso bottom (7.5,13)). Eyes are the content ^^ polylines (stroke #000000 0.8): left (3.5,9.5)→(4.5,8)→(5.5,9.5), right (9.5,9.5)→(10.5,8)→(11.5,9.5). Two pink cheeks #F8BBD0 1.3x0.6 at (3,10.3)/(10.7,10.3), opacity 0.9. Left arm 2x2 rests at (0,9). The right arm 2x2 (13,9) is raised from the shoulder onto the cat's rear via a `pat` group — translate(-1.5px,-5px) ↔ (-1.5px,-4.4px) at 1.2s, so it sits at x 11.5–13.5, y 4–6, still touching the torso's top-right corner, and drawn over the cat.

## Props
- **Cat** (asleep on the head, bottom edge on y=6; drawn head-right at 1x, then mirrored and scaled 1.15x about (7.5,6) with a static wrapper, so it ends up head-left, about 3.3–12.4 wide and ~4.5 tall): body #8D9DA6 built from three stacked rects (6.4x1.4 / 5.4x1.3 / 3.6x0.7) with three #607D8B stripes; head 3.1x2.8 with two 0.8x0.7 ears carrying #F8BBD0 inner-ear pixels; closed eyes as two #37474F 0.9x0.3 bars, a #F48FB1 0.4x0.3 nose, two #B0BEC5 front paws tucked under the chin; tail curling along the (now right) side with a #607D8B tip. Inside a `cat-breathe` group (2.4s scale(1,1)↔scale(1.02,1.06), origin at the cat's base); one ear is in an `ear-flick` group and the tail tip in a `tail-tip` group.
- **Zzz**: three monospace bold letters (z 2.2 #7986CB, z 2.6 #9FA8DA, Z 3.0 #7986CB) starting just above the cat's head (x 1.2–2.2, y 1.1–1.6), drifting translate(-1.8px,-5.5px) while scaling 0.6→1.25 and fading, 2.4s each, staggered 0/0.8/1.6s.
- **Hearts**: two tiny #F48FB1 pixel hearts (5 rects, ~1.7 wide) on the right at (13.5,3.6) and (14.5,1.6), drifting translate(1px,-4.5px) with opacity 0→0.95→0 over the first half of a 4.8s cycle, the second delayed 2.4s.
- **Ground shadow**: (3,15) 9x1 #000000 opacity 0.5, breathing scaleX 1↔1.015.

## Animation
- **breathe (2.4s)** and **shadow-breathe (2.4s)**: slow, tiny.
- **pat (1.2s)**: right arm translate(-1.5px,-5px) → (-1.5px,-4.4px) → back.
- **cat-breathe (2.4s)**: scale(1,1) → scale(1.02,1.06) → back.
- **ear-flick (4.8s)**: rotate 0 → -25° at 62% → 0 at 64% → -18° at 66% → 0 by 68% (one double flick per loop).
- **tail-tip (4.8s)**: rotate 0 → -30° at 29% → 0 by 34% (one twitch per loop).
- **zz-float (2.4s ×3, staggered)**: rise, grow, fade.
- **heart-float (4.8s ×2, offset 2.4s)**: drift up and fade within the first half of each cycle.

## Expression
Clawd stands frozen in place so as not to wake the little grey cat dozing on his head, his eyes squeezed into contented arcs and his cheeks pink, breathing as softly as he can and giving the cat's back the gentlest possible pats; the cat rises and falls with each breath, flicks an ear and twitches the tip of its tail in its sleep, Zzz drift up from its nose, and a couple of tiny hearts float away.
