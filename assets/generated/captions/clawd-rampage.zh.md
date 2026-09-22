# clawd-rampage.svg

Clawd 冲动地左右横冲直撞、把东西一头撞飞的动画。4 秒循环：原地蓄力 → 向右冲刺 → 撞飞木箱 → 弹回发懵 → 转身 → 向左冲刺 → 撞飞垃圾桶 → 再转回来；被撞飞的东西会从上方掉回原位补货，无限撞下去。

## 身体结构
标准躯干 11x7 位于 (2,6)，#DE886D。全身套三层组：`charge-move`（水平 translateX 在 -2.5px 与 +2.5px 之间往返）、`run-bounce`（0.25s 迈步弹跳 translateY -0.5px）、`impact-squash`（每次撞击瞬间 scale(0.9,1.08)，以脚底 (7.5,15) 为锚点）。四条腿 1x4 位于 (3,11)/(5,11)/(9,11)/(11,11)——向上多伸进躯干 2px，保证上身前倾后倾时不脱节——分外侧对与内侧对，以 0.25s 反相空跑（translateY -1.2px），即便 Clawd 站着不动腿也在原地打滑。上半身（躯干+眼睛+手臂+怒气符号）放在 `upper-lean` 组里：蓄力时后仰 translate(∓0.8px,0.4px)，冲刺时前倾 translate(±1px,0.3px)，撞击瞬间 translate(±1.2px,0)。眼睛 1x2 位于 (4,8)/(10,8)，全程 scaleY(0.65) 眯成凶狠的瞪眼，并向冲刺方向偏移 translateX(±1.5px)（视差）；每次撞击时 scaleY(0.05) 闭眼 2.5%（"咚"），随后 scaleY(0.9) 睁大发懵一拍，再眯回去。双臂 2x2 位于 (0,9)/(13,9)，带 0.25 透明度的右下投影（+0.5,+0.5）；朝向前进方向的那只手臂经 translate(∓3px,1px) 推到身前（面朝右时右臂前置 0–38% 及 84–100%，面朝左时左臂前置 42–80%），两臂同时绕肩关节 (2,10)/(13,10) 以 0.25s 快速摆动 rotate(15°↔-10°) / rotate(-15°↔10°)。

