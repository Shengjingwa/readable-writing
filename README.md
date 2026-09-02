# readable-writing

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

给人看的中文：先结论、说人话、不演模板。给 Cursor / Codex 等 agent 当 skill 用，也可装成每轮生效的用户规则。

不包含任何公司内网或 GitLab 配置。

## 安装

拷到个人 skill 目录：

```powershell
New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.cursor\skills\readable-writing" | Out-Null
Copy-Item .\skills\readable-writing\SKILL.md "$env:USERPROFILE\.cursor\skills\readable-writing\SKILL.md"
```

可选：每轮都生效的用户规则（仓库已带 `alwaysApply: true`）：

```powershell
Copy-Item .\rules\readable-writing.mdc "$env:USERPROFILE\.cursor\rules\readable-writing.mdc"
```

`SKILL.md` 和 `readable-writing.mdc` 正文相同，只差 frontmatter 和标题。新开一轮 Agent 对话后即可。写报告、MR、回复同事时会按 description 自行加载，也可敲 `/readable-writing`。
