# my-first-repo

这是我使用 Git 和 GitHub 创建的第一个仓库 🎉

## 这个仓库做了什么

- [x] 配置 Git 身份（user.name / user.email）
- [x] 在 GitHub 上创建远程仓库
- [x] `git clone` 克隆到本地
- [x] `git add` 暂存文件
- [x] `git commit` 提交到本地仓库
- [x] `git push` 推送到 GitHub

## 常用 Git 命令速查

| 命令 | 作用 |
| --- | --- |
| `git clone <url>` | 克隆远程仓库到本地 |
| `git status` | 查看工作区状态 |
| `git add <file>` | 把文件加入暂存区 |
| `git commit -m "说明"` | 提交暂存区的改动 |
| `git push origin main` | 推送到远程 main 分支 |
| `git log --oneline` | 查看提交历史 |

---

## 📚 AI 概念学习资料（AI 作业）

本仓库还包含一份 AI 概念学习作业，用三份精美的交互式 HTML 页面讲解三个核心 AI 概念，并配套一份关系说明文档。

### 学习资料文件

| 文件 | 主题 |
| --- | --- |
| `learning-materials/agent.html` | Agent（智能体）—— 感知 / 思考 / 行动 / 循环 |
| `learning-materials/llm-context.html` | 大模型的上下文 —— 系统提示、对话历史、工具结果、检索片段 |
| `learning-materials/skill.html` | Skill（技能）—— 把任务打包成可复用的指令+工具集合 |
| `concept-relationship.md` | 三者如何相互配合、协同工作（关系说明） |

### 三句话总结

- **Agent** = 决策者，决定"下一步做什么"
- **Context** = 记忆载体，模型能看到的所有信息
- **Skill** = 执行手册，让 Agent 能真正动手完成任务

三者协同关系：**Agent 做决策 + Context 做记忆 + Skill 做执行 = 一个能自主完成复杂任务的 AI 系统。**

> 详细解释见 [`concept-relationship.md`](./concept-relationship.md)。
