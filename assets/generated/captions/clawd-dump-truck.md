# clawd-dump-truck.svg

Clawd as a reckless dump truck ("泥头车"): his own torso, eyes and arms are the cab, sitting on a dark chassis with three spinning wheels, a flashing beacon on his head and a steel dump bed full of dirt trailing behind him. He speeds along a scrolling road, then the bed tips up and dirt clods spill out onto the road before it drops back down. 4s loop.

## Body
Standard torso 11x7 at (2,6), #DE886D, eyes 1x2 at (4,8)/(10,8), arms 2x2 at (0,9)/(13,9) — all kept intact so he is still Clawd. The four legs are replaced by the vehicle: a chassis bar (-6.5,13) 22x1.3 #37474F with a front bumper (15,12.4) 1.2x1.9 #546E7A, and three wheels (tire circle r 1.7 #212121, hub r 0.8 #9E9E9E, a 0.36x1.4 spoke #424242 that spins) centred at (-3.5,14.6), (4.5,14.6), (11.5,14.6), drawn in front of the chassis and the bed. Everything is inside a `truck-bob` group that jitters translate(0.15px,-0.45px)/(-0.15px,-0.1px) at 0.3s like an engine on a rough road. The eyes stay in a reckless scaleY(0.7) squint looking ahead translateX(1.5px), glance back translateX(-1.5px) while the bed is dumping (57–74%), and blink once at 29.5% and 89.5% — all on one 4s timeline.

## Props
- **Dump bed**: steel box (-6,7) 6x6 #607D8B with a lighter rim (-6.3,6.6) 6.6x0.7 #90A4AE and two vertical ribs #455A64; it tips about its rear-bottom corner (-6,13) via `bed-tip` so the front lifts and the load slides out the back.
- **Dirt load**: a mound of brown rects (#795548 5.2x1.6 / 3.8x1.1 / 1.9x0.9 stacked from y 5.6 up to 3.8) with #8D6E63 highlights and a #5D4037 shadow clod, inside the bed group so it tilts with it.
- **Dirt clods**: four 0.8–1.2 squares (#795548 / #6D4C41 / #8D6E63) in world space at the tipped rear rim (~-8.5, 6–7), tumbling down-left to the road (translate up to (-3.3, 9.2), rotate ±150–260°) and vanishing on landing.
- **Exhaust stack**: 0.8x4.5 pipe #37474F at (0.3,3) with a cap #263238, between bed and cab; three dark-gray (#616161) rounded 1.1–1.3 squares of smoke rise translate(-2.2px,-4px) scale 0.5→1.5 opacity 0→0.9→0 at 0.8s, staggered 0/0.27/0.54s.
- **Beacon**: mount (6.5,5.2) 2x0.8 #455A64, lamp (6.9,4.1) 1.2x1.2 #FFC107 flashing opacity 1↔0.35 at 0.5s (step-end), and a #FFE082 glow 2.8x2.2 pulsing scale 1→0.6 / opacity 0.55→0 in sync.
- **Road dashes**: five gray (#9E9E9E) 2.5x0.5 bars at y=17 spaced 6 apart, scrolling translateX 0→-6px every 0.4s (seamless), clipped to x -9..16 by a clipPath.
- **Speed lines**: three gray (#9E9E9E) 2–2.5x0.5 bars behind the bed at x ~-10.5..-8, flickering opacity 0.9↔0.35 with a -0.8px drift at 0.3s.
- **Dust puffs**: two gray (#BDBDBD) 1/0.8 squares behind the rear wheel (-6.6,14.9)/(-6,15.4), 0.4s, drifting translate(-2px,-1.4px).
- **Ground shadow**: (-5,15) 21x1 #000000 opacity 0.5 under the whole truck, pulsing scaleX 1↔1.03 with the bob.

## Animation
- **truck-bob (0.3s)**: translate 0 → (0.15px,-0.45px) at 30% → (-0.15px,-0.1px) at 70% → 0.
- **bed-tip (4s)**: rotate 0 until 55% → -22° at 65% → held to 75% → +1.5° bounce at 83% → 0 at 85%.
- **clod-1..4 (4s, ease-in)**: appear at 59% / 62% / 65% / 67% just outside the rear rim, fall to translate (-2.5,8.6) / (-3.3,8.8) / (-1.9,9) / (-2.9,9.2) with rotation by 69% / 72% / 75% / 77%, then opacity 0.
- **spin (0.4s, linear)**: each wheel spoke rotates 360°.
- **beacon-flash (0.5s, step-end)** / **beacon-glow (0.5s)**: lamp and glow pulse together.
- **eyes-drive (4s)**: translateX(1.5px) scaleY(0.7) 0–28% → blink 29.5% → 31–54% ahead → 57–74% translateX(-1.5px) glance back → 77–88% ahead → blink 89.5% → 91–100% ahead.
- **smoke-rise (0.8s ×3 staggered)**, **road-scroll (0.4s, linear)**, **lines-flicker (0.3s)**, **puff (0.4s, second puff delayed 0.2s)**, **shadow-bob (0.3s)**.

## Expression
Squinting straight ahead with his beacon flashing and black smoke puffing from the stack, Clawd the dump truck rattles down the road at full tilt, wheels spinning and dust kicking up behind the rear tyre. Halfway through he cocks the bed up without slowing down, glances back over his shoulder as clods of dirt tumble out onto the road, drops the bed with a bounce and floors it again.
