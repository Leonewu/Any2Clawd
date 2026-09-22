# clawd-rampage.svg

An impulsive rampage animation of Clawd charging left and right and headbutting things off the frame. 4s loop: rev up → dash right → smash a wooden crate → bounce back dazed → turn → dash left → smash a trash can → turn back; the knocked-away objects drop back in from above so the rampage never ends.

## Body
Standard torso 11x7 at (2,6), #DE886D. The whole body is wrapped in three groups: `charge-move` (horizontal translateX between -2.5px and +2.5px), `run-bounce` (0.25s step bounce, translateY -0.5px) and `impact-squash` (scale(0.9,1.08) at the instant of each hit, anchored at the feet (7.5,15)). The four legs are 1x4 at (3,11)/(5,11)/(9,11)/(11,11) — 2px overlap into the torso so the upper-body lean never disconnects them — split into an outer pair and an inner pair that scramble out of phase at 0.25s (translateY -1.2px), running in place even while Clawd stands still. The upper body (torso + eyes + arms + anger mark) sits in an `upper-lean` group: translate(∓0.8px, 0.4px) leaning back while revving, translate(±1px, 0.3px) leaning forward while dashing, translate(±1.2px, 0) at impact. The eyes are 1x2 at (4,8)/(10,8), permanently squinted scaleY(0.65) in an angry glare, shifted translateX(±1.5px) toward the charge direction (parallax), snapping shut scaleY(0.05) for 2.5% at each impact ("bonk"), then opening wide scaleY(0.9) for a dazed beat before squinting again. Both arms 2x2 at (0,9)/(13,9) with a 0.25-opacity drop shadow (+0.5,+0.5); the leading arm is pushed in front of the body via translate(∓3px, 1px) (right arm while facing right 0–38% and 84–100%, left arm while facing left 42–80%), and both arms swing rotate(15°↔-10°) / rotate(-15°↔10°) at 0.25s about the shoulder joints (2,10)/(13,10).

