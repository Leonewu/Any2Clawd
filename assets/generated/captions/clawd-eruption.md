# clawd-eruption.svg

Clawd blowing his top like a volcano: for almost two seconds the pressure builds — a red flush climbs his body from the feet up, he swells and trembles, steam leaks from the top of his head — then three small columns of fire burst up from just above his head (2.5 units clear of it), dark lava rocks fly out in arcs, and he squashes down from the recoil; the columns burn and flicker, then die down and he deflates back to normal. The red flush never drains below 30%, so the static first frame already shows a red-faced, angry-browed Clawd. 4s loop.

## Body
Standard torso 11x7 at (2,6), #DE886D, four 1x2 legs at (3,13)/(5,13)/(9,13)/(11,13), arms 2x2 at (0,9)/(13,9). Wrapper groups: `tremble` (0.1s micro-shake) around `swell` (4s, origin at the feet: scale 1 → scale(1.1,1.07) at 44% as the pressure peaks → scale(0.94,0.86) at 46.5% recoil squash → scale(1.04,1.02) at 50% → 1 by 55%). A `pressure` overlay (2,6) 11x7 #D32F2F opacity 0.55 with origin at the torso bottom (7.5,13) starts at scaleY 0.3 (the lower third of the torso already red), grows to 1 from 0% to 44% (the red climbing up the body), holds to 84%, and drains back to 0.3 by 96%. Two black angry brows 1.9x0.55 at (3.5,6.9)/(9.6,6.9) rotated ±22°. Eyes 1x2 at (4,8)/(10,8): scaleY 0.7 → tightening to 0.35 at 44% → popping wide scaleY(1.15) 46–58% → squint 0.6 62–84% → 0.7 by 92%. Arms tremble at 0.1s.

## Props
- **Fire columns**: three copies of one pixel flame in three tones (outer #FF3D00 / middle #FF9100 / core #FFD54F) hovering above the head, all sharing the base line y 3.5 (2.5 units above the head top). Each is drawn at 2x and shrunk with a static wrapper: the center one anchored at (7.5,3.5) with `scale(0.5)` (about 3 wide, up to y -1.2), the side ones anchored at (4,3.5) and (11,3.5) with `scale(0.35)` (about 2 wide, up to y 0.2), leaving ~1 unit between them. All three sit in one `erupt` group with origin (7.5,3.5) that scales them up from that line; each has its own flicker group (`col-flick` 0.3s for the center, `col-flick-2` / `col-flick-3` 0.25s with 0.1s / 0.2s delays for the sides: scale(1,1)↔scale(1.06,1.06) translateX(0.3px)).
- **Lava rocks**: five dark 0.7–0.9 squares (#3E2723 / #4E342E) starting at the crater (x 6.4–8.2, y 3.2), launched at 46% up and out to translate (±7,6) / (±4.5,9) / (-2,10) with 200° spins, landing beside the body by 60% and vanishing at 63%.
- **Steam**: three #B0BEC5 rounded puffs just above the head (x 5.4–9.5, y 4) rising translate(0,-3.5px) scale 0.5→1.3 at 0.5s, gated visible only from 14% to 44%.
- **Ground shadow**: (3,15) 9x1 #000000 opacity 0.5, trembling.

## Animation
- **pressure (4s, linear)**: scaleY 0.3 → 1 over 0–44%, hold to 84%, back to 0.3 by 96%.
- **swell (4s)**: inflate to 44%, squash at 46.5%, rebound 50%, normal 55–100%.
- **erupt (4s)**: scaleY 0 / opacity 0 until 44% → 44.5% scaleY(0.05) opacity 1 → 47% scaleY(1.08) → 51% 0.95 → 55% 1.03 → 60–84% 1 → 90% 0.55 → 95% 0.08 → 95.5% hidden.
- **col-flick (0.3s)**, **col-flick-2 / col-flick-3 (0.25s, staggered)** flicker.
- **eyes-erupt (4s)**: 0.7 → 0.35 at 44% → 1.15 wide 46–58% → 0.6 squint 62–84% → 0.7 by 92%.
- **lava-1..5 (4s, ease-in)**: hidden until 45%, launched 46%, apex ~52% at (dx·0.6, ≈-4), landing 60%, gone 63%.
- **steam-gate (4s, step-end)** 14–44% + **steam-rise (0.5s ×3 staggered)**.
- **tremble (0.1s)**, **arm-tremble-l / arm-tremble-r (0.1s)**.

## Expression
Clawd stands stock-still and shaking as anger literally rises through him — the red creeps up from his feet to his brow, his body swells, wisps of steam escape the top of his head — until KABOOM: three jets of fire blast up over his skull, chunks of rock sail out to either side and the recoil squashes him flat; he glares up wide-eyed under the roaring jets, settles into a smoulder, and as the fire gutters out he deflates, the red drains most of the way down, and the pressure starts building all over again.
