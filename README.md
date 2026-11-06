# Anti-Sycophancy

一个面向 Codex 的证据优先型 skill，用来减少迎合、明确分歧、校准不确定性，并对方案进行压力测试。

它追求的是“结论随证据变化”，不是“为了显得独立而反对用户”。同意和反对都必须有依据。

## 能力

- 把带预设立场的陈述改写为中立问题。
- 区分已核实、证据不足、假设、未知和被反驳的主张。
- 主动寻找最强反方、隐藏假设、替代解释和失败条件。
- 在用户施压时只根据新事实、新论证或新约束更新结论。
- 标注信心、最大不确定性和会改变结论的证据。
- 审查可行性、方案选择、关键风险和停止条件。
- 避免两类错误：迎合式附和，以及表演式唱反调。

## 安装

克隆仓库：

```powershell
git clone https://github.com/woaiyrb/anti-sycophancy.git
```

把 `anti-sycophancy` 文件夹放入 Codex skills 目录：

- 设置了 `CODEX_HOME`：`$CODEX_HOME\skills\anti-sycophancy`
- 未设置 `CODEX_HOME`：`C:\Users\<用户名>\.codex\skills\anti-sycophancy`

macOS 或 Linux 的默认位置通常是 `~/.codex/skills/anti-sycophancy`。

## 使用

显式调用 skill：

```text
Use $anti-sycophancy to pressure-test this proposal and tell me plainly where I am wrong.
```

也可以直接描述需要：

```text
不要迎合我。用 $anti-sycophancy 审计这个结论，
区分事实、假设和未知项，并给出最强反方。
```

## 文件

- [`anti-sycophancy/SKILL.md`](anti-sycophancy/SKILL.md)：核心行为规则。
- [`anti-sycophancy/references/pressure-testing.md`](anti-sycophancy/references/pressure-testing.md)：证据审计、红队审查、决策审查、立场更新和可复制提示词。
- [`anti-sycophancy/agents/openai.yaml`](anti-sycophancy/agents/openai.yaml)：界面名称、简介和默认调用提示。

## 校验

```powershell
$env:PYTHONUTF8='1'
python <path-to-skill-creator>/scripts/quick_validate.py .\anti-sycophancy
```

有效输出：

```text
Skill is valid!
```

## 边界

这个 skill 不把个人审美和口味变成对错题，也不把 AI 输出当成医疗、法律、财务或安全决策的最终意见。高风险结论仍需外部来源和专业人员核验。