## Props
- **Anger mark**: 4 L-shaped polylines forming a 💢 cross, stroke #FF3D00 width 0.6, at (12.2,3.4) above the top-right of the head, inside the upper-lean group so it follows the body; pulses scale 1→1.2→1 at 0.5s and is always visible.
- **Wooden crate (right target)**: 3x3 at (16,12) resting on the ground — dark frame #6D4C41, lighter face #A1887F (2.2x2.2 inset), plus a horizontal and a vertical plank line #6D4C41 forming a cross. Drawn behind Clawd.
- **Trash can (left target)**: 3x3 body #90A4AE at (-4,12) with two vertical ridge lines #607D8B, a 3.6x0.7 lid #607D8B at (-4.3,11.3) and a 1x0.5 lid handle #455A64. Drawn behind Clawd.
- **Impact sparks**: 3 small squares per side (#FFC107 0.8, #FF9800 0.7, #FFEB3B 0.6) at the right contact point (~16,10.5–12.4) and the left contact point (~-2,10.5–12.4), in world space.
- **Speed lines**: 3 gray (#9E9E9E) thin bars 2–2.5 x 0.5 at y=7.6/9.6/11.6, one set behind each side of the body (local x=-4.5..-2, and 17..19.5), inside the charge-move group so they trail the body.
- **Dust puffs**: 2 gray (#BDBDBD) 0.9/0.7 squares behind the feet on each side (local (-1.2,13.6)/(-0.6,14.3) and (15.3,13.6)/(14.9,14.3)), gated per side so they only show while revving.

## Animation
- **charge-move (4s)**: 0% translateX(-2.5px) → 10% -3px (backs up to rev) → 26% +2.5px with cubic-bezier(0.75,0,1,1) acceleration (dash right) → 27.5% +2.8px (overshoot into the crate) → 32% +1.6px (recoil) → 46% hold → 52% +2.2px (back up) → 68% -2.5px (dash left) → 69.5% -2.8px → 74% -1.6px → 88% hold → 100% -2.5px.
- **run-bounce (0.25s)**: translateY 0 → -0.5px at 25%/75%, one bounce per step.
- **impact-squash (4s)**: scale(1) until 25% → 27.5% scale(0.9,1.08) → 31% scale(1.05,0.96) → 34% scale(1); mirrored at 67–76%.
- **upper-lean (4s)**: 0–10% translate(-0.8px,0.4px) rev → 15–26% translate(1px,0.3px) charge → 28% translate(1.2px,0) impact → 34–40% (0,0) → 46–52% translate(0.8px,0.4px) rev facing left → 57–68% translate(-1px,0.3px) → 70% translate(-1.2px,0) → 76–88% (0,0) → 94–100% translate(-0.8px,0.4px).
- **step-outer / step-inner (0.25s)**: outer legs lift translateY(-1.2px) at 50%, inner legs out of phase.
- **eyes-charge (4s)**: 0–25% translateX(1.5px) scaleY(0.65) → 26.5–29% scaleY(0.05) shut → 31–38% scaleY(0.9) dazed → 41–67% translateX(-1.5px) scaleY(0.65) → 68.5–71% shut → 73–80% scaleY(0.9) → 83–100% translateX(1.5px) scaleY(0.65). Single timeline, no separate blink.
- **arm-r-turn / arm-l-turn (4s)**: right arm translate(-3px,1px) forward 0–38% and 84–100%; left arm translate(3px,1px) forward 42–80%; otherwise at the side.
- **arm-swing-a / arm-swing-b (0.25s)**: rotate(15°)↔(-10°) and rotate(-15°)↔(10°) fast swing.
- **anger-pulse (0.5s)**: scale 1 → 1.2 → 1.
- **crate-fly (4s)**: rest until 25% → 26.5% translate(0.6px,-0.8px) rotate(15°) nudge → 32% translate(2px,-4.5px) rotate(110°) → 37% translate(2.6px,-6.2px) rotate(200°) opacity 0.6 → 38.5% opacity 0 → 78% translate(0,-6px) opacity 0 → 84% drops back to rest, opacity 1.
- **can-fly (4s)**: 0–36% hidden at translate(0,-6px) → 42% drops in to rest → hit at 68% → 68.5% nudge translate(-0.6px,-0.8px) rotate(-15°) → 74% translate(-2px,-4.5px) rotate(-110°) → 79% translate(-2.6px,-6.2px) rotate(-200°) opacity 0.6 → 80.5% opacity 0 → 100% back at translate(0,-6px) hidden.
- **spark-r1/r2/r3 (4s)**: appear at 27–27.5% opacity 0.95/0.9, fan out translate(2,-2.5)/(3,-0.5)/(1.2,-3.5) and vanish by 33–34%. **spark-l1/l2/l3** mirrored at 69–76%.
- **lines-l (4s)**: opacity 0 → 0.9 at 13% → translateX(-0.8px) at 20% → translateX(-1.5px) opacity 0 at 26%. **lines-r** mirrored at 53–68%.
- **dust-gate-l / dust-gate-r (4s, step-end)**: left puffs visible 0–9% and 89–100%, right puffs visible 47–51%. **puff-l / puff-r (0.4s, second puff delayed 0.2s)**: translate(∓1.6px,-1.2px) scale 0.5→1.4, opacity 0→0.9→0.
- **shadow-charge (4s)**: ground shadow follows charge-move horizontally; scaleX 0.9 while dashing, 1.1 at impact.

## Expression
Clawd, eyes narrowed into an angry glare with a 💢 pulsing over his head, scrambles his legs in place kicking up dust, then rockets sideways with speed lines trailing and headbutts a wooden crate — his body squashes, sparks burst, his eyes snap shut, and the crate tumbles away spinning. He bounces back, blinks dazed for a moment, whips around, and does exactly the same thing to a trash can on the other side; the next victims drop in from above and he never stops.