## 道具
- **怒气符号**：4 条 L 形折线组成的 💢 十字，描边 #FF3D00 宽 0.6，位于头顶右上 (12.2,3.4)，放在 upper-lean 组内随身体移动；0.5s scale 1→1.2→1 脉动，常驻可见。
- **木箱（右侧目标）**：3x3 位于 (16,12) 贴地——深色边框 #6D4C41、浅色板面 #A1887F（内缩 2.2x2.2），加一横一竖两条木板线 #6D4C41 组成十字。绘制在 Clawd 之后（底层）。
- **垃圾桶（左侧目标）**：3x3 桶身 #90A4AE 位于 (-4,12)，两条竖向棱线 #607D8B，3.6x0.7 桶盖 #607D8B 位于 (-4.3,11.3)，1x0.5 盖柄 #455A64。绘制在 Clawd 之后（底层）。
- **撞击火花**：每侧 3 个小方块（#FFC107 0.8、#FF9800 0.7、#FFEB3B 0.6），右侧接触点约 (16,10.5–12.4)，左侧约 (-2,10.5–12.4)，世界坐标。
- **速度线**：3 条灰色 (#9E9E9E) 细条 2–2.5 x 0.5，y=7.6/9.6/11.6，身体两侧各一组（局部 x=-4.5..-2 与 17..19.5），放在 charge-move 组内跟随身体拖尾。
- **扬尘**：每侧脚后 2 个灰色 (#BDBDBD) 0.9/0.7 小方块（局部 (-1.2,13.6)/(-0.6,14.3) 与 (15.3,13.6)/(14.9,14.3)），按侧门控，只在蓄力时显示。

## 动画
- **charge-move (4s)**：0% translateX(-2.5px) → 10% -3px（后退蓄力）→ 26% +2.5px，cubic-bezier(0.75,0,1,1) 加速冲刺 → 27.5% +2.8px（过冲撞进木箱）→ 32% +1.6px（反弹）→ 46% 保持 → 52% +2.2px（后退）→ 68% -2.5px（向左冲刺）→ 69.5% -2.8px → 74% -1.6px → 88% 保持 → 100% -2.5px。
- **run-bounce (0.25s)**：translateY 0 → 25%/75% -0.5px，每步一弹。
- **impact-squash (4s)**：25% 前 scale(1) → 27.5% scale(0.9,1.08) → 31% scale(1.05,0.96) → 34% scale(1)；67–76% 镜像重复。
- **upper-lean (4s)**：0–10% translate(-0.8px,0.4px) 蓄力 → 15–26% translate(1px,0.3px) 冲刺 → 28% translate(1.2px,0) 撞击 → 34–40% (0,0) → 46–52% translate(0.8px,0.4px) 面朝左蓄力 → 57–68% translate(-1px,0.3px) → 70% translate(-1.2px,0) → 76–88% (0,0) → 94–100% translate(-0.8px,0.4px)。
- **step-outer / step-inner (0.25s)**：外侧腿 50% 抬起 translateY(-1.2px)，内侧腿反相。
- **eyes-charge (4s)**：0–25% translateX(1.5px) scaleY(0.65) → 26.5–29% scaleY(0.05) 闭眼 → 31–38% scaleY(0.9) 发懵 → 41–67% translateX(-1.5px) scaleY(0.65) → 68.5–71% 闭眼 → 73–80% scaleY(0.9) → 83–100% translateX(1.5px) scaleY(0.65)。单一时间线，无独立眨眼。
- **arm-r-turn / arm-l-turn (4s)**：右臂 0–38% 及 84–100% 前置 translate(-3px,1px)；左臂 42–80% 前置 translate(3px,1px)；其余时间在体侧。
- **arm-swing-a / arm-swing-b (0.25s)**：rotate(15°)↔(-10°) 与 rotate(-15°)↔(10°) 快速摆臂。
- **anger-pulse (0.5s)**：scale 1 → 1.2 → 1。
- **crate-fly (4s)**：25% 前静止 → 26.5% translate(0.6px,-0.8px) rotate(15°) 被顶一下 → 32% translate(2px,-4.5px) rotate(110°) → 37% translate(2.6px,-6.2px) rotate(200°) opacity 0.6 → 38.5% opacity 0 → 78% translate(0,-6px) opacity 0 → 84% 掉回原位，opacity 1。
- **can-fly (4s)**：0–36% 隐藏于 translate(0,-6px) → 42% 掉落到位 → 68% 被撞 → 68.5% translate(-0.6px,-0.8px) rotate(-15°) → 74% translate(-2px,-4.5px) rotate(-110°) → 79% translate(-2.6px,-6.2px) rotate(-200°) opacity 0.6 → 80.5% opacity 0 → 100% 回到 translate(0,-6px) 隐藏。
- **spark-r1/r2/r3 (4s)**：27–27.5% 出现 opacity 0.95/0.9，扇形飞散 translate(2,-2.5)/(3,-0.5)/(1.2,-3.5)，33–34% 消失。**spark-l1/l2/l3** 在 69–76% 镜像。
- **lines-l (4s)**：opacity 0 → 13% 0.9 → 20% translateX(-0.8px) → 26% translateX(-1.5px) opacity 0。**lines-r** 在 53–68% 镜像。
- **dust-gate-l / dust-gate-r (4s, step-end)**：左侧扬尘 0–9% 与 89–100% 可见，右侧 47–51% 可见。**puff-l / puff-r (0.4s，第二颗延迟 0.2s)**：translate(∓1.6px,-1.2px) scale 0.5→1.4，opacity 0→0.9→0。
- **shadow-charge (4s)**：地面阴影跟随 charge-move 水平移动；冲刺时 scaleX 0.9，撞击时 1.1。

## 动作表达
Clawd 眯着眼一脸凶相、头顶 💢 一跳一跳，四条腿原地打滑扬起灰尘，随即带着速度线横向弹射出去，一头撞上木箱——身体被挤扁、火花四溅、眼睛"咚"地闭上，木箱翻着跟头飞走。他弹回来发懵地眨了眨眼，猛地转身，对另一边的垃圾桶如法炮制；下一个倒霉蛋从天而降补位，他永远停不下来。
