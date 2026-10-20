# Codex，你不妨把话说得更清楚一点

*“Codex有一个好，用户提了一个需求，写得比西方记者都快。但是写出来的东西啊，都too young too simple， sometimes naive!”*

`write-like-cn-human` 是一份中文写作 skill，帮助 agent 直接表达观点，用自然、完整的中文说明谁在做什么、涉及什么对象，以及得到什么结果。适用于日常答复、解释、方案、报告和文案。

## 写作原则

### 先给结论，再提供有效依据

开头给出用户需要的结论、结果或建议，随后提供支持判断的事实和分析。每段增加有效信息，一个观点说明清楚后，就继续下一个问题。

### 清理免责声明式的防御发言

围绕用户实际关心的问题写作。判断一句限定或提醒是否有用，可以问：它改变了读者的什么理解或决定？删除它后，哪项陈述会产生实际误解？

仅用于预防想象中的批评、展示谨慎或强调自己认真核查的句子，直接删除。确实影响判断的条件，放在相关结论旁边具体说明。

### 默认正向表达

直接说明事物是什么、工作覆盖什么、准备采取什么行动。对于“不是 A，而是 B”一类句式，如果 A 只是凭空设置的对照，就直接说明 B。

软件边界条件、兼容性限制、明确排除项和纠正已有误解等情形，可以保留有实际意义的否定表达。

### 写清主体、动作和对象

把具体的人、工作和结果写进句子。用实际动作解释抽象概念，补全读者理解所需的信息。

例如，在参与者和任务已经明确的情况下，把“对齐之后，把工作给出去，再做闭环”改为：

> 你和 agent 确认任务要求后，把资料整理工作交给 agent，最后检查整理结果是否符合要求。

补充的信息来自用户材料和已有上下文。涉及事实、数字、来源、判断强度和因果关系时，保持原意。

### 使用自然、完整的中文词组

有多个同样准确的说法时，优先选择自然的双音节词，尤其是动词。例如“修改方案”“检查结果”“说明原因”。“吃苹果”“写文章”等常见搭配可以直接保留。

当完整词组更容易理解时，使用“进行业务转型”“开展需求分析”“作出决定”等表达。根据动作阶段选择措辞，例如“进行”表示过程，“完成”表示结束。

信息完整、中文自然和阅读顺畅，比单纯减少字数更重要。

## 安装到 Codex

将仓库克隆到个人技能目录：

```sh
git clone https://github.com/UbicusMyron/write-like-cn-human.git ~/.codex/skills/write-like-cn-human
```

如果使用自定义的 `CODEX_HOME`，将安装路径调整为该目录下的 `skills/write-like-cn-human`。

## 使用

在请求中调用技能：

```text
请使用 $write-like-cn-human 撰写项目说明，先给结论，再提供必要依据。
```

也可以修改现有文本：

```text
请使用 $write-like-cn-human 修改下面这段文字，保留完整信息，使用自然的中文。

[待修改的文字]
```

## 文件

- [SKILL.md](SKILL.md)：技能规则与交付检查。
- [references/examples.md](references/examples.md)：中文改写示例及适用情形。
- [agents/openai.yaml](agents/openai.yaml)：显示名称和默认调用提示。

## 设计参考

这份 skill 根据个人中文表达偏好重新编写，主要参考以下项目：

- [Stop That Shit Slop](https://github.com/lennney/stop-that-shit/blob/main/skills/stss/SKILL.md)：根据读者用途判断防御语句，正向说明工作范围。
- [Humanizer](https://github.com/blader/humanizer/blob/main/SKILL.md)：清理无意义的否定对照和重复收尾。
- [Writing Clearly and Concisely](https://github.com/softaworks/agent-toolkit/blob/main/skills/writing-clearly-and-concisely/SKILL.md)：肯定表达、具体措辞和有效信息。
- [Technical Writing Guide](https://github.com/strictdoc-project/technical_writing_skill/blob/main/SKILL.md)：结论先行，段落围绕问题展开。
- [中文去 AI 味](https://github.com/ai-zixun/humanizer-zh/blob/main/SKILL.md)：自然的中文搭配、明确的主语与动作。
