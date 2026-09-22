# Catclawd Body Structure Reference (cat-form Clawd)

The cat form keeps Clawd's body, colors and proportions exactly (torso 11x7 at (2,6) #DE886D, eyes 1x2 at (4,8)/(10,8) #000000, arms 2x2 at (0,9)/(13,9), four 1x2 legs at (3,13)/(5,13)/(9,13)/(11,13), ground shadow (3,15) 9x1) and adds cat markers in the same palette plus pink #F8BBD0 / #F48FB1 accents. Sticker names use the `catclawd-` prefix.

## Added parts

| Part | Rects | Notes |
|------|-------|-------|
| left ear | (2,5) 2.5x1, (2,4) 1.5x1, (2,3.2) 0.7x0.8, body color; inner ear (2.4,4.6) 0.7x0.8 #F8BBD0 | stair-step triangle on the top-left corner; rotate about its base (3.2,6) |
| right ear | (10.5,5) 2.5x1, (11.5,4) 1.5x1, (12.3,3.2) 0.7x0.8; inner ear (11.9,4.6) | mirror of the left; rotate about (11.8,6) |
| tail | (13,11.6) 1.3x1.2, (14,10.6) 1.2x1.4, (14.6,9.2) 1.1x1.7, (14.5,7.8) 1.1x1.6, (13.9,6.8) 1.2x1.2, body color | curls up from the lower right of the torso, drawn behind the body; sway/rotate about its root (13.6,12.2) |
| whiskers | two 0.3-wide black lines per side: (2,8.2)→(-0.6,7.7), (2,8.9)→(-0.6,9); mirrored from x=13 to 15.6 | sit at eye height, above the arms |
| nose | (7.2,10.3) 0.6x0.45 #F8BBD0 | not a mouth — the no-mouth rule still applies |
| cheeks | (3,10.4) and (10.7,10.4) 1.3x0.6 #F8BBD0 opacity 0.9 | on by default in the cat form |

## Render order
shadow → tail → legs → torso → cheeks + nose → whiskers → eyes → ears → arms → effects.

## Expression channels
- Eyes carry the main emotion (happy ^^ polylines, normal 1x2 bars, wide 1.4x2, `><`, teary).
- Ears and tail are secondary animation: give every main action a small ear reaction (rotate ±10–25° about the ear base) and a tail reaction (sway ±18–25° at 0.4–0.6s, or a single flick).
- A "spin" is a horizontal flip of the whole cat group: scaleX 1 → -1 → 1 about (7.5,15); ears, tail and whiskers visibly swap sides.

## Size
All markers stay within x -0.6..15.7 and y 3.2..15, so the crop window stays near the 20-unit minimum and the cat fills the frame.
