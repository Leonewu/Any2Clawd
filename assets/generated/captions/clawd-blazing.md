# clawd-blazing.svg

Clawd burning with rage: a small crown of pixel fire hovers above his head and a small flame burns on the ground at each side of him — none of it touching him — embers drift up, and every 1.5 seconds the blaze surges while he puffs up with it. 3s loop.

## Body
Standard torso 11x7 at (2,6), #DE886D, four 1x2 legs at (3,13)/(5,13)/(9,13)/(11,13), arms 2x2 at (0,9)/(13,9). Two wrapper groups: `tremble` (0.1s full-body micro-shake, translate ±0.15px) around `flare-body` (1.5s: scale(1.06,0.95) at 6% → scale(0.98,1.06) at 14% → 1 by 24%, in step with the fire surge; origin at the feet). Over the torso a `flush` overlay (2,6) 11x7 #D32F2F pulsing opacity 0.2↔0.42 at 0.5s. Two black angry brows 1.9x0.55 at (3.5,6.9)/(9.6,6.9), statically rotated ±22° so the inner ends slant down. Eyes 1x2 at (4,8)/(10,8) held in a scaleY(0.6) glare with a single scaleY(0.05) blink at 42% of the 3s cycle. Arms tremble on their own 0.1s cycle (arm-tremble-l/r).

## Props
- **Fire** (in a `fire-surge` group with origin (7.5,15)): three pixel flame tongues, each stacked rects in three tones — outer #FF3D00, middle #FF9100, core #FFD54F. Each tongue is drawn at 2x and shrunk with a static `scale(0.55)` wrapper anchored at its base. A floating crown above the head: anchored at (7.5,3.5) — bottom at y 3.5 (2.5 units clear of the head top at y 6), about 3.3 wide, rising to y 0.2; flicker origin (7.5,3.5). Two small flames standing on the ground at the sides, about 2.2 units clear of the arms: left anchored at (-3,15) rising to y 10.9, right anchored at (18,15) rising to y 10.9. Nothing touches the body.
- **Embers**: five 0.5–0.7 squares (#FFD54F / #FF9100 / #FFEB3B) leaving the three flames, drifting up 2–2.5 units with slight x drift, shrinking scale 1→0.4, opacity 0→0.95→0, on 0.75s / 1.0s cycles with staggered delays.
- **Ground shadow**: (3,15) 9x1 #000000 opacity 0.5, trembling with the body.

## Animation
- **fire-surge (1.5s)**: scale(1,1) → scale(1.04,1.12) at 8% → scale(0.98,1.02) at 18% → 1 by 28% (two surges per loop).
- **flick-a (0.375s)** crown: scale(1,1)→scale(1.05,1.06) translateX(0.3px); **flick-b (0.5s, right delayed 0.2s)** side flames: scale(1,1.04) translateX(-0.2px)↔scale(0.96,0.94) translateX(0.2px).
- **flare-body (1.5s)**, **tremble (0.1s)**, **arm-tremble-l / arm-tremble-r (0.1s)**, **flush (0.5s)**.
- **eyes-fury (3s)**: scaleY(0.6) glare, shut scaleY(0.05) at 42%, open by 44%.
- **ember-1..5 (0.75s / 1.0s)**: rise and fade.

## Expression
Clawd stands rooted to the spot, brows slammed down, eyes narrowed to slits, his whole body flushing red and quivering with fury; a small crown of fire hovers over his head and two little flames burn on the ground beside him, licking and swaying, sparks floating up, and every couple of beats the whole blaze flares up as he swells with rage.
