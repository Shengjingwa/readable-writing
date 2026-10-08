# 英文写作（STE 规则）

写英文时用这份：commit、英文 MR、英文文档、工具描述、报错信息、给别的 agent 的指令。[SKILL.md](SKILL.md) 里除「句子怎么写」以外的规则照用；「待确认：」在英文里写成 `Unverified:`。

这些规则来自 ASD-STE100 Simplified Technical English 的写法部分，不含官方词典，产出不算认证 STE。

## 规则

下表三列分别是规则名、正确写法、要避免的写法。

| 规则 | 这样写 | 别这样写 |
|---|---|---|
| 一词一义 | One word for one action, everywhere | `check`, `verify`, `confirm` for the same action |
| 主动语态 | "The agent deletes the file." | "The file is deleted." Use passive only when the actor is unknown. |
| 简单时态 | "We received the report." | "We have received the report." |
| `-ing` 只当名词 | "during processing" | "The tool is processing the queue." |
| 一句一个指令 | "Open the file. Read line 3." | "Open the file and read line 3, then check it." |
| 句子短 | Instruction ≤ 20 words; description ≤ 25 words | Stacked subordinate clauses |
| 一段一个话题 | ≤ 6 sentences per paragraph | One paragraph for three topics |
| 名词堆叠 ≤ 3 | "fuel pump valve" | "high pressure fuel pump inlet valve assembly" |
| 不省词 | Keep the subject, verb, and article | "Files not backed up will be lost." (Which files?) |
| 警告在前 | "Warning: a timeout can produce a partial artifact." | A condition buried mid-sentence |
| 3 项以上用列表 | A numbered list for 3 or more steps or conditions | A sequence buried in prose |
| 常用词 | use, start, before, help, enough, validate the file | utilize, initiate, prior to, facilitate, sufficient, perform validation of the file |
| 术语 | Keep a necessary technical term. Define it once. | Undefined jargon |

## 计数和例外

- 代码标识符、数字连单位，各算 1 个词。
- 两个相关的短句可以用 "and" 或 "if" 连起来，前提是每半句仍只有一个指令或判断。读着顺比死守规则更要紧。
- Commit 标题用祈使句，例如 `fix: retry order sync on 502`。

## 例子

> Before: Once the upstream job has completed and assuming no errors were raised, the downstream agent should proceed to consume the output artifact, though it is worth noting that partial artifacts are sometimes produced under timeout conditions.
>
> After: Wait until the upstream job finishes with no errors. Then read the output artifact. Warning: a timeout can produce a partial artifact. Make sure that the artifact is complete before you use it.
