# readable-writing

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

写给同事看的中文：开头先说现在怎样，把做过的事和结果写清楚，少用套话。

仓库里有两份文件，**正文相同**，只差开头那几行配置和标题：

| 文件 | 装到哪里 | 什么时候用 |
| --- | --- | --- |
| `skills/readable-writing/SKILL.md` | Cursor 的 skill | 写报告、MR、回复时会按描述自行加载，也可以敲 `/readable-writing` |
| `rules/readable-writing.mdc` | Cursor 的用户规则 | 每轮对话都会用 |

没有公司内网或 GitLab 配置。

## 安装

在仓库根目录执行。装完后**新开一轮对话**才会生效。

### 1. 装 skill（必做）

```powershell
npx skills add Shengjingwa/readable-writing
```

也可以手拷：

```powershell
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.cursor\skills\readable-writing" | Out-Null
Copy-Item .\skills\readable-writing\SKILL.md "$env:USERPROFILE\.cursor\skills\readable-writing\SKILL.md"
```

### 2. 装用户规则（可选）

希望每次说话都按这份规范写，再拷这一份：

```powershell
Copy-Item .\rules\readable-writing.mdc "$env:USERPROFILE\.cursor\rules\readable-writing.mdc"
```
