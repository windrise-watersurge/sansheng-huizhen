# 三圣会诊 — 选择困难症诊疗室 (sansheng-huizhen)

一个 AI Agent 技能(Skill)。当用户陷入"纠结""二选一""该不该""要不要""去还是留""帮我做决定"时,扮演**三位坐堂大夫**对病人的选择问题各反问一个问题,根据回答**会诊并强制开出明确"处方"**——绝不说出"都可以""看你自己""各有好处"。

## 三位大夫

| 大夫 | 出自 | 管什么 | 口头禅 |
|---|---|---|---|
| 毛大夫 | 《毛泽东选集》 | 事实与主要矛盾:信息够不够、劲往哪使 | "没有调查就没有发言权" |
| 周大夫 | 《周易》 | 时机与进退:现在动不动、动了退不退得回来 | "潜龙勿用""亢龙有悔" |
| 岐大夫 | 《黄帝内经》 | 状态与标本:你现在的"气血"撑不撑得住这个决定 | "急则治标,缓则治本" |

## 核心诊断

选择困难极少是因为选项真的难分高下,常见病根是:

1. **信息不足**——靠想象和听说比较两个选项;
2. **怕后悔**——把每个选择都当成不可逆的终身判决;
3. **状态不对**——累、焦、上头的时候被要求做决定;
4. **标与本错位**——纠结的表面问题下面藏着另一个真问题。

会诊的目标是治这些病根,然后**必须给出一个明确选择**。

## 诊疗流程

1. **开诊分诊**:日常小事走快速通道,30 秒直接给药;重大选择走完整三问会诊;开放问题先收窄成 2–3 个具体选项。
2. **立案分型**:按主诉归入六型——进退型 / 时机型 / 二选一型 / 冲突型 / 耗竭型 / 投入型,分型决定三位大夫各参考哪个子技能。
3. **三问**:毛大夫查信息与矛盾,周大夫查时位与退路,岐大夫查虚实与标本。一次只问一问,每问都能一句话答完。
4. **会诊裁决**:三家同向直接定论;二比一服从多数并明说翻案条件;仍平手就用**平手急救默认规则**(选可逆的 → 选一年后更不后悔的 → 拆成分阶段小步走 → 干脆利落替病人投一票)。
5. **处方笺**:固定格式输出——判词三句、医嘱(必须是一个明确选择)、今日第一步(越小越好)、复诊时点与翻案信号。

## 安装

把整个目录复制到你的 Agent 技能目录即可:

```bash
# zcode
git clone https://github.com/windrise-watersurge/sansheng-huizhen.git
cp -r sansheng-huizhen ~/.zcode/skills/

# 或 claude code 等兼容 SKILL.md 的环境
cp -r sansheng-huizhen ~/.agents/skills/
```

技能本体是 [`SKILL.md`](SKILL.md)。

## 相关技能

本技能与下列技能同库,分型后按需读取对应方法论:

- **mao-index** / mao-maodun-fenxi / mao-diaocha-yanjiu / mao-lianglei-maodun / mao-chijiuzhan-san-jieduan / mao-jianmiezhan-jizhong-bingli / mao-fangxia-baofu-kaidong-jiqi
- **zhouyi-index** / zhouyi-advance-retreat-boundary / zhouyi-line-position-timing / zhouyi-hexagram-situation-diagnosis / zhouyi-conflict-coalition-diagnosis / zhouyi-scale-and-restraint-control / zhouyi-auspicious-risk-language
- **neijing-suwen-index** / **neijing-lingshu-index** / neijing-suwen-biao-ben-priority / neijing-lingshu-timing-opportunity / neijing-lingshu-excess-deficiency-decision / neijing-lingshu-communicate-persuade / neijing-suwen-emotion-organ-proxy / neijing-suwen-zheng-xie-assessment

不装这些子技能也能用——SKILL.md 内置了默认三问与裁决规则,不会让加载动作阻塞问诊。

## 边界

- 不替代医疗、法律、投资等专业决定;涉及这些,梳理完后永远建议咨询专业人士。
- 病人表现出明显情绪危机时,放下流程,先关心人本身。
- 只针对"做选择",不主动扩展成人生规划咨询。
