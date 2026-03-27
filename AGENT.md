# Agent 版

这个仓库现在就是专门给 agent 用的。

把整个仓库放到 agent 里后，就可以直接开始写、迭代、保存、学习小红书文案。

## 最小使用方式

把下面这些文件交给 agent：

- `agent/system-prompt.md`
- `agent/style-profile.md`

如果你希望 agent 越写越像你，再额外给它：

- `agent/memory-bank.md`

然后你可以二选一：

### 方式 A：按字段输入

```text
主题：___
目标人群：___
内容类型：___
参考调性：___
关键词：___
```

### 方式 B：直接说你想表达什么

```text
我想写一篇介绍这个仓库的小红书文案。
读者是爱发小红书、想借助 AI 提高文案质量的人。
想要有点种草感、科技感，最好更像爆款口吻。
摘要也想写得更让人点进去。
```

agent 会自动补全缺失信息；只有在关键信息真的不足时才追问。

## 推荐文件组合

### 最轻量
- `agent/system-prompt.md`
- `agent/style-profile.md`

### 更完整
- `agent/program.md`
- `agent/style-profile.md`
- `agent/memory-bank.md`
- `agent/workflow.md`

### 不支持读文件
- 直接复制 `agent/bootstrap.md`
- 把 `agent/style-profile.md` 的内容粘进风格档案区域
- 如果已有记忆样本，也把 `agent/memory-bank.md` 的内容一起粘给 agent

## 文件说明

- `agent/system-prompt.md`：一站式 prompt，适合直接开聊
- `agent/program.md`：完整规则源，包含评分、迭代、约束检查、风格学习规则
- `agent/bootstrap.md`：给网页端或不方便上传文件的场景
- `agent/workflow.md`：常用操作模板
- `agent/style-profile.md`：抽象出来的长期风格规则
- `agent/memory-bank.md`：保存用户最终选用或人工修改终稿的记忆库

## 现在默认支持的规则

- 用户不一定要按模板填空，也可以自由表达需求
- 默认输出标题、摘要、正文、标签
- 其中摘要默认是一句更想让人点进去的话，不是普通摘要
- 推荐主标题默认控制在 20 字以内
- 每次新增要求都要继续纳入评分和后续迭代
- 如果 agent 能写文件，会把每轮迭代稿保存到 `history/` 里，方便回看改动
- 如果用户提供最终选用文案或人工修改版，会自动保存，并写入记忆库
- 后续生成会优先参考这些终稿，让表达更像用户本人

## 典型工作流

1. 给 agent `agent/system-prompt.md`
2. 如果有历史风格，再给 `agent/style-profile.md`
3. 如果有历史终稿记忆，再给 `agent/memory-bank.md`
4. 直接输入字段，或者直接说你想表达什么
5. agent 自动执行：生成 -> 自评 -> 找最低分 -> 迭代 -> 定稿
6. 如果 agent 能写文件，会把每轮稿子存到 `history/任务目录/`
7. 如果你后面贴出“我最终发的是这个版本”，agent 会保存终稿并更新记忆
8. 之后新文案会更偏向你最终会采用的表达方式

## 当前定位

- 这是一个纯 agent 仓库
- 直接放到 agent 里就可以使用

## 适用场景

- Claude Code
- ChatGPT / Gemini 上传文件
- Cursor
- 其他支持 prompt 文件的 agent
