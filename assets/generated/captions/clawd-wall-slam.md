# clawd-wall-slam.svg

Impatience level 3 ("berserk"): Clawd rams a brick wall three times, faster each time — the wall cracks, cracks more, then its middle bricks burst out — and he is knocked back seeing stars, shakes it off, and revs up again while the wall quietly heals. 4s loop.

## Body
Standard torso 11x7 at (2,6), #DE886D, four 1x4 legs at (3,11)/(5,11)/(9,11)/(11,11) scrambling out of phase at 0.2s (translateY -1.2px). Groups: `charge-move` (translateX between -4.9px and +3.5px: three accelerating dashes with cubic-bezier(0.75,0,1,1), ease-out overshoots at the hits, a hard knock-back to -4.8px after hit 3, and a 0.1s left-right head shake at 84–88%), `run-bounce` (0.2s translateY -0.5px), `impact-squash` (scale(0.9,1.08) on hits 1 and 2, scale(0.9,1.1) → (1.08,0.94) on hit 3, origin at the feet), `upper-lean` (lean back translate(-0.8px,0.4px) while revving, (1px,0.3px) into each dash, (1.2px,0) at impact, a wobble during the shake-off). Two eye sets on one timeline: angry 1x2 rectangles at (4,8)/(10,8) with scaleY(0.6) squint and translateX(1.5px) toward the wall, snapping shut scaleY(0.05) at each hit, hidden from 55.5% to 82.5%; dizzy "x" eyes (two crossed polylines per eye, stroke 0.7) shown in that window; the angry eyes come back wide (scaleY 1) at 84% and squint again by 90%. Left arm 2x2 at (0,9) swings rotate(18°↔-12°) at 0.2s; the right arm is fixed in front of the body via a static translate(-3,1) wrapper and swings rotate(-12°↔10°); both have 0.25-opacity drop shadows.

## Props
- **Brick wall**: x 17..20, y 0..15, drawn first. Solid parts (17,0,3x7) and (17,12,3x3) fill #A0522D with mortar lines #D7CCC8 (horizontal every 1.5, staggered vertical joints). The middle zone y 7..12 is four loose bricks (3x1.25, 3x1.25, 3x1.25, 3x0.5) each with its own joint line, which fly out on hit 3 leaving a hole. The whole wall sits in a `wall-shake` group.
- **Cracks**: three dark zig-zag polylines (stroke #3E2723 width 0.35) across the impact zone — one appears after hit 1, two more after hit 2, all gone at 92%.
- **Anger marks**: two 💢 (stroke #FF3D00 width 0.6) at (12.2,3.4) and (0.8,3.4), pulsing scale 1→1.25 at 0.4s, inside a `rage-gate` group hidden 55–84%.
- **Head steam**: three gray-blue (#B0BEC5) rounded 0.9–1.1 squares rising 4px from the top of the head (x 5.4–9.5, y 4.4), 0.7s, staggered 0/0.25/0.5s, scale 0.5→1.4, opacity 0→0.9→0; in the same rage-gate.
- **Dizzy stars**: three yellow (#FFD54F) 1.1 diamonds on a flattened orbit (outer static translate(7.5,3.6) scale(1,0.4), inner group rotating 360° per 0.8s, radius ~4.15), gated 56–82%.
- **Impact sparks**: two squares per hit (#FFC107 0.7 / #FF9800 0.6) at the wall face (~16.3, 8.2 / 10.6) for hits 1 and 2, four bigger ones (0.7–0.9, #FFC107 / #FF9800 / #FFEB3B) for hit 3, all fanning left.
- **Speed lines**: three gray (#9E9E9E) bars behind the body (local x -4.5..-2) on each dash.
- **Dust puffs**: two gray (#BDBDBD) squares behind the feet, 0.35s, gated to the rev windows.

## Animation
- **charge-move (4s)**: 0% -4 → 8% -4.5 → 18% 3 (hit 1) → 19.5% 3.3 → 22% 0 → 26% -0.5 → 34% 3 (hit 2) → 35.5% 3.3 → 38% 0.5 → 41% 0 → 48% 3 (hit 3) → 49.5% 3.5 → 54% -4.8 → 56% -4.3 → 58–82% -4.5 → 84% -4.1 → 86% -4.9 → 88% -4.2 → 90% -4.5 → 100% -4.
- **impact-squash (4s)**: 19.5% / 35.5% scale(0.9,1.08) → recover by 25% / 41%; 49.5% scale(0.9,1.1) → 53% scale(1.08,0.94) → 56% normal.
- **upper-lean (4s)**: rev 0–8%, dash 12–18%, impact 20%, rev 23–26%, dash 29–34%, impact 36%, rev 39–41%, dash 44–48%, impact 50%, thrown back translate(-1px,0) at 54%, slumped (0,0.3px) 56–82%, shake 84/86/88%, rev 90–100%.
- **eyes-angry (4s)**: squint 0–18% → shut 18.5–21% → squint 23–34% → shut 34.5–37% → squint 39–48% → shut 48.5–55% → opacity 0 55.5–82% → wide open 84% → squint 90–100%. **eyes-dizzy (4s, step-end)**: opacity 1 from 55.5% to 82.5%.
- **rage-gate (4s, step-end)**: opacity 0 from 55% to 84%. **stars-gate**: opacity 1 from 56% to 82%. **stars-orbit (0.8s, linear)**: rotate 0→360°.
- **anger-pulse (0.4s)**, **steam-rise (0.7s ×3 staggered)**, **step-outer / step-inner (0.2s)**, **arm-swing-a / arm-swing-b (0.2s)**, **run-bounce (0.2s)**.
- **wall-shake (4s)**: translateX 0.4 → -0.2 → 0 at hit 1 (18.7–21.5%), 0.6 → -0.3 → 0 at hit 2 (34.7–37.5%), 1 → -0.5 → 0.2 → 0 at hit 3 (48.7–53%).
- **crack-1 / crack-2 (4s, step-end)**: appear at 18.5% / 34.5%, disappear at 92%.
- **brick-a/b/c/d (4s)**: from 48% fly translate up to (3.3,0) / (3.5,2.5) / (3,3.6) / (2.6,-2.4) with rotate ±60–150°, opacity 0.6 at 59% and 0 at 60.5%; fade back into place (opacity 0→1) between 92% and 98%.
- **spark-1a/1b, 2a/2b, 3a–3d (4s)**: bursts at 18–24.5%, 34–40.5%, 48–56.5%.
- **lines-l (4s)**: 9–18%, 27–34%, 42–48%. **dust-gate (4s, step-end)**: 0–7%, 23–25%, 39–40%, 91–100%. **puff (0.35s)**.
- **shadow-slam (4s)**: follows charge-move; scaleX 0.9 on dashes, 1.1 on the knock-back.

## Expression
Steam pouring off his head and a 💢 throbbing on each side, Clawd scrambles in place and hurls himself at the brick wall — thud, a crack; back up, harder — thud, more cracks; back up, harder still — BANG, the middle of the wall blows out in flying bricks and he is thrown back on his heels with x-ed eyes and stars circling his head. He wobbles, shakes his head clear, the fury comes right back, and while he's revving up the bricks quietly settle back into a whole wall for round two.
