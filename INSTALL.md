# 安装与使用

**alpha0.1-preview · 非常早期的预览实验版**

有终端与项目文件权限的 Agent 可从 GitHub 安装；账号技能库按要求上传完整 ZIP；不支持原生导入的任务可阅读完整单文件方法版。

## 让 Agent 安装

把下面一句话发给当前 Agent：

```text
请从 https://github.com/viowai/7viow-presentation-production 安装 alpha0.1-preview 的 7viow-presentation-production，按仓库 INSTALL.md 选择当前宿主的方式，默认仅用于当前项目，并确认入口、全部参考、模板和许可文件完整可读。
```

执行时沿用已有的宿主与安装范围决定；未指定范围则安装到当前项目。已有同名技能时先保存本地改动，再更新原入口。整个技能目录一起安装，保留相对位置；只有 `SKILL.md` 会丢失方法参考和模板。

安装器复制成功后，还要在实际宿主确认技能是否可见。缺少终端、文件写入或自定义导入能力时，改用下方适用方式，并说明实际完成范围。

## 终端快捷安装

需要 **Node.js 22.20.0 或更高版本**。在要使用 Skill 的项目目录执行。以 Codex 为例：

```bash
npx -y skills@1.7.4 add viowai/7viow-presentation-production --skill 7viow-presentation-production --agent codex --copy -y
```

这条命令使用仓库当前默认分支，安装到当前项目。`--copy` 保留完整文件副本；`--skill` 限定本技能，避免扩大安装范围。

**固定为 alpha0.1-preview：**

```bash
npx -y skills@1.7.4 add https://github.com/viowai/7viow-presentation-production/tree/alpha0.1-preview --skill 7viow-presentation-production --agent codex --copy -y
```

如需长期精确复现某次文档与包内容，可在上述 `tree/` 后使用 GitHub 上相应的完整提交号。预览版名称保持不变时，安装说明和分发修正可能同步到该预览标签。

Node.js 用于快捷安装；本 Skill 的方法正文没有 Node.js 运行依赖。PPT 制作和验收仍需要宿主提供相应文件工具。

## 选择目录型宿主

将命令中的 `codex` 换成下面的参数。路径为 **Skills CLI 1.7.4** 的项目级目标；不是所有同品牌网页端的安装路径。

| 宿主 | `--agent` 参数 | 项目内目录 |
| --- | --- | --- |
| Codex | `codex` | `.agents/skills/` |
| Claude Code | `claude-code` | `.claude/skills/` |
| Cursor | `cursor` | `.agents/skills/` |
| GitHub Copilot | `github-copilot` | `.agents/skills/` |
| OpenCode | `opencode` | `.agents/skills/` |
| Antigravity App / IDE | `antigravity` | `.agents/skills/` |
| Antigravity CLI | `antigravity-cli` | `.agents/skills/` |
| Gemini CLI | `gemini-cli` | `.agents/skills/` |
| Grok Build | `grok` | `.grok/skills/` |
| CodeBuddy | `codebuddy` | `.codebuddy/skills/` |
| TRAE | `trae` | `.trae/skills/` |
| TRAE CN | `trae-cn` | `.trae/skills/` |
| Qoder | `qoder` | `.qoder/skills/` |
| ZCode | `zcode` | `.zcode/skills/` |

