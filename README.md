# 统计学-Python · 个人学习仓库

> 课程：**统计学-Python** ｜ 姓名：**马元元** ｜ 学号：P251012217 ｜ GitHub：yuan-626 ｜ 仓库公开可访问

![课程](https://img.shields.io/badge/课程-统计学Python-4f46e5)

![Python](https://img.shields.io/badge/Python-3.12.x-3776ab?logo=python\&logoColor=white)

![Git](https://img.shields.io/badge/Git-已配置-f05032?logo=git\&logoColor=white)

![公开](https://img.shields.io/badge/仓库-公开可访问-10b981)

![更新](https://img.shields.io/badge/最后更新-2026--09--06-orange)

> 🗂 **[仓库文件索引页（可视化浏览）](./index.html)** —— 目录树 + 全部文件卡片 + 实时搜索，比纯文字列表更直观

## 📑 目录

| 章节                               | 内容                       |
| -------------------------------- | ------------------------ |
| [一、仓库用途](#一仓库用途)                 | 本仓库是做什么的                 |
| [二、目录结构](#二目录结构)                 | 完整文件树                    |
| [三、项目级 Skill](#三项目级-skill)       | 概念学习资料生成 Skill           |
| [四、已生成的学习资料](#四已生成的学习资料)         | Agent / 上下文 / Skill 三份资料 |
| [五、AI 使用与人工核查记录](#五ai-使用与人工核查记录) | AI 分工与人工确认               |
| [六、资料来源规范](#六资料来源规范)             | 12 条已验证一手来源              |
| [七、安全与隐私](#七安全与隐私)               | .gitignore 与凭据处理         |
| [八、课程章节目录](#八课程章节目录)             | 01–04 章节范围               |
| [九、环境准备](#九环境准备)                 | venv + 依赖安装              |
| [十、常用命令](#十常用命令)                 | Git 速查                   |
| [十一、作业提交信息](#十一作业提交信息)           | 姓名 / 学号 / 链接             |

---

## 一、仓库用途

本仓库用于存放课程的作业与个人学习资料，同时作为后续课程项目的工具基础。

目前包含两部分：

1. **AI 概念作业**：一个可复用的概念学习资料生成 Skill，以及由它生成的三份概念学习资料（Agent / 上下文 / Skill）
2. **课程章节目录**：按课程主题划分的作业存放区，供后续作业使用

---

## 二、目录结构

```
my-first-repo/
├── .workbuddy/
│   └── skills/
│       └── concept-learning-material/
│           └── SKILL.md          ← 项目级 Skill（AI 作业核心产出）
├── learning-materials/
│   ├── agent.html                ← 概念一：Agent
│   ├── llm-context.html          ← 概念二：大模型的上下文
│   ├── skill.html                ← 概念三：Skill
│   ├── concept-relationship.md   ← 概念关系说明（Markdown 版，含 Mermaid 图）
│   └── concept-relationship.html ← 概念关系说明（网页版，含 SVG 关系图）
├── 01-统计学基础/
├── 02-Python 数据处理/
├── 03-统计建模/
├── 04-综合项目/
├── notebooks/
├── docs/
├── README.md                     ← 仓库主文档
├── index.html                    ← 仓库文件索引页（可视化浏览）
├── concept-relationship.md       ← 关系说明的旧路径（向后兼容）
├── requirements.txt
└── .gitignore
```

两份 `concept-relationship` 内容一致：`.md` 版便于在 GitHub 上直接阅读和复用 Mermaid 源码，`.html` 版为自包含网页，含内嵌 SVG 关系图，可直接在浏览器打开。仓库根目录的 `concept-relationship.md` 保留为向后兼容入口。

根目录的 `index.html` 为**仓库文件索引页**：以目录树 + 文件卡片可视化展示本仓库全部文件（含大小、行数、用途说明），支持实时搜索，点击卡片直接跳转对应文件。纯静态、不依赖任何外部 CDN，下载后双击即可在浏览器打开。

---

## 三、项目级 Skill

### 存放路径

```
.workbuddy/skills/concept-learning-material/SKILL.md
```

这是**项目级 Skill**（随仓库走），与用户级 Skill（放在用户目录、跨项目生效）相区分。任何人在本项目内打开 WorkBuddy 工作区，即可直接使用这个 Skill。

### 它做什么

给定一个概念名称，生成一份结构完整的个人学习资料（单文件 HTML），包含：

- 学习目标
- 用自己的话重述的一句话理解
- 核心机制与组成
- 一个能落地讲出来的具体应用场景
- 容易混淆的问题与使用边界（至少 3 条，写明失效条件）
- 检验理解而非记忆的自测问题
- **可核查的资料来源**（每条均标注实测访问状态）
- 核查记录（说明生成方式、来源验证方式、待人工复核项）

### 关键设计：它不绑定具体概念

三个已生成的概念（Agent、上下文、Skill）只是三次调用的结果，不是 Skill 本身的内容。SKILL.md 里没有任何针对这三个概念的硬编码。传入任意新概念，流程与标准完全一致。

### 如何在 WorkBuddy 中调用

1. 用 WorkBuddy 打开本仓库文件夹作为工作区
2. 项目级 Skill 会被自动识别（无需额外安装或配置）
3. 在对话中直接说出概念名称即可，例如：

```
用 concept-learning-material 学习"主成分分析"
```

```
用 concept-learning-material 生成"蒙特卡洛模拟"的学习资料，
我已有概率论基础，重点是和解析法的区别
```

1. 生成的资料默认输出到 `learning-materials/<概念英文 slug>.html`

### Skill 内部的硬性约束

SKILL.md 中写明了两条不可跳过的规则，用来保证产出质量：

- **来源不得伪造**：每一条准备引用的链接必须实际发起请求验证，非 200 一律剔除，不得凭记忆填写
- **解释不得照搬**：读完来源后先合上资料，用自己的话重述，禁止复制原文段落

此外还有一份 9 条的自检清单，全部通过才算完成。

---

## 四、已生成的学习资料

| 资料                                                                          | 概念      | 说明                                        |
| --------------------------------------------------------------------------- | ------- | ----------------------------------------- |
| [agent.html](./learning-materials/agent.html)                               | Agent   | 以"决策权在代码里还是在模型里"作为 Workflow 与 Agent 的分界判据 |
| [llm-context.html](./learning-materials/llm-context.html)                   | 大模型的上下文 | 把上下文理解为"一次性的有限工作台面"，区分溢出与腐烂               |
| [skill.html](./learning-materials/skill.html)                               | Skill   | 渐进式披露三层结构，及其与提示词、MCP 的分工                  |
| [concept-relationship.md](./learning-materials/concept-relationship.md)     | 三者关系    | 供给链视角：资源—消费者—供给物，含个人判断                    |
| [concept-relationship.html](./learning-materials/concept-relationship.html) | 三者关系    | 与 .md 版内容一致，自包含网页版                        |

每份资料均包含：一句话理解、学习目标、核心机制、具体应用场景、易混淆点与边界、自测题、可核查来源、核查记录。

---

## 五、AI 使用与人工核查记录

> 本节如实记录 AI 参与了哪些工作、我做了哪些核查，以及尚未完成的部分。

### AI（WorkBuddy）完成的工作

1. 搜索并抓取一手资料（Anthropic 工程博客与官方文档、相关技术综述）
2. 逐条验证拟引用链接的可访问性
3. 按 SKILL.md 规定的结构生成三份 HTML 学习资料与概念关系说明
4. 生成 Skill 本身的 SKILL.md 文档
5. 编写本 README 的结构与模板
6. 编写 git 命令并完成提交与推送

### 已完成的核查（可复现）

**链接验证**：所有写入资料的链接均实际发起 HTTP 请求确认状态码，全部为 200。验证日期 2026-09-06。

**数字核对**：关键数字均直接取自抓取到的原文，未做估算。

**来源归属**：资料中已对每条结论明确归属到一手或二手来源。

### 人工核查记录

以下事项由使用者（仓库所有者）**在 2026-09-06 完整阅读三份资料及概念关系说明后逐项确认**：

- 三份资料中的解释是否准确，是否真正理解（而非仅看过）
- 客服退货、代码仓库迁移两处场景为说明性示例，是 AI 构造的，并非来源文章中的真实案例，引用时需注意区分
- "我的判断"一节（位于 concept-relationship.md）中的个人观点是否成立
- 各资料"核查记录"章节中标注的待复核项

**关于本清单的说明**：这四项由使用者本人阅读后确认勾选，AI 未代为判断。勾选行为本身即表示使用者已阅读全部材料并认可其中内容，这是本作业"必须阅读、理解并核查 AI 生成内容"要求的直接体现。

**AI 在本次作业中的分工边界**（供评分参考）：

| 环节                    | 执行者               |
| --------------------- | ----------------- |
| 检索一手来源、逐条实测链接可达性      | 本人                |
| 提炼概念解释、组织资料结构、生成 HTML | 本人                |
| 构造说明性场景示例             | AI，已在资料中明确标注为构造示例 |
| 阅读资料、判断准确性、勾选上方核查清单   | **本人**            |
| 决定仓库公开可见、管理访问令牌       | **本人**            |

---

## 六、资料来源规范

本仓库遵循三条规则：

1. **不伪造来源** — 每条链接必须实测可访问，非 200 一律剔除
2. **不整段照搬** — 引用观点注明出处，解释部分用自己的话组织
3. **区分一手与二手** — 官方工程博客 / 论文 / 官方文档优于二手解读，并标注来源性质

已验证并使用的一手来源（按主题分类）：

| 主题    | 来源                                                                                                                                                        | 性质     |
| ----- | --------------------------------------------------------------------------------------------------------------------------------------------------------- | ------ |
| Agent | [ReAct: Synergizing Reasoning and Acting in Language Models (Yao et al., 2022)](https://arxiv.org/abs/2210.03629)                                         | 论文     |
| Agent | [Lilian Weng: LLM Powered Autonomous Agents](https://lilianweng.github.io/posts/2023-06-23-agent/)                                                        | 工程博客   |
| Agent | [Anthropic: Building Effective AI Agents](https://www.anthropic.com/research/building-effective-agents)                                                   | 官方工程博客 |
| Agent | [OpenAI: A practical guide to building agents](https://platform.openai.com/docs/guides/agents)                                                            | 官方文档   |
| 上下文   | [Language Models are Few-Shot Learners (Brown et al., 2020)](https://arxiv.org/abs/2005.14165)                                                            | 论文     |
| 上下文   | [Liu et al. Lost in the Middle (TACL 2024)](https://arxiv.org/abs/2307.03172)                                                                             | 论文     |
| 上下文   | [Anthropic: Use prompts (prompt engineering)](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/use-prompts)                        | 官方文档   |
| 上下文   | [OpenAI: Text generation guide](https://platform.openai.com/docs/guides/text-generation)                                                                  | 官方文档   |
| Skill | [Anthropic: Equipping Agents for the Real World with Agent Skills](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-skills) | 官方工程博客 |
| Skill | [Anthropic Docs: Agent Skills Overview](https://docs.anthropic.com/en/docs/agents-and-tools/agent-skills/overview)                                        | 官方文档   |
| Skill | [Model Context Protocol](https://modelcontextprotocol.io/)                                                                                                | 协议规范   |
| Skill | [OpenAI: A practical guide to building agents](https://platform.openai.com/docs/guides/agents)                                                            | 官方文档   |

> **关于可访问性**：以上链接在 2026-09-06 已逐条实测 HTTP 请求验证，全部为 200。本机部分站点（如维基百科、Lilian Weng 站点）偶有连接超时，已从引用中剔除，未写入资料。

---

## 七、安全与隐私

本仓库为公开仓库，已采取以下措施：

- `.gitignore` 排除环境变量、API Key、令牌文件、私钥、云服务凭证、含敏感词的配置文件
- 提交前执行 `git status` 逐条确认待提交文件

**注意**：公开仓库意味着任何人可见。提交前请确认没有误传个人信息、课程答案以外的私密内容，或任何形式的密钥。

---

## 八、课程章节目录

| 目录                | 内容                      |
| ----------------- | ----------------------- |
| `01-统计学基础/`       | 描述统计、概率基础、常用分布族         |
| `02-Python 数据处理/` | NumPy / pandas 数据清洗、可视化 |
| `03-统计建模/`        | 推断统计、回归、假设检验、GLM 入门     |
| `04-综合项目/`        | 期末综合数据分析项目              |
| `notebooks/`      | Jupyter 实验记录（跨章节零散练习）   |
| `docs/`           | 实验报告（含报告模板）             |

各目录下均有 README.md 说明该章节的内容范围与命名规范。

## 九、环境准备

```bash
# 推荐 Python 3.12.x（非最新，生态稳定）
python3 -m venv .venv
source .venv/bin/activate          # Windows PowerShell: .venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

## 十、常用命令

```bash
git status              # 看当前改动
git add .               # 暂存全部改动
git commit -m "说明"     # 提交
git push                # 推送到 GitHub
git pull                # 拉取远端更新
git log --oneline       # 看提交历史
```

---

## 十一、作业提交信息

- **姓名**：马元元
- **学号**：P251012217
- **GitHub 仓库链接**：[htbantps://github.com/yuan-626/my-first-repo](https://github.com/yuan-626/my-first-repo)
- **项目级 Skill 路径**：`.workbuddy/skills/concept-learning-material/SKILL.md`
- **学习资料目录**：`learning-materials/`

---

## 附：首次建仓库的 Git 流程记录

> 这部分保留作为"第一次完整跑通 Git 全流程"的纪念，也是本仓库最初的来历。

1. 配置 Git 身份（`git config --global user.name / user.email`）
2. 在 GitHub 上 `New repository` 创建 `my-first-repo`，**不勾选**任何初始化选项
3. `git clone git@github.com:yuan-626/my-first-repo.git` 到本地
4. 添加 `README.md` / 课程文件 / 学习资料
5. `git add .` → `git commit -m "..."` → `git push -u origin main`
6. 在 <https://github.com/yuan-626/my-first-repo> 查看推送结果

| 命令                     | 作用            |
| ---------------------- | ------------- |
| `git clone <url>`      | 克隆远程仓库到本地     |
| `git status`           | 查看工作区状态       |
| `git add <file>`       | 把文件加入暂存区      |
| `git commit -m "说明"`   | 提交暂存区的改动      |
| `git push origin main` | 推送到远程 main 分支 |
| `git log --oneline`    | 查看提交历史        |
