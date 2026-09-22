# catclawd-happy.svg

Cat-form Clawd bursting with joy: he crouches, hops up and spins a full turn in the air, lands with a squash and a bounce of the ears, then does two happy little hops with his tail quivering, surrounded by sparkles and small hearts. 4s loop. First catclawd sticker; the cat form is documented in `catclawd-body-structure.md`.

## Body
Cat-form Clawd (see `catclawd-body-structure.md`): standard torso 11x7 at (2,6), four 1x2 legs, arms 2x2 at (0,9)/(13,9), plus stair-step ears with pink inner ears, a curled tail behind the lower right of the torso, two black whiskers per side, a pink nose and pink cheeks — all in Clawd's own colors. Happy ^^ polyline eyes (stroke #000000 0.8) the whole time. The whole cat sits in a `hop` group (translateY + squash/stretch, origin at the feet) wrapping a `spin` group (scaleX 1 → -1 → 1 about (7.5,15), i.e. a horizontal flip that swaps ears, tail and whiskers to the other side). Arms rotate about the shoulders (2,10)/(13,10): raised rotate(±70°) during the flight, rotate(±30°/±25°) on the happy hops. Ears rotate about their bases (3.2,6)/(11.8,6): a small tilt on take-off, a ±22° bounce on landing, small nods on the hops. The tail sways rotate(-18°↔18°) about its root (13.6,12.2) at 0.5s throughout.

## Props
- **Sparkles**: four 4-point pixel stars (two 0.7x2.2 crossed bars) in #FFD54F / #FFF59D at (-1.5,3), (16.5,1.5), (2,-1.5), (13.5,-1), popping scale 0.2→1→0.9→0.2 with a 70° twist and opacity 0→1→0 over 14–40% of the cycle, delays 0/0.5/1.0/2.3s.
- **Hearts**: two #F48FB1 pixel hearts (5 rects, ~1.7 wide) at (-1.6,6) and (15.2,4.5), rising translate(0.8px,-4.5px) with opacity 0→0.95→0 over 2–34% of the cycle, delayed 2.5s / 3.1s so they appear during the happy hops.
- **Ground shadow**: (3,15) 9x1 #000000 opacity 0.5, widening on crouch/landing (scaleX 1.1–1.15) and shrinking to 0.6 / opacity 0.2 at the top of the jump.

## Animation
- **hop (4s)**: 0–6% rest → 12% crouch translateY(0.6px) scale(1.08,0.88) → 18% translateY(-2.5px) scale(0.96,1.06) → 30% apex translateY(-4.2px) → 42% (-2.5px) → 49% land → 52% squash scale(1.12,0.84) → 57% scale(0.98,1.03) → 61% rest → 66% dip → 72% hop translateY(-1.4px) → 78% squash → 82% rest → 86% hop (-1.1px) → 91% squash → 95–100% rest.
- **spin (4s)**: scaleX 1 until 12% → -1 at 30% → 1 at 49% → hold.
- **tail-sway (0.5s)**: rotate -18° ↔ 18°.
- **ear-l / ear-r (4s)**: ±10° at 14%, ∓8° at 30%, 0 at 49%, ±22° at 53%, ∓10° at 58%, 0 at 63%, ±8° at 74%, 0 at 80%, ±6° at 88%, 0 by 93%.
- **arm-l / arm-r (4s)**: 0 → ±70° 18–42% → 0 at 52% → ±30° at 70% → 0 at 78% → ±25° at 86% → 0 by 93%.
- **shadow-hop (4s)**: tracks the hop (wide on crouch/landing, small and faint at the apex).
- **sparkle (4s ×4, staggered)** and **heart-up (4s ×2, delayed 2.5s/3.1s)**.

## Expression
Cat-Clawd is so happy he can't keep his feet on the ground: he scrunches down, springs up and whirls right around in the air — ears, whiskers and tail flashing to the other side — thumps down in a squashed heap with his ears flopping, and then, still grinning ^^, bounces twice more on the spot with his arms half raised, tail quivering, sparkles and little hearts popping around him.
