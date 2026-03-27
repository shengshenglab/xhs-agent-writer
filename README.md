# 小红书 Agent 文案仓库

这个仓库现在只有一个定位：

把它直接交给 Claude / ChatGPT / Gemini / Cursor / Codex 这类 agent，用对话生成、迭代、保存和学习小红书文案。

放到 agent 里后就可以直接用。

## 从哪里开始

- 想让支持仓库指令的 agent 直接接管这个仓库：打开仓库根目录即可，agent 会读取 `AGENTS.md`
- 想看人类可读的简明说明：看 `AGENT.md`
- 想看完整工作流规则：看 `agent/program.md`
- 想看常用对话模板：看 `agent/workflow.md`

## 当前目录

```text
xhs-agent-writer/
├── README.md
├── AGENT.md
├── AGENTS.md
├── agent/
│   ├── system-prompt.md
│   ├── program.md
│   ├── workflow.md
│   ├── bootstrap.md
│   ├── style-profile.md
│   └── memory-bank.md
├── history/
│   └── TEMPLATE.md
├── bootstrap.md
├── style-profile.md
└── WORKFLOW.md
```

## 这个仓库能做什么

- 直接根据你的想法生成小红书文案
- 不要求你必须按模板填空，也可以自由表达
- 自动做评分、找到最低分维度、继续迭代
- 默认把推荐主标题控制在 20 字以内
- 把每轮迭代稿保存到 `history/`
- 如果你提供最终选用版或人工修改版，会把终稿写入记忆库
- 后续生成的新文案会越来越贴近你本人会发的表达

## 核心文件

- `agent/system-prompt.md`：给 agent 的一站式系统提示词
- `agent/program.md`：完整规则源，包含评分、迭代、约束检查、记忆功能
- `agent/workflow.md`：常用操作模板
- `agent/bootstrap.md`：不支持读本地文件时直接复制粘贴
- `agent/style-profile.md`：长期风格规则
- `agent/memory-bank.md`：最终选用文案 / 人工修改终稿的记忆库
- `history/TEMPLATE.md`：任务存档模板

## 最直接的用法

把整个仓库交给 agent，然后直接说：

```text
先按仓库里的规则工作，帮我写一篇小红书文案。

主题：___
目标人群：___
内容类型：___
参考调性：___
关键词：___
```

如果你不想按模板填，也可以直接说：

```text
我想写一篇介绍某个工具的小红书文案。
读者是___。
我想重点表达___。
风格希望更像___。
```
