# clawd-hug.svg

A warm hug: Clawd holds a mini Clawd (half his size) against his chest with both arms wrapped round it, rocking gently side to side; he squeezes it twice, pats its back twice, and a couple of small hearts drift up from between them. Both have happy ^^ eyes and pink cheeks. 4s loop. The mini Clawd is a held prop, drawn in the same colors with a darker outline so it reads against the big body.

## Body
Standard torso 11x7 at (2,6), #DE886D, legs 1x2 at (3,13)/(5,13)/(9,13)/(11,13) planted. The whole pair sits in a `sway` group rocking rotate(-3°↔3°) about the feet (7.5,15) at 2s. Torso, face, mini and arms are in a `body` group (origin at the feet) that pulls in scale(1.04,0.97) / (1.05,0.965) on the two squeezes (18% / 31%). Big eyes are the happy ^^ polylines (stroke #000000 0.8) at (3.5,9.5)→(4.5,8)→(5.5,9.5) / (9.5,9.5)→(10.5,8)→(11.5,9.5), squinting scaleY(0.7) on each squeeze; cheeks #F8BBD0 1.5x0.6 at (2.6,10)/(10.9,10). Both arms 2x2 (0,9)/(13,9) are brought round to the front and down to hold the mini's lower half: translate(±4.5px,3.3px) (x 4.5–6.5 and 8.5–10.5, y 12.3–14.3), tightening to ±5.1/±5.2px on the squeezes; the right arm lifts to translate(-4.3px,2.5px) twice for the pats (58–78%). The arms carry a 0.3 #B85C42 outline so they read over the same-coloured mini.

## Props
- **Mini Clawd**: a full Clawd drawn at base coordinates and placed with a static `translate(4.75,10.5) scale(0.5) translate(-2,-6)` — torso 5.5x3.5 at (4.75,10.5) hanging 1 unit below the big torso, arms 1x1 at its sides, cheeks and ^^ eyes (stroke 1.1 in its own space), no legs (tucked); torso and arms outlined with #B85C42 (0.6 in its own space) so the same-coloured shape stays legible. In a `mini` group (origin (7.5,14)) that pops up translateY(-0.4/-0.5px) scale(0.95,1.05) on the squeezes and dips translateY(0.2px) scale(1.02,0.98) on the pats.
- **Hearts**: two #F48FB1 pixel hearts (5 rects, ~1.7 wide) at (11.4,6.2) and (1.4,6.8), rising translate(0.8px,-5.2px) with opacity 0→0.95→0 over the first half of a 4s cycle, the second delayed 2s.
- **Ground shadow**: (3,15) 9x1 #000000 opacity 0.5, shifting translateX ±0.4px with the sway.

## Animation
- **sway (2s)**: rotate -3° ↔ 3° (two rocks per loop).
- **body (4s)**: scale(1,1) → (1.04,0.97) at 18% → 1 → (1.05,0.965) at 31% → 1 by 36%.
- **arm-l / arm-r (4s)**: wrapped translate(±4.5px,3.3px); ±5.1px at 18%, ±5.2px at 31%; right arm pats at 63% and 73% (translate(-4.3px,2.5px)).
- **mini (4s)**: pop-ups at 18% and 31%, dips at 64% and 74%.
- **eyes-big (4s)**: scaleY 0.7 at 18% and 31%.
- **heart (4s ×2, offset 2s)**, **shadow (2s)**.

## Expression
Clawd cradles a tiny Clawd against his chest, arms wrapped snug around its middle, and rocks it slowly from side to side, both of them beaming ^^ with pink cheeks; twice he gives it an extra squeeze that lifts it up a little and makes his eyes crinkle, then pats its back, pat pat, while little hearts float up between them.
