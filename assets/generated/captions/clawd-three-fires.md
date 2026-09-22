# clawd-three-fires.svg

Clawd so angry that three little fires hover above his head — a bigger one in the middle and two smaller ones at the sides, each licking and swaying on its own rhythm with embers drifting up — while he huffs and puffs, flushed red and shaking. 3s loop.

## Body
Standard torso 11x7 at (2,6), #DE886D, four 1x2 legs at (3,13)/(5,13)/(9,13)/(11,13), arms 2x2 at (0,9)/(13,9). A `tremble` group (0.1s micro-shake) wraps everything; inside it the torso, face, arms and the three fires sit in a `huff` group (0.6s heavy breathing: scale(1.04,1.05) translateY(-0.4px) at 45%, origin at the torso bottom (7.5,13)) while the legs stay planted. Over the torso a `flush` overlay (2,6) 11x7 #D32F2F pulsing opacity 0.2↔0.42 at 0.6s in time with the breathing. Two black angry brows 1.9x0.55 at (3.5,6.9)/(9.6,6.9) rotated ±22°. Eyes 1x2 at (4,8)/(10,8) held at scaleY(0.6) with one scaleY(0.05) blink at 57%. Arms tremble at 0.1s.

## Props
- **Three fires** hovering above the head — bottoms at y 4, 2 units clear of the head top at y 6 — each stacked rects in three tones (outer #FF3D00 / middle #FF9100 / core #FFD54F), drawn at 2x and shrunk with a static `scale(0.5)` wrapper anchored at its base: left fire anchored at (3.5,4), about 1.5 wide, rising to y 1.25; center fire anchored at (7.5,4), about 2 wide, rising to y 0.6; right fire anchored at (11.5,4), about 1.5 wide, rising to y 1.25. They ride inside the huff group so they rise and fall with his chest.
- **Embers**: five 0.5–0.7 squares (#FFD54F / #FFEB3B / #FF9100) leaving the flame tips, drifting up about 2 units, shrinking scale 1→0.4 and fading, on 0.75s / 1.0s cycles with staggered delays.
- **Ground shadow**: (3,15) 9x1 #000000 opacity 0.5, trembling.

## Animation
- **flick-a (0.375s)** center fire: scale(1,1)↔scale(1.06,1.15) translateX(0.3px); **flick-b (0.5s, right fire delayed 0.25s)** side fires: scale(1,1.08) translateX(-0.25px)↔scale(0.95,0.92) translateX(0.25px).
- **huff (0.6s)**: chest heaves scale(1.04,1.05) translateY(-0.4px) at 45%.
- **flush (0.6s)**: opacity 0.2 → 0.42 at 45% → 0.2.
- **eyes-fury (3s)**: scaleY(0.6) glare, shut at 57%, open by 59%.
- **tremble (0.1s)**, **arm-tremble-l / arm-tremble-r (0.1s)**, **ember-1..5 (0.75s / 1.0s)**.

## Expression
Clawd plants his feet and seethes, chest heaving with heavy breaths, face flushing redder with each one, brows crushed down over slitted eyes and his whole body quivering — and over his head three little fires hover and burn, the middle one highest, the side ones flickering along, sparks floating off their tips.
