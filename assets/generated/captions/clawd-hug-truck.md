# clawd-hug-truck.svg

A comforting hug for a little dump truck: Clawd holds a cute toy-sized dump truck — light blue, rounded, with a small face in its cab window, a grey beacon and a round heap of dirt. At first he holds it out a little and its face is down while he looks at it with plain eyes; then he pulls it in to his chest, rocks it, squeezes it twice and pats its back, and the truck blinks and comes up smiling ^^ with pink cheeks, its beacon warming to yellow, while Clawd's own eyes go ^^ and his cheeks blush and two small hearts drift up. 5s loop; both blink at the loop seam so the reset back to the sad face is hidden. The truck is a held prop with its own expression (the cheer-up arc is the point of the sticker).

## Body
Standard torso 11x7 at (2,6), #DE886D, legs 1x2 at (3,13)/(5,13)/(9,13)/(11,13) planted. Everything rocks in a `sway` group rotate(-2.5°↔2.5°) about the feet at 2.5s. Torso, face, truck and arms sit in a `body` group (origin at the feet) that pulls in scale(1.04,0.97) / (1.05,0.965) on the squeezes (46% / 56%). Two eye sets on one timeline: plain 1x2 bars at (4,8)/(10,8) shifted translateY(0.5px) (looking down at the truck), visible 0–43% with a blink at 19.5%, closing at 43% to hand over; happy ^^ polylines (stroke #000000 0.8) from 44%, squinting scaleY(0.7) on each squeeze, closing at 96% while the plain eyes reopen by 98.5%. Cheeks #F8BBD0 1.5x0.6 at (2.6,10)/(10.9,10) fade in 43–47% and out 95–98%. Both arms 2x2 (0,9)/(13,9), outlined 0.3 #B85C42, come round to the front: holding out at translate(±4px,4.2px) until 22%, wrapped at (±4.5px,3.4px) from 30%, tightening to ±5.1/±5.2px on the squeezes; the right arm lifts to (-4.3px,2.6px) at 68% and 76% for the pats.

## Props
- **Toy dump truck** (side view, cab on the left, held across the lower chest in a `truck` group with origin (7.5,14)): chassis (3.7,13.2) 7.8x0.6 #546E7A; three wheels r 0.65 #37474F with r 0.25 #B0BEC5 hubs at (4.8,13.95)/(8.9,13.95)/(10.6,13.95); bed (6.9,11.3) 4.6x2.2 rx 0.4 #64B5F6 with a #90CAF9 rim; a round dirt heap (#8D6E63 3.8x1.2 + #A1887F 2.4x0.9, both rounded) on top; cab (3.5,10.6) 3.2x2.9 rx 0.5 #64B5F6 with a #E3F2FD window (3.9,11) 2.4x1.5. In the window, two faces on one timeline: **sad** (`tf-sad`, #37474F) — two drooping 0.45x0.55 eyes at (4.25,11.55)/(5.5,11.55) under two 0.7x0.2 brows tilted ∓22° into a 八 shape — visible until 47%; **happy** (`tf-happy`) — two tiny ^^ polylines (stroke #37474F 0.32) from 48%, plus #F8BBD0 0.5x0.25 cheeks fading in 47–51%. A beacon on the cab roof at x 5.7–6.6 (clear of Clawd's eye): grey #B0BEC5 lamp until 49%, then a warm #FFC107 lamp with a #FFE082 glow 1.3x1 pulsing scale 1→1.15 / opacity 0.5–0.7 until 97%. The truck sits translateY(0.9px) lower while held out (0–22%), pops up translateY(-0.4/-0.5px) scale(0.96,1.04)/(0.95,1.05) on the squeezes and dips translateY(0.2px) scale(1.02,0.98) on the pats.
- **Hearts**: two #F48FB1 pixel hearts (5 rects, ~1.7 wide) at (11.4,6.2) and (1.4,6.8), rising translate(0.8px,-5.2px) with opacity 0→0.95→0 over 3–38% of a cycle, delayed 3s and 4s so they appear after the truck is smiling.
- **Ground shadow**: (3,15) 9x1 #000000 opacity 0.5, shifting translateX ±0.35px with the sway.

## Animation
- **sway (2.5s)**, **shadow (2.5s)**.
- **truck (5s)**: 0–22% translateY(0.9px) → 30% 0 → squeezes 46% / 56% → pats 68% / 76%.
- **arm-l / arm-r (5s)**: hold out → wrap at 30% → tighten 46% / 56% → right-arm pats 68% / 76%.
- **body (5s)**: squeezes at 46% and 56%.
- **eyes-plain / eyes-happy / cheeks-big (5s)**: plain until 43%, ^^ from 44%, blink hand-back at 96–98.5%.
- **tf-sad / tf-happy / tf-cheeks (5s)**: sad until 47%, blink, ^^ from 48%, hand-back at 96–98.5%.
- **beacon-grey / beacon-warm (5s, step-end)** at 49% / 97%, **beacon-glow (5s)**.
- **heart (5s ×2, delays 3s / 4s)**.

## Expression
Clawd holds the little blue dump truck out in front of him and looks down at it — its brows drooping, its beacon dull — then gathers it in against his chest and rocks it slowly, gives it two gentle squeezes that lift it up a little and two soft pats on the back. The truck blinks, and when its eyes open they are happy ^^ with pink cheeks, its beacon glowing warm yellow; Clawd's eyes crinkle into ^^ too, his cheeks go pink, and a couple of small hearts float up between them.
