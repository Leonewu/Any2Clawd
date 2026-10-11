# clawd-morning-stretch.svg

A wordless good-morning: Clawd starts curled up asleep, stretches tall with both arms raised overhead and a squeezed-shut yawn, then drops its arms and pops its eyes open just as a little pixel sun in the top-right sky flashes its rays. 5s loop, everything on one shared timeline.

## Body
Standard torso 11x7 at (2,6), #DE886D, with four 1x3 legs at (3,12)/(5,12)/(9,12)/(11,12) planted outside the animated group. Torso and eyes sit in a `body` group that squashes/stretches from the feet (origin 7.5,13): curled scale(1.12,0.75), stretched scale(0.92,1.1). Three eye sets switch by opacity on the same timeline: shut "- -" (two 1.6x0.45 rects at y 9.2), yawn-squeezed "> <" (polylines (3.6,8.4)→(5.1,9.2)→(3.6,10) / (11.4,8.4)→(9.9,9.2)→(11.4,10), stroke 0.6), and normal open 1x2 eyes that pop in at scale 1.4. Arms are 2x2 at (0,9)/(13,9), drawn after the torso: curled they tuck to translate(±0.5px,1.5px); raised they stretch to scale(1,2), tilt ±18° outward about their bottom (1,11)/(14,11) and translate(±2.2px,-4.6px) so their base sits on the torso's top corners.

## Props
- **Sun**: pixel disc #FFC83D (3x1 / 5x4 / 3x1 rects, centered (16,-2)) with a #FFE082 highlight pixel, in the top-right sky clear of Clawd's raised arms. Eight #FFB300 0.8x1.3 rays at radius ~4.6 (rotated copies about (16,-2)), hidden until the wake moment.
- **Ground shadow**: (3,15) 9x1 #000000 opacity 0.5, widening when curled and narrowing when stretched.

## Animation
- **body-stretch (5s)**: curled scale(1.12,0.75) with a slow breath (11% 1.14,0.73) → 40% stretched (0.92,1.1), held to 52% → 58% squash (1.06,0.92) → 62% rebound (0.97,1.05) → 66–86% normal → 96% curled again.
- **arm-l / arm-r (5s)**: tucked → 40% raised overhead, quivering 44/48/52% (rotate ±16–24°, scaleY 2–2.05) → 58% dropped → 66% rest → 96% tucked.
- **eyes-shut / eyes-yawn / eyes-open (5s)**: shut 0–29% → "> <" yawn 30–53% → shut 54–57% → open 58–87% → shut 88–100%.
- **eyes-pop (5s)**: open eyes scale 1.4 at 58% → 1 by 64%.
- **sun-rise (5s)**: translateY 2.5px opacity 0 until 26% → floats up and brightens to 58% → holds → 96% sinks and fades.
- **rays-flash (5s)**: hidden until 56% → burst scale 0.8→1.3 at 61% → settles, small pulse at 77% → fades by 92%.
- **shadow (5s)**: scaleX 1.15 curled → 0.9 stretched → 1.06 squash → 1.

## Expression
Clawd wakes up the way everyone does: curled in a sleepy lump, then a huge full-body stretch with claws reaching for the sky and eyes squeezed into a yawning "> <", a little shiver at the top — and then flop, arms down, eyes snap wide open, and the morning sun in the corner bursts into rays. Good morning without a single word.
