# clawd-snake-rush.svg

Impatience level 2 ("the hasty one"): the same Snake-game zig-zag as clawd-snake-bump, but at full charge — Clawd dashes across each row, headbutts the obstacle waiting at the end (crate, trash can, traffic cone) so it tumbles away, drops a row without pausing, and wraps back to the top while the obstacles drop back in. 4s loop.

## Body
Standard torso 11x7 at (2,6), #DE886D, four 1x4 legs at (3,11)/(5,11)/(9,11)/(11,11) (2px overlap into the torso so the lean never disconnects them), scrambling out of phase at 0.25s (translateY -1.2px) even when standing. Groups from the outside in: `charge-move` (smooth translate across the three rows dy -8/-4/0 with cubic-bezier(0.75,0,1,1) acceleration on each dash and ease-out overshoot at the hits), `rush-vis` (blinks the body out for the wrap), `run-bounce` (0.25s translateY -0.5px), `impact-squash` (scale(0.9,1.08) → (1.05,0.96) at each hit, origin at the feet), and `upper-lean` (torso + eyes + arms + anger mark: translate(∓0.8px,0.4px) leaning back while revving, (±1px,0.3px) leaning into each dash, (±1.2px,0) at impact). Eyes 1x2 at (4,8)/(10,8) on one timeline: scaleY(0.65) angry squint, translateX(±1.5px) toward the dash, scaleY(0.05) shut for 2.5% at each hit, scaleY(0.9) dazed for a beat after. Arms 2x2 at (0,9)/(13,9) with 0.25-opacity drop shadows; the leading arm is pushed in front of the body with translate(∓3px,1px) (right arm on the two rightward rows, left arm on the leftward row) and both swing rotate(15°↔-10°)/(-15°↔10°) at 0.25s.

## Props
- **Anger mark**: 💢 (4 L-shaped polylines, stroke #FF3D00 width 0.6) at (12.2,3.4), always on, pulsing scale 1→1.2 at 0.5s, inside upper-lean so it follows the body.
- **Wooden crate** (row 1, right): 3x3 at (16,4) — frame #6D4C41, face #A1887F, cross plank lines #6D4C41.
- **Trash can** (row 2, left): 3x3 body #90A4AE at (-5,8), ridges #607D8B, lid 3.6x0.7 #607D8B at (-5.3,7.3), handle #455A64.
- **Traffic cone** (row 3, right): base 3x0.7 #37474F at (16,14.3), tiers #FF7043 (2x1.8 / 1.2x1.3 / 0.7x0.7) with a light stripe #ECEFF1.
- **Impact sparks**: three squares (#FFC107 0.8, #FF9800 0.7, #FFEB3B 0.6) at each contact point in world space: (~16,2.5–4.4) row 1, (~-2.8,6.5–8.4) row 2, (~16,10.5–12.4) row 3.
- **Speed lines**: three gray (#9E9E9E) 2–2.5x0.5 bars behind the body on the side opposite the dash (local x -4.5..-2 or 17..19.5), inside charge-move.
- **Dust puffs**: two gray (#BDBDBD) 0.9/0.7 squares behind the feet on each side, gated to the rev windows.
- **Ground shadow**: stays on the ground at y=15, follows x, scaleX 0.55/0.75/1 per row, hidden during the wrap.

## Animation
- **charge-move (4s)**: 0% (-4,-8) → 6% (-4.5,-8) back up → 20% (4,-8) dash → 21.5% (4.4,-8) overshoot → 25% (3,-8) recoil → 30% (4,-4) drop → 32% (4.5,-4) → 44% (-3.5,-4) dash left → 45.5% (-3.9,-4) → 49% (-2.5,-4) → 54% (-4,0) drop → 56% (-4.5,0) → 68% (4,0) dash → 69.5% (4.4,0) → 73% (3,0) → hold to 80% → 84% (-4,-8) (moved while invisible) → hold.
- **rush-vis (4s, step-end)**: opacity 0 from 80% to 84%.
- **run-bounce (0.25s)** / **step-outer / step-inner (0.25s)**: step bounce and scrambling legs.
- **impact-squash (4s)**: squash at 21.5% / 45.5% / 69.5%, recovered by 28% / 52% / 76%.
- **upper-lean (4s)**: rev 0–6%, charge 10–20%, impact 22%, neutral 26–30%, rev-left 32%, charge-left 36–44%, impact 46%, neutral 50–53%, rev 55%, charge 60–68%, impact 70%, neutral 74–84%, rev 88–100%.
- **eyes-charge (4s)**: squint right 0–20% → shut 20.5–23% → dazed 25–29% → squint left 31–44% → shut 44.5–47% → dazed 49–53% → squint right 55–68% → shut 68.5–71% → dazed 73–79% → squint right 84–100%.
- **arm-r-turn / arm-l-turn (4s)**: right arm forward 0–30% and 54–100%, left arm forward 33–51%.
- **arm-swing-a / arm-swing-b (0.25s)** and **anger-pulse (0.5s)**.
- **crate-fly (4s)**: hit at 20% → nudge 20.5% → (2,-4.5) rot 110° at 26% → (2.6,-6.2) rot 200° opacity 0.6 at 31% → gone 32.5% → drops back in from (0,-6) between 86% and 92%.
- **can-fly (4s)**: hit at 44% → (-2,-4.5) rot -110° at 50% → (-2.6,-6.2) opacity 0.6 at 55% → gone 56.5% → drops back in 76–82% while Clawd is still on row 3.
- **cone-fly (4s)**: hit at 68% → (2,-4.5) rot 110° at 74% → (2.6,-6.2) opacity 0.6 at 79% → gone 80.5% → drops back in 90–96%.
- **spark-a1..a3 / b1..b3 / c1..c3 (4s)**: bursts at 20–28% / 44–52% / 68–76%, fanning translate (±2,-2.5) / (±3,-0.5) / (±1.2,-3.5).
- **lines-l (4s)**: 9–20% and 59–68%; **lines-r**: 35–44%.
- **dust-gate-l / dust-gate-r (4s, step-end)** + **puff-l / puff-r (0.4s)**: left dust 0–5%, 53–56%, 85–100%; right dust 31–33%.
- **shadow-rush (4s)**: translateX follows the body; scaleX 0.55 → 0.75 → 1 down the rows; opacity 0 during the wrap.

## Expression
Clawd, glaring with a 💢 pulsing over his head, scrambles for a split second and rockets across the top row into a crate, which spins off as he squashes and bounces back with his eyes clamped shut; without waiting he drops a row, flips around and does the same to a trash can, drops again and flattens a traffic cone, then blinks out through the wall and is instantly back at the top-left, already revving, while the crate, can and cone fall back into place for the next run.
