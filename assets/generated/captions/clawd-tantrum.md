# clawd-tantrum.svg

Clawd throwing a cute little fit (气鼓鼓跺脚): cheeks puffed, eyes squeezed into angry chevrons, deep blush, fists clenched at his sides and trembling. Four heavy stomps — left, right, left, right — each with a wind-up (the leg swings out from the hip and lifts while the body rises and leans over the other side), a two-frame slam (body crushed flat, dust, thud lines, a puff of air from the cheek, eyes squeezed tighter) and a hold. After the fourth slam he glances away with a hmph. 3s loop; no running gait, arm swing, head shake or jump, so it reads purely as stamping.

## Body
Standard torso 11x7 at (2,6), #DE886D. Everything sits in a `tremble` group (0.1s translate ±0.12px — he shakes with anger throughout). The torso, face and arms are in a `body` group (origin at the feet (7.5,15)) held at the puffed baseline scale(1.08,0.96); on each wind-up it rises translateY(-0.6px) and leans rotate(±4°) over the planted side (right for a left stomp), on the slam it drops translateY(0.7px) crushed to scale(1.2,0.82), holds low at scale(1.12,0.92) and eases back over the rest of the 0.75s slot. Legs are 1x3 from y=12 (1px overlap into the torso) in two pairs outside the body group — left (3,12)/(5,12) with hip origin (4.5,12), right (9,12)/(11,12) with origin (10.5,12); the stomping pair swings out sideways rotate(±42°) and lifts translateY(-1.4px) over the wind-up (10%), then snaps back to rotate(0) translateY(0) in 2% for the slam; the other pair stays planted. Eyes are two chevrons (stroke #000000 0.8): left `>` (3.6,8.1)→(5.2,9)→(3.6,9.9), right `<` (11.4,8.1)→(9.8,9)→(11.4,9.9), squeezing scale(0.8,0.85) translateY(0.3px) on each slam and sliding translateX(-2.2px) for the final glance (92–97%). Cheeks are #F48FB1 1.8x0.8 at (2.6,10.2)/(10.6,10.2). Arms 2x2 at (0,9)/(13,9) are held clenched and slightly down, rotate(∓15°) about the shoulders (2,10)/(13,10), jerking to ∓40° for 2% on each slam — never swinging.

## Props
- **Dust**: two #BDBDBD 0.8–1 squares at each foot ((2.2,14.2)/(4.6,14.3) left, (11.8,14.2)/(9.6,14.3) right) bursting outward/upward scale 0.5→1.4 opacity 0→0.9→0 for ~12% after each slam on that side.
- **Thud impact lines**: three short #424242 0.35 lines fanning out from the outside of each stomping foot (x 0.1–1.8 left, 13.2–14.9 right, y 14.2–15.8), flashed on with step-end for 3% at each slam.
- **Cheek puffs**: #CFD8DC rounded 1x0.9 pixels at (0.4,10.6)/(13.6,10.6), blowing outward translate(∓2.4px,-1.2px) scale 0.5→1.4 on each slam of that side, plus a bigger one (scale 1.2→1.6, translate(-3px,-1.6px)) from the left cheek on the final hmph (91–100%).
- **Ground shadow**: (3,15) 9x1 #000000 opacity 0.5, scaleX 1.06 at rest, flashing to 1.3 / opacity 0.62 on each slam.

## Animation
- Slots: L 0–25%, R 25–50%, L 50–75%, R 75–100%. Within a slot starting at S: wind-up S→S+10%, peak S+12%, slam S+14%, hold/ease S+18%→S+25%.
- **body (3s)**: rise + lean on each wind-up, crush on each slam, low hold, ease back.
- **legs-l / legs-r (3s)**: swing out rotate(±38°→42°) translateY(-1.2→-1.4px) then snap down.
- **eyes (3s)**: squeeze on each slam; glance translateX(-2.2px) 92–97%.
- **arm-l / arm-r (3s)**: ∓15° held, ∓40° jerk on each slam.
- **shadow (3s)**, **dust-l1/l2/r1/r2 (3s)**, **impact-l / impact-r (3s, step-end)**, **hmph-l / hmph-r (3s)**, **tremble (0.1s)**.

## Expression
Cheeks blown up and face flushed, eyes screwed into `> <`, fists clenched and shaking at his sides, Clawd stamps his foot in a temper: he hoists one leg out to the side, tips his whole body over the other foot, and brings it down with a thud that squashes him flat and sends dust and impact lines flying — then stays hunched and quivering for a beat before hoisting the other leg. Left, right, left, right; after the fourth stomp he turns his eyes away with a puff of air. Hmph.
