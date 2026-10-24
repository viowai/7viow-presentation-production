# 宿主、安装与使用方式

入口资料复核日期：2026-10-24。按实际宿主、账户许可与客户端版本选择包格式。以下说明不表示已在全部宿主安装或运行验证。

## 阅读方法

“官方入口已核实”表示查到了对应入口或路径；“实际运行”需要在当前宿主通过真实任务验证。两者不能互换。原生入口不明的产品可使用完整手动说明，但只有提供实际文件生产、回收和验证能力时，才可能完成本 Skill 的全部结果。手动阅读不称原生安装或自动触发。

Skill 技术名统一为 `7viow-presentation-production`。文件夹方式的目标是 `宿主技能目录/7viow-presentation-production/SKILL.md`，同时保留 references、assets 和其他随包资源。目录包与单文件版只选一种，避免同名重复来源。

## 国际目标

| 产品 | 经官方资料核实的方式 | 本包形态与边界 |
| --- | --- | --- |
| Codex 本地 Desktop／CLI／IDE | 项目 `.agents/skills/`，用户 `~/.agents/skills/`；显式或按描述调用 | 完整目录包。需在实际安装后核对发现与调用。[官方 Skills](https://learn.chatgpt.com/docs/build-skills) |
| ChatGPT Work | 独立 skills 支持桌面；跨 Web／桌面／移动的分发通过 plugin。创建方法与消费分发入口不同 | 另生成 `7viow-presentation-production` portable plugin 预览包：根 `plugin.json` 和 `skills/`。未提交目录、未注册市场、未验证云端运行。[Skills](https://learn.chatgpt.com/docs/build-skills)、[Plugin 包结构](https://developers.openai.com/plugins/build/plugins) |
| Claude Code | 项目 `.claude/skills/`，用户 `~/.claude/skills/` | 目录包，使用标准 name/description，不依赖 Codex 专有工具。[官方 Skills](https://code.claude.com/docs/en/skills) |
| Claude Work／Cowork | 在 Desktop Customize 或 claude.ai Skills 设置管理账户启用的技能；Cowork不读取本机 `~/.claude/skills/` | 账户上传是另一项明确动作。保留完整资源，不把 Claude Code 本地路径当作 Cowork 可见性证明。[官方账户与云端区别](https://code.claude.com/docs/en/skills#use-skills-in-cowork-and-cloud-sessions) |
| GitHub Copilot | 项目 `.github/skills/`、`.agents/skills/` 等；用户 `~/.copilot/skills/` 或 `~/.agents/skills/` | 目录包；具体 IDE／CLI／cloud 的文件工具仍分别验证。[官方 Agent Skills](https://docs.github.com/en/copilot/concepts/customizations/agent-skills) |
| Microsoft 365 Copilot | Agent Builder声明式Agent的Skills预览：Configure → Skills → Add，上传完整ZIP；仅适用Frontier组织及相应许可，IB租户不可用 | 使用 `-root.zip`（根部SKILL.md，剔除无扩展名VERSION；入口少于20,000字符）。公开ISV发布尚不支持，不把GitHub Copilot路径代作M365适配。[官方条件](https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/declarative-agent-skills)、[上传结构](https://learn.microsoft.com/en-us/microsoft-365/copilot/extensibility/agent-builder-add-skills) |
| Cursor | 项目 `.agents/skills/` 或 `.cursor/skills/`；用户对应目录 | 目录包；本地与云端可用性分开，未代用户启用同步。[官方 Skills](https://prod.cursor.com/docs/skills) |
| Google Antigravity | 项目 `.agents/skills/`；App／IDE用户目录为 `~/.gemini/config/skills/`，CLI为 `~/.gemini/antigravity-cli/skills/` | 目录包；按实际App／IDE／CLI选择目录。[官方 Skills](https://antigravity.google/docs/skills) |
| Gemini Enterprise | Web Skills → + → Upload skill，MD/ZIP；Standard/Plus/按量版支持上传，Frontline不支持自建上传，需管理员启用 | 使用 `-root.zip`，官方也接受单顶层目录内的SKILL.md，本包默认提供根ZIP。该技能入口属于assistant，官方列明不能与agents混用；未实测Canvas和PPTX导出。[官方Skills](https://docs.cloud.google.com/gemini/enterprise/docs/skills) |
| OpenCode | 项目 `.opencode/skills/`，用户 `~/.config/opencode/skills/`；兼容 `.agents/skills/` 等 | 目录包。[官方 Skills](https://opencode.ai/docs/skills/) |

## 中国目标

| 产品 | 经官方资料核实的方式 | 本包形态与边界 |
| --- | --- | --- |
| 腾讯 WorkBuddy | 技能页 → 添加技能 → 上传技能；自定义本地包通过该入口导入 | 完整 ZIP。聊天安装市场技能不能替代自定义包导入。[官方使用说明](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market) |
| 腾讯 CodeBuddy | 项目 `.codebuddy/skills/`，用户 `~/.codebuddy/skills/` | 目录包；不包含 hooks，不要求调整信任或安全设置。[官方 CLI Skills](https://www.codebuddy.cn/docs/cli/skills) |
| 百度 DuMate | Skills → Add → Install，支持 URL 或本地 ZIP／MD | 本包选完整 ZIP；手动版仅随任务阅读，不作为原生MD包上传。[官方扩展说明](https://cloud.baidu.com/discover/dumate-skill-extension-admin.html) |
| 百度 库库AI／Comate | 未核实相应版本导入本包的原生入口 | 单文件方法版；待目标产品、版本与官方入口明确后补实测，不套用 DuMate 路径。 |
| 字节 TRAE IDE | 项目 `.trae/skills/`；CN 用户目录 `~/.trae-cn/skills/`；设置中可导入 ZIP／MD。`.agents/skills` 需启用相应开关 | 目录或 ZIP；设置调整由用户明确授权。国际版目录需按实际客户端核实，不照抄 CN 全局路径。[官方技能](https://docs.trae.cn/ide_skills) |
| TraeWork | 插件市场 → 技能 → 上传技能，要求根级SKILL.md的ZIP／.skill；本地与云端运行环境分别生效 | 使用 `-root.zip`。本地任务需桌面版，不能用本地安装证明云端可见。[官方Work Skills](https://docs.trae.cn/work_skills) |
| 豆包工作 | 未核实当前账户可用的自定义Skill上传合同 | 暂提供完整单文件方法版。不能从开放平台介绍推断可直接导入某种ZIP，现有官方PPT能力与自定义Skill导入分别判断。[官方开放平台](https://open.doubao.com/) |
| 阿里 Qoder／Qoder CN | IDE／CLI：项目 `.qoder/skills/`、用户 `~/.qoder/skills/`；Qoder 新客户端：Extensions → Skills → Add Skills → Upload Skill，支持ZIP／MD | 根据实际客户端选择入口，不同时装多个同名副本。[IDE／CLI](https://docs.qoder.com/extensions/skills)、[客户端](https://docs.qoder.com/qoder/skills) |
| 阿里 QwenWork | 中文文档提供 `~/.qwenwork/skills/`；企业管理端支持技能ZIP，单顶层同名目录、≤10 MB，并受个人上传/组织策略约束 | 完整目录或 ZIP；账户权限、地域与版本分别确认，不更改组织策略。[本地 Skills](https://www.alibabacloud.com/help/zh/qwenwork/skills)、[企业技能管理](https://www.alibabacloud.com/help/en/qwenwork/skills-management) |
| 智谱 ZCode | 用户 `~/.zcode/skills/<name>/SKILL.md`；设置 Skills 页面刷新并启用；项目目录见官方QA | 目录包；未执行刷新/启用。[官方 Skills](https://zcode.z.ai/en/docs/skill)、[项目QA](https://zcode.z.ai/en/docs/qa) |

## 选择下载格式

1. **目录／ZIP**：完整保留 Skill 及引用，交给已支持该格式的宿主。常规ZIP是单个同名顶层文件夹，QwenWork使用此形态；`-root.zip`把SKILL.md和资源直接置于根部，适配已核实的Gemini Enterprise、M365 Agent Builder与TraeWork格式。两者方法文件一致，仅根部包结构及VERSION元数据不同。安装后以真实小任务核对描述发现、引用读取和文件输出。
2. **单文件手动版**：入口、全部参考和模板已内联。把它作为方法资料随当前任务提供，明确要求使用。它不作为原生Skill上传文件，不声称自动触发，也不赋予宿主本来没有的工具；已核实原生入口的产品优先用完整ZIP/目录。
3. **Portable plugin 预览包**：共享同一份 Skill，用于支持 Agent Plugins 的分发路线试用。包内包含同一份完整 Skill；该预览包尚未完成原生安装验收或市场登记。[官方包装依据](https://developers.openai.com/plugins/build/plugins)

## 需要实测才能升级的声明

每个具体宿主都要验证一次：完整资源可读→真实新材料生成→实际原生文件回收→局部修改保留→目标阅读导出。在未运行的宿主，状态统一是“官方入口/方法覆盖，运行未测试”。当前没有任何宿主被声明为完成安装验收。

本说明不支持跨产品自动同步、自动更新或代表用户公开提交。文档入口日后变化时，由维护者手动触发核查和重新打包。
