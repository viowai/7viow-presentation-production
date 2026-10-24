# 7viow Presentation Production

**alpha0.1-preview · 非常早期的预览实验版**

一项帮助 AI 协调 PPT 生产的 Skill：从意图和内容规划开始，形成可执行的制作交接，接回实际文件，完成修改、原生编辑检查与导出。

适合愿意参与内容确认、检查实际作品并反馈问题的早期试用者。当前方法和宿主适配仍在验证中，流程、包结构与使用方式可能继续调整。

作者与维护者：Viow。系列品牌：7viow。

## 可以用来做什么

- 从原始资料组织新演示：确认用途、结构、页级内容与制作方案，再进入原生文件制作。
- 延续已确认的材料：继承有效的内容和设计决定，只确认本轮实质变化。
- 处理返回稿和作者手改：识别真实当前原件，完成局部修改、章节整合或不同读者版本，并保留未受影响的内容。
- 完成交付检查：核对全稿内容、视觉关系、可编辑对象、目标应用表现、阅读导出和后续编辑来源。

## 快速安装

把下面一句话发给具备终端与文件权限的 Agent：

> 请从 https://github.com/viowai/7viow-presentation-production 安装 alpha0.1-preview 的 7viow-presentation-production，按仓库 INSTALL.md 选择当前宿主的方式，默认仅用于当前项目，并确认入口、全部参考、模板和许可文件完整可读。

也可在目标项目终端执行。以下以 Codex 为例，需要 **Node.js 22.20.0 或更高版本**：

```bash
npx -y skills@1.7.4 add viowai/7viow-presentation-production --skill 7viow-presentation-production --agent codex --copy -y
```

Claude Code 将 `codex` 换成 `claude-code`，Cursor 换成 `cursor`。固定预览版本安装、其他宿主、确认发现、更新与移除见 [完整安装说明](INSTALL.md)。不使用终端时，在下方选择完整下载包。

## 下载与开始使用

从 [alpha0.1-preview 下载页](https://github.com/viowai/7viow-presentation-production/releases/tag/alpha0.1-preview) 选择包。具体宿主路径、上传方式及条件见 [宿主与使用方式](HOSTS.md)。

| 文件 | 用途 |
| --- | --- |
| `7viow-presentation-production-alpha0.1-preview.zip` | 含同名顶层文件夹的完整目录包，用于本地技能目录及接受该结构的上传入口。 |
| `7viow-presentation-production-alpha0.1-preview-root.zip` | `SKILL.md` 位于 ZIP 根部，用于要求根级入口的宿主。 |
| `7viow-presentation-production-plugin-alpha0.1-preview.zip` | 含 `plugin.json` 与 `skills/` 的 portable Agent Plugins 预览包。 |
| `7viow-presentation-production-alpha0.1-preview-manual.md` | 完整单文件方法版，供不支持原生 Skill 导入的任务作为上下文阅读。 |

本地安装时，将完整的 `7viow-presentation-production` 文件夹放入宿主技能目录，保留全部参考和模板。例如 Codex 的用户目录为 `~/.agents/skills/`，项目目录为 `.agents/skills/`；同名 Skill 只保留一个有效来源。[Codex 官方说明](https://learn.chatgpt.com/docs/build-skills)

然后明确调用 `7viow-presentation-production`，附上实际源文件、读者与用途、要保留的决定、设计参考及需要的输出。比如：

> 用 7viow-presentation-production，基于这些原始资料制作一份面向合作方的演示。先给我完整需求提示，再逐层确认结构和内容；最终需要可编辑 PPTX、PDF 和必要制作源。

已有确认稿时，可以直接说：

> 沿用这份已确认 PPT 的内容和风格，保留全部条件。目录和事实不用重问，只修改第 6 页的关系图并重新导出，其他内容保持不变。

单文件方法版需随任务提供，并要求 AI 阅读其中的方法和所需章节；它不会安装 Skill 或增加宿主工具。

## 协作方式

新任务默认依次处理意图、完整提示、外部规划、结构与内容确认、制作交接、返回稿及原生交付。已有批准的决定直接继承；用户可明确调整本次路线与确认范围。

外部规划默认推荐 ChatGPT 或豆包，制作交接默认推荐 Kimi 或豆包。交接时核实辅助设计能力，并按需推荐三项 7viow writing skills；实际发布、可用性和导入方式须在任务当时查证。它们是可选协作能力，使用本 Skill 不以安装其他 Skill 为前提。若外部路线不可用，先明确能力缺口，再确认可行的替代路线。

协调者负责接续与实际交付，内容作者负责含义，制作工具负责原生版式和导出。一个 AI 可以承担多个角色。

## 已知限制

- 这是非常早期的实验预览，尚未建立跨宿主稳定性和质量提升的充分证据。
- 已有本地原始材料生成、连续修改和 PowerPoint 原生验收的运行记录；项目级安装器复制已在隔离目录验证，原生宿主的自动发现、账号导入和完整制作仍未逐一测试。
- 本 Skill 提供工作方法。实际 PPTX 制作、文件回收、应用编辑与 PDF 导出需要宿主具备相应工具。工具不可用时，应明确具体缺口。
- 尚未完成可支持改善结论的同条件 A/B 对照。平台账户、额度、字体和文件工具会影响实际结果。
- 外部上传、安装、登录、支付和公开发布依照实际用户授权执行。更新由维护者手动发版，包内没有自动更新或后台任务。

## 内容与反馈

[SKILL.md](SKILL.md) 是入口；`references/` 保存按需方法；`assets/` 提供可改写的工作模板；`agents/openai.yaml` 提供宿主展示信息。完整资源均随包提供。

通过 [Issues](https://github.com/viowai/7viow-presentation-production/issues) 反馈宿主与版本、实际任务、预期结果、观察到的问题及可公开的最小复现。提交前移除私人或客户材料。

采用 [Apache License 2.0](LICENSE.txt)。Copyright 2026 Wenbin Li；作者与维护者 Viow。版权说明见 [COPYRIGHT.txt](COPYRIGHT.txt)。