安装器参数与路径依据：[固定版本宿主表](https://github.com/vercel-labs/skills/blob/v1.7.4/docs/agents.md)。实际客户端的目录、启用与刷新方式见 [宿主说明](HOSTS.md)。

**Qoder CN：**官方项目路径为 `.lingma/skills/`，个人路径为 `~/.lingma/skills/`；安装器 1.7.4 的 `qoder-cn` 分别写入 `.qoder/skills/` 和 `~/.qoder-cn/skills/`，存在差异。本版按下方完整目录复制法放入官方位置，再按客户端要求刷新或重启 IDE。[Qoder CN 官方说明](https://docs.qoder.cn/user-guide/skills)

**跨项目使用：**明确选择个人范围后，可给命令加 `--global`；具体个人目录见 [宿主说明](HOSTS.md)。Antigravity App 的官方个人目录为 `~/.gemini/config/skills/`，安装器 1.7.4 的 `antigravity --global` 使用旧位置 `~/.gemini/antigravity/skills/`；App 跨项目使用时采用完整目录复制法放入官方位置。Antigravity CLI 的个人目录为 `~/.gemini/antigravity-cli/skills/`，与 App 分开。[Antigravity 官方说明](https://antigravity.google/docs/skills)

## 下载与手动复制

从 [alpha0.1-preview 发布页](https://github.com/viowai/7viow-presentation-production/releases/tag/alpha0.1-preview) 选择：

| 包 | 选择条件 |
| --- | --- |
| [完整目录 ZIP](https://github.com/viowai/7viow-presentation-production/releases/download/alpha0.1-preview/7viow-presentation-production-alpha0.1-preview.zip) | 解压后取得同名技能目录；用于本地复制或接受外层文件夹的上传入口。 |
| [根目录 ZIP](https://github.com/viowai/7viow-presentation-production/releases/download/alpha0.1-preview/7viow-presentation-production-alpha0.1-preview-root.zip) | `SKILL.md` 直接位于 ZIP 根部；用于相应账号上传入口。 |
| [Portable Plugin ZIP](https://github.com/viowai/7viow-presentation-production/releases/download/alpha0.1-preview/7viow-presentation-production-plugin-alpha0.1-preview.zip) | 根部有 `plugin.json`，Skill 位于 `skills/`；仅交给接受该插件格式的入口。 |
| [完整单文件方法版](https://github.com/viowai/7viow-presentation-production/releases/download/alpha0.1-preview/7viow-presentation-production-alpha0.1-preview-manual.md) | 作为当前任务的方法资料；不是原生安装或单独抽取的 `SKILL.md`。 |

手动复制时，把解压所得完整目录放到选定宿主位置。例如 Codex 项目最终为：

```text
你的项目/
└── .agents/skills/7viow-presentation-production/
    ├── SKILL.md
    ├── references/
    ├── assets/
    ├── agents/openai.yaml
    ├── LICENSE.txt、COPYRIGHT.txt
    └── README.md、INSTALL.md、HOSTS.md、VERSION
```

也可在目标项目通过安装器复制已解压的本地目录。把示例路径替换为实际目录，不要指向 ZIP：

```bash
npx -y skills@1.7.4 add /path/to/7viow-presentation-production --skill 7viow-presentation-production --agent codex --copy -y
```

## 账号上传与插件入口

Claude 账号技能库、Gemini Enterprise、M365 Agent Builder、WorkBuddy、DuMate、千问办公及其他客户端的具体入口与条件见 [宿主与上传方式](HOSTS.md)。根据入口选择完整目录 ZIP 或根目录 ZIP；portable plugin 包不能替代普通技能上传包。

GitHub 公开不等于进入 ChatGPT 或其他产品的插件市场。账号上传、插件安装和本地目录安装分别验证；本版尚未逐一完成这些入口的真实导入及完整任务运行。

临时使用单文件版时，把该文件和任务材料一起交给 AI：

> 请完整读取这份 7viow-presentation-production 方法文件，按当前已确认阶段处理本次任务。所需参考与模板已经内联；遇到缺少的文件工具，明确说明能完成的范围。

## 确认安装与第一次使用

查看当前项目的安装记录：

```bash
npx -y skills@1.7.4 list --agent codex
```

个人范围安装的查询也加 `--global`。再在实际宿主中刷新技能列表或新开会话，确认 `7viow-presentation-production` 可选、能读取参考与模板。Codex 可使用 `$7viow-presentation-production`；其他宿主按技能菜单或名称调用。

第一次可先让它处理不涉及外部发送的小任务：

> 用 7viow-presentation-production 阅读这些材料，整理本次演示的读者、用途、保留决定与所需文件，给我完整需求提示供确认；先不上传材料或开始原生制作。

## 更新与移除

更新由你手动触发。先保存自己改过的技能文件，再在原项目重复相同安装命令，保持宿主和范围一致。固定在预览版时继续使用其 tag 地址；要更换版本则明确选择新的 tag。上传型入口按客户端要求替换完整包，避免同时启用同名目录版和插件版。

移除当前项目中的本技能：

```bash
npx -y skills@1.7.4 remove 7viow-presentation-production -y
```

该命令按名称移除当前项目各宿主的本技能，保留其他技能；个人范围版本需加 `--global`。多个 Agent 可能共享 `.agents/skills/`，只想在其中一个宿主停用时，应使用该产品的启用开关。这里采用按名称完整移除，避免把共享目录的 `remove --agent codex` 当作必然删除文件的命令。

手动复制的版本通过宿主管理入口或移除对应技能目录处理；账号上传与插件包使用各自的卸载入口。操作后检查文件和技能列表。

## 常见问题与验证范围

- **找不到技能：**检查宿主参数、项目与个人范围、入口目录、启用状态和会话刷新；网页端不会自动读取本机技能目录。
- **缺参考或模板：**重新安装完整目录，保留资源相对位置。
- **Node.js 版本不满足：**使用 22.20.0 或更高版本，或改用完整 ZIP 手动复制。
- **无法访问 GitHub 或 npm：**使用已取得的完整包和宿主允许的导入方式。
- **能发现技能但不能生成 PPTX：**安装只提供方法，实际制作、编辑和导出仍取决于宿主工具。

公开源的项目级安装、完整文件复制、重复安装、列出与按名称移除已在隔离项目验证。上表宿主参数覆盖的是安装器路径及资源完整性；各原生客户端中的发现、模型调用与 PPT 制作表现仍需分别验证。

完整 CLI 操作依据见 [Skills CLI 1.7.4](https://github.com/vercel-labs/skills/blob/v1.7.4/docs/commands.md)。本包采用 [Apache-2.0](LICENSE.txt)。
