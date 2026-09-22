# clawd-dump-truck-smash.svg

Clawd as an unstoppable road-rage dump truck ("泥头车"): he stands on the chassis as the cab of a big blue open-box dump truck, brows knitted, a 💢 throbbing, steam pouring off his head, tearing along a scrolling road at full speed and ramming four obstacles in a row — a traffic cone, a wooden crate, a striped road barrier and a green pixel bug — each launched in a spinning arc over the truck. 3s loop.

## Body
Standard torso 11x7 raised to (2,4), #DE886D, eyes 1x2 at (4,6)/(10,6), arms 2x2 at (0,7)/(13,7), and the four 1x2 legs at (3,11)/(5,11)/(9,11)/(11,11) standing on the chassis top (y 13). Above the eyes two black angry brows: 1.9x0.55 bars at (3.5,5)/(9.6,5) statically rotated ±22° so their inner ends slant down. The eyes sit in an `eyes-drive` group (translateX(1.5px) scaleY(0.75) squint, snapping to scaleY(0.05) for ~2% at each hit) wrapping an `eye-twitch` group (0.15s scale(1.12,0.92) flicker). The vehicle: chassis (-8.5,13) 24x1.3 #37474F, bumper (15,12.2) 1.4x2.1 #546E7A, four wheels (tire r 1.7 #212121, hub r 0.8 #9E9E9E, spinning 0.36x1.4 spoke #424242) — twin rear axles at (-6.3,14.6)/(-2.7,14.6) under the dump body and two front at (5,14.6)/(11.5,14.6). Two wrapper groups: `hit-jolt` (translate(-0.9px,-1.2px) kick-back at every hit, 3s) around `truck-bob` (0.2s translate(±0.25px, -0.7px) engine shake).

## Props
- **Dump body** (blue open box, x -8..0, y 5..13, in a `bed-jiggle` group hopping translateY -0.35px at 0.2s): box #1E88E5, rim (-8.3,4.5) 8.6x0.7 #64B5F6, raised headboard (-1.4,2.4) 1.4x2.8 #1565C0 with a #64B5F6 cap next to the cab, two horizontal reinforcement ribs #1565C0 at y 7.6 and 10.2, a hinged tailgate (-8.7,4.7) 0.8x8.3 #1565C0 with #0D47A1 hinges, and three #5D4037 mud splats on the side.
- **Heaped dirt**: brown (#795548) mound stacked from y 3.2 up to a peak at y 0.6 with #8D6E63 highlights and a #5D4037 shadow clod, plus two #6D4C41 clods hopping translateY -0.9px at 0.2s.
- **Exhaust stack**: 0.8x2.6 pipe #37474F on the headboard at (-1.1,-0.2) with a #263238 cap; three #616161 rounded smoke puffs blown backward translate(-6px,-1.6px) scale 0.5→1.5 opacity 0→0.9→0 at 0.5s, staggered.
- **Head steam**: three #B0BEC5 rounded puffs at the head top (x 3.6–11.1, y 2.4) blown backward translate(-3.5px,-2px) at 0.375s, staggered.
- **Beacon**: #455A64 mount (6.5,3.2), #FFC107 lamp (6.9,2.1) flashing 1↔0.3 at 0.3s (step-end), #FFE082 glow pulsing in sync.
- **Rage mark**: one 💢 (4 L-shaped polylines, stroke #FF3D00 width 0.65) at (12.4,1.2) above the top-right of the head, always on, pulsing scale 1→1.25 at 0.3s inside a `rage-hit` group that blows it up to scale 1.45 at every hit.
- **Obstacles** (drawn behind the truck inside a `scene-clip` clipPath x -9..20, parked at translate(4.5px,0) outside it): 1 traffic cone (#37474F base, #FF7043 tiers, #ECEFF1 stripe); 2 wooden crate (#6D4C41 frame, #A1887F face, cross plank lines); 3 striped barrier (#E53935 / #ECEFF1 0.8x1.1 stripes on two #546E7A legs); 4 green pixel bug facing the truck (#66BB6A body, #2E7D32 head and spots, #ECEFF1 eye, #1B5E20 legs and antennae). All parked at x 16.3–19.3 with the ground at y 16.3.
- **Bumper sparks**: four squares (#FFC107 0.9, #FF9800 0.8, #FFEB3B 0.6, #FFC107 0.6) at the bumper face (~16.2, 11.4–14.7), fanning translate (1.5,-3.5) / (3,-1) / (-1,-4) / (2.5,-3) at every hit.
- **Road dashes**: six #9E9E9E 2.5x0.5 bars at y=17 spaced 6 apart, scrolling translateX 0→-6px every 0.3s (20 units/s), clipped to x -9..20.
- **Wind streaks**: six #B0BEC5 3–4x0.4 bars at y -2.2 / -0.9 spaced 12 apart, scrolling -12px every 0.6s (same 20 units/s), clipped.
- **Dust puffs**: two #BDBDBD squares behind the rear wheels (-8.4,14.9)/(-7.8,15.4), 0.3s.
- **Ground shadow**: (-7,15) 23x1 #000000 opacity 0.5, pulsing scaleX with the bob.

## Animation
- **obs-1..4 (3s, linear)**: hits at H = 8% / 30% / 52% / 74%. Each: parked at translate(4.5px,0) until H-7.5% → slides in at road speed to (0,0) at H → H+0.4% nudge (-0.3px,-0.8px) → H+2.8% (-3,-11~-12) → H+5.6% (-9,-16~-17) → H+8.4% (-15,-15) → H+11.2% (-21,-6) → H+13% (-24,0) opacity 0, spinning 400–520° (direction alternating) → reset while invisible.
- **hit-jolt (3s)**: translate(-0.9px,-1.2px) at H+0.8%, back by H+4%, four times.
- **eyes-drive (3s)**: squint, shut H+0.6%–H+2.4%, open by H+4%, four times. **eye-twitch (0.15s)** runs throughout.
- **rage-hit (3s)**: scale 1 → 1.45 at H+1% → 1 by H+5.3%, four times; **anger-pulse (0.3s)** underneath.
- **spark-a/b/c/d (3s)**: four bursts, appearing at H(+0–0.7%), faded by H+4.7–5.4%.
- **truck-bob (0.2s)**, **bed-jiggle (0.2s)**, **clod-hop (0.2s, second clod delayed 0.1s)**, **spin (0.25s, linear)**, **beacon-flash / beacon-glow (0.3s)**, **smoke-stream (0.5s ×3)**, **steam-stream (0.375s ×3)**, **road-scroll (0.3s, linear)**, **wind-scroll (0.6s, linear)**, **puff (0.3s)**, **shadow-bob (0.2s)**.

## Expression
Brows locked in a V, eyes twitching, steam and a 💢 boiling over his head, Clawd stands braced on top of his big blue dump truck as it hammers down the road flat out — beacon strobing, black smoke ripped backward, wind streaking past, dirt bouncing in the heaped bed. Nothing slows him down: a cone, a crate, a striped barrier and a hapless bug come at him one after another and each one is punted off the bumper in a shower of sparks, cartwheeling high over his head and out of sight behind the tailgate, while the 💢 flares bigger with every hit.
