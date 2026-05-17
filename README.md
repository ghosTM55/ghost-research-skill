# ghost-research

基于横纵分析法（Horizontal-Vertical Analysis）的个人深度研究 Skill。它不是原版 `hv-analysis` 的简单复制，而是根据我自己的研究工作流做过适配：输出面向 Obsidian / KBS，强调可沉淀、可追踪、可复用的 Markdown 研究报告。

## 来源与致谢

本项目 fork / adapted from：

- 原项目：[KKKKhazix/khazix-skills](https://github.com/KKKKhazix/khazix-skills)
- 原 Skill：[hv-analysis](https://github.com/KKKKhazix/khazix-skills/tree/main/hv-analysis)
- 方法论提出者：[@Khazix0918](https://x.com/Khazix0918)

原项目采用 MIT License。若你继续 fork、改写或发布本项目，请保留对原作者与原方法论的署名。

## 这个版本改了什么

| 原版 hv-analysis | ghost-research |
|-----------------|----------------|
| 输出面向 PDF 研究报告 | 输出面向 Obsidian / KBS 的 Markdown 研究报告 |
| 更适合完整公开报告 | 更适合个人知识库、项目知识库、长期研究沉淀 |
| 固定报告生产流程 | 面向深度研究和 KBS 沉淀，默认生成可写入知识库的 Markdown 报告 |
| 偏通用 Agent 工具描述 | 改为更适配 Hermes Agent，同时保留可迁移性 |
| 图表规范较弱 | 增加 Mermaid 使用判断逻辑，但避免为了图而图 |
| 默认生成最终报告 | 默认服务于个人 KBS / 项目 KBS 的研究沉淀 |

## 我的使用场景

我的研究报告类工作主要通过 [Hermes Agent](https://github.com/NousResearch/hermes-agent) 完成，并沉淀到两类知识库中：

1. **个人 KBS / Obsidian**：用于个人长期研究、市场观察、产品分析、技术趋势判断。
2. **项目 KBS**：用于具体项目、公司、产品方向、合作机会或战略议题的研究沉淀。

因此这个 Skill 默认关注：

- Markdown / Obsidian 格式，而不是 PDF 排版；
- frontmatter、tags、aliases、双链、callout；
- 信息来源、置信度、延伸阅读；
- 研究对象的纵向历史、横向竞争格局和交叉洞察；
- 根据研究语境写入个人 KBS 或项目 KBS；路径不明确或存在覆盖风险时再确认。

## 适用场景

适合用来研究：

- 产品 / 公司 / 项目
- 技术概念 / AI 模型 / 行业范式
- 人物 / 团队 / 创始人
- 赛道 / 市场 / 竞品格局
- 一个你想真正搞懂、并沉淀进知识库的对象

不适合：

- 简单名词解释
- 一句话结论
- 新闻摘要
- 纯写作润色
- 不需要联网验证的轻量问答

## 使用前请根据自己情况修改

这个 Skill 带有明显的个人工作流假设。建议 fork 后至少检查并修改：

1. **输出位置**：个人 Obsidian、公司 KBS、项目文档库，或其他沉淀位置。
2. **frontmatter 字段**：tags、aliases、status、type、related_notes 是否符合你的知识库规范。
3. **研究范围**：根据你的知识库结构、研究对象类型和输出用途，调整竞品范围、来源标准和报告长度。
4. **联网工具**：根据你使用的 Agent，改成对应的搜索、浏览器、网页读取或论文检索工具。
5. **文件写入规则**：如果你的 Agent 有自动写文件能力，建议明确个人知识库、项目知识库和覆盖已有文件时的处理方式。
6. **语言风格**：是否需要更咨询报告、更学术、更口语，或更适合公开发布。
7. **可视化规范**：Mermaid、表格、关系图是否适合你的阅读和发布环境。

## 安装 / 使用

### Hermes Agent

如果你使用 Hermes Agent，可以把本 Skill 安装到本地 skills 目录，例如：

```bash
mkdir -p ~/.hermes/skills/research/ghost-research
cp ./SKILL.md ~/.hermes/skills/research/ghost-research/SKILL.md
hermes skills list | grep ghost-research
```

安装后开启新 session，或在当前 Hermes 会话中 `/reset`，再显式加载：

```text
/skill ghost-research
```

如果本项目发布到了 GitHub，也可以使用 raw `SKILL.md` URL 安装：

```bash
hermes skills install "https://raw.githubusercontent.com/<owner>/<repo>/main/SKILL.md" --category research --name ghost-research
```

### 其他 Agent

这个 Skill 本质上是 Markdown 指令集，不强依赖 Hermes。Claude Code、Codex、OpenCode 或其他支持 Agent Skills / 自定义指令的工具也可以改造使用。

但请注意：不同 Agent 的工具名、联网能力、文件写入权限和 skill 加载路径不同。不要直接照搬安装命令，先根据自己的 Agent 环境调整。

## 示例指令

```text
帮我用 ghost-research 的方式研究一下 Cursor
```

```text
调研一下 AI 视频生成工具赛道，重点看产品定位、商业化和用户口碑
```

```text
深度研究一下某家公司，并写入项目 KBS
```

## 默认输出形态

默认输出为 Obsidian Markdown 报告，包含：

- YAML frontmatter
- 执行摘要 callout
- 一句话定义
- 纵向分析：从诞生到当下
- 横向分析：竞争图谱
- 横纵交汇洞察
- 信息可靠性评估
- 延伸阅读

Mermaid 图表只在信息结构确实需要可视化时使用，不为了装饰强行加图。

## License

本项目基于 MIT License 的原始项目改写。发布时请保留原作者署名与许可证信息。
