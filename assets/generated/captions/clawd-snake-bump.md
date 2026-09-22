# clawd-snake-bump.svg

Impatience level 1 ("the patient one"): Clawd works his way down the screen like the snake in the Snake game — stepping on a grid with hard cuts, bumping the invisible screen edge at the end of each row, dropping a row, and finally eating an apple before wrapping back to the top. 6s loop.

## Body
Standard torso 11x7 at (2,6), #DE886D, four 1x2 legs at (3,13)/(5,13)/(9,13)/(11,13) that alternate a gentle 0.4s step (outer pair vs inner pair, translateY -0.8px). The whole body sits in a `snake-grid` group that moves on a 2-unit grid with `step-end` timing (no easing, like the game), inside a `snake-vis` group that blinks the body out for the wrap-around, and a `bump-nudge` group that adds the smooth part: a 0.6px shove plus scale(0.92,1.05) squash at each edge bump (origin at the feet) and a 1.2px hop while eating. Eyes are normal 1x2 rectangles at (4,8)/(10,8) on one 6s timeline: translateX(±1.5px) toward the walking direction, translateY(1px) looking down before each drop, scaleY(0.05) shut for 2% at each bump, hidden while a second ^^ polyline set shows during the eating beat, and a single blink at 94% while waiting at the top. Arms 2x2 at (0,9)/(13,9) swing rotate(10°↔-6°) / (-10°↔6°) at 0.4s about the shoulders.

## Props
- **Anger pops**: two 💢 marks (4 L-shaped polylines, stroke #FF3D00 width 0.6) at (12.2,3.4) and (0.8,3.4) above the head corners, each popping in (scale 0.5→1.25→1, opacity 0→1) only at its bump and fading out within ~7% of the cycle.
- **Impact sparks**: two small squares (#FFC107 0.8, #FF9800 0.6) per edge in world space — right edge at (19.2,1.3)/(19.4,2.8) for row 1, left edge at (-5,5.3)/(-5.2,6.8) for row 2 — flying outward and fading over ~4%.
- **Pixel apple**: at the bottom-right (18–20.5, 9.2–12.5): red body #E53935 (2.5x2 + a 1.5x0.5 cap), stem #6D4C41, leaf #43A047, highlight #FF8A80. Drawn behind Clawd; disappears at 69% (eaten) and reappears at 88% with the wrap.
- **Ground shadow**: stays on the ground at y=15, follows the body horizontally only, and grows scaleX 0.55→0.75→1 (opacity 0.3→0.5) as Clawd comes down the rows.

## Animation
- **snake-grid (6s, step-end)**: row 1 at dy=-8: translateX -4 → -2 → 0 → 2 → 4 at 0/5/8.33/11.67/15%; hold at (4,-8) until 25%; down (4,-6) 25% → (4,-4) 28.33%; row 2: 4 → 2 → 0 → -2 → -4 at 28.33/31.67/35/38.33/41.67%; hold until 51.67%; down (-4,-2) 51.67% → (-4,0) 55%; row 3: -4 → -2 → 0 → 2 → 4 at 55/58.33/61.67/65/68.33%; hold on the apple until 88%; jump back to (-4,-8) at 88%.
- **snake-vis (6s, step-end)**: opacity 1 → 0 at 85% → 1 at 88% (wrap through the wall).
- **bump-nudge (6s)**: 15% → 16.5% translate(0.6px,0) scale(0.92,1.05) → 19% back; 41.67% → 43.2% translate(-0.6px,0) scale(0.92,1.05) → 45.7% back; 71% → 73% translate(0,-1.2px) hop → 75.5% back.
- **step-outer / step-inner (0.4s)**: outer legs lift translateY(-0.8px) at 50%, inner legs out of phase.
- **arm-swing-a / arm-swing-b (0.4s)**: rotate(10°)↔(-6°) and rotate(-10°)↔(6°).
- **eyes-normal (6s)**: 0–15% translate(1.5px,0) → 16–18% scaleY(0.05) shut → 23–30% translate(0,1px) look down → 33–41.67% translate(-1.5px,0) → 42.7–44.7% shut → 50–57% look down → 60–68.5% translate(1.5px,0) → 69.5–70% shut then opacity 0 → 84.5–86% back to opacity 1 open → 94% scaleY(0.1) blink → 98–100% translate(1.5px,0).
- **eyes-happy (6s, step-end)**: ^^ eyes opacity 1 from 70% to 84%.
- **anger-r / anger-l (6s)**: pop at 16.5% / 43.2%, gone by 23% / 49.7%.
- **spark-r1/r2 (6s)**: 15.8–19.5% / 16.2–20% translate(1.2,-1.5) / (1.4,0.8). **spark-l1/l2**: 42.5–46.2% / 42.9–46.7% mirrored.
- **apple-vis (6s, step-end)**: opacity 1 → 0 at 69% → 1 at 88%.
- **shadow-grid (6s, step-end)**: translateX follows the grid; scaleX 0.55 on row 1, 0.65–0.75 on row 2, 0.85–1 on row 3; opacity 0 during the wrap.

## Expression
Clawd plods across the top row one square at a time, thumps into the edge of the screen with a little 💢 and a squint-shut wince, tilts his eyes down and drops a row, plods back the other way, thumps the other edge, drops again, marches onto the apple, munches it with happy ^^ eyes and a small hop, then blinks out through the wall and reappears at the top-left, blinking, ready to do it all over.
