# catclawd-pout.svg

Cat-form Clawd in a cute huff (气鼓鼓): cheeks puffed, arms folded across his chest, ears flattened back, eyes squeezed into angry chevrons, blush deepened, a tiny grey cloud bobbing over his head. He turns his face away to one side with a "hmph" puff of air, stomps once as he swings back to glare, then turns away to the other side — while his tail slaps the ground the whole time. 4s loop.

## Body
Cat-form Clawd (see `catclawd-body-structure.md`). The whole cat sits in a `huff` group (translateX 0 → -1.5px turned away left 20–42% → a 0.3px overshoot at 48% → 0 at 52–60% → +1.5px turned away right 68–88% → 0 by 96%). Torso, face, ears and arms sit in a `puff-body` group (origin at the feet) held at scale(1.08,0.96) — the puffed cheeks — swelling to scale(1.14,0.93) on each hmph (18% / 66%) and squashing to scale(1.16,0.9) on the stomp at 49%. Eyes are two chevrons (stroke #000000 0.8): left `>` (3.6,8.1)→(5.2,9)→(3.6,9.9), right `<` (11.4,8.1)→(9.8,9)→(11.4,9.9), sliding translateX(∓2.2px) to look away with each turn. Cheeks are larger and deeper #F48FB1 1.8x0.8 at (2.6,10.2)/(10.6,10.2); nose #F8BBD0 as usual. Ears are pinned back: left rotate(-30°) / right rotate(30°) about their bases, flattening further to ∓40° on each hmph and lifting to ∓14° for the stomp. Both arms are folded in front of the chest via translate(±4.6px,1px) (x 4.6–6.6 and 8.4–10.4, y 10–12) with 0.22-opacity drop shadows, squeezing tighter to ±5px on each hmph. The right pair of legs stomps once (translateY -1.4px at 45%, down at 49%).

## Props
- **Tail**: standard curled tail rotating about its root (13.6,12.2), slapping the ground rotate 0 → 52° at 55% → 46° at 70% → 0, on a 0.5s ease-in cycle; a #BDBDBD 0.8 dust puff at (16.2,14.2) pops on each slap.
- **Cloud**: three #90A4AE rounded rects (3.2x1.2 at (9.6,1.4), 1.5x1 at (10.2,0.7), 1.1x0.9 at (11.4,0.9)) over the right ear, bobbing translateY 0↔-0.4px at 1s.
- **"Hmph" puffs**: two #CFD8DC rounded 1x0.9 pixels at the cheeks (0.6,9.6) and (13.4,9.6), each blowing outward translate(∓2.4px,-1.2px) scale 0.5→1.4 opacity 0→0.9→0 as he turns that way (16–30% left, 64–78% right).
- **Ground shadow**: (3,15) 9x1 #000000 opacity 0.5, scaleX 1.06, following the turns and widening to 1.14 on the stomp.

## Animation
- **huff (4s)**: 0–12% centre → 20–42% left → 48% overshoot → 52–60% centre → 68–88% right → 96–100% centre.
- **puff-body (4s)**: scale(1.08,0.96) base; (1.14,0.93) at 18% and 66%; (1.06,0.98) at 46% → (1.16,0.9) at 49% → base by 54%.
- **eyes-look (4s)**: translateX 0 → -2.2px 20–42% → 0 50–60% → 2.2px 68–88% → 0.
- **tail-slap (0.5s)**, **slap-dust (0.5s)**, **cloud-bob (1s)**.
- **ear-l / ear-r (4s)**: ∓30° base, ∓40° at 18% and 66%, ∓14° at 49%, ∓34° at 53%.
- **arm-fold-l / arm-fold-r (4s)**: translate(±4.6px,1px) base, ±5px at 18% and 66%.
- **hmph-l (16–30%)**, **hmph-r (64–78%)**, **stomp (42–49%)**, **shadow-pout (4s)**.

## Expression
Cheeks blown up like a balloon, arms folded tight and ears pinned flat, cat-Clawd glares out through squeezed chevron eyes with a little storm cloud hovering over his head. He turns his face away with a huffy puff of air, stomps a foot and swings back to glare at you, then turns away to the other side just as huffily — and all the while his tail thumps the ground: thwap, thwap, thwap.
