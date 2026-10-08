# readable-writing

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

写给同事看的中文：开头先说现在怎样，把做过的事和结果写清楚，少用套话。也支持按 STE（简化技术英语）写英文。

这是一个 Cursor skill。写报告、MR / PR 描述、回复时，agent 会按描述自行加载；也可以敲 `/readable-writing` 手动调用。没有公司内网或 GitLab 配置。

`skills/readable-writing/` 里有 5 个文件。agent 先读 `SKILL.md`，其余 4 个按任务再读：

| 文件 | 什么时候读 |
| --- | --- |
| `SKILL.md` | 每次加载都读：底线、先把事说清楚、句子怎么写 |
| `GENRES.md` | 从头写时，查对应文体（报告、MR / PR 描述、回复、纪要、故障通报、讲解）的内容顺序 |
| `REWRITE.md` | 改写别人给的文字时 |
| `ENGLISH.md` | 写英文时，替换句子规则 |
| `CHECKLIST.md` | 交出去之前逐条自检 |

## 安装

在仓库根目录执行。装完后**新开一轮对话**才会生效。

```powershell
npx skills add Shengjingwa/readable-writing
```

也可以手拷整个目录：

```powershell
Copy-Item .\skills\readable-writing "$env:USERPROFILE\.cursor\skills\" -Recurse -Force
```
