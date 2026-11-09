# work-with-docs（wwd）

用于持续编写、审阅、讨论、迁移和归档 Markdown 文档的中文技能。它帮助你把已确认结果组织成可点击的分层目录和独立主题，按需保存工作材料，并在获得授权后维护待讨论与待办。

版本：0.7.4。许可证：[MIT](LICENSE)。

## 能做什么

- 编写和审阅文档，维护概览、术语与关联链接。
- 用 `grill` 深入讨论指定问题，用 `gloss` 梳理概念。
- 根据用户指令迁移、归档或保存阶段版本。

普通聊天不会自动建立文档库，讨论不自动授权正式写入。技能由 Markdown 和 YAML 组成，无脚本、联网服务、API 密钥或必装的其他技能。

技能入口：[SKILL.md](skills/work-with-docs/SKILL.md)。详细规则和模板：[文档目录](skills/work-with-docs/docs/00目录.md)。

## Windows 桌面应用安装

适用于支持本地技能的 ChatGPT Windows 桌面应用中的 Codex 工作环境。官方说明确认 Windows 应用支持技能，并默认使用 Windows 原生 Agent；本包完成了静态兼容检查，尚未在 Windows 实机验证加载和使用。

1. 解压本仓库。
2. 按 `Win + R`，输入 `%USERPROFILE%`，在用户目录下创建 `.agents`，再在里面创建 `skills`（已有则复用）。
3. 将仓库中 `skills/work-with-docs` 整个文件夹复制进去。最终文件应位于 `%USERPROFILE%\.agents\skills\work-with-docs\SKILL.md`，同级保留 `agents` 和 `docs` 文件夹。已有同名技能时，先保留旧版，再替换整个文件夹，避免混入旧文件。
4. 打开应用的 Skills 入口查找 `wwd · work with docs` 或 `work-with-docs`。没有出现时重启应用，再检查目录是否多套了一层。
5. 选中该技能，或在聊天中明确说“使用 work-with-docs”。让 Agent 报告实际读取的 `SKILL.md` 路径与版本，确认是本次安装的 0.7.4。

如只想在一个项目中使用，可将文件夹放在该项目的 `.agents/skills/` 下。用户级与项目级避免重复安装同名版本。

如果已将 Agent 切换为 WSL，应放在该 Linux 用户的 `~/.agents/skills/work-with-docs`；仅改变集成终端类型，不等于切换 Agent。无需为使用本技能启用 WSL。

## 首次试用

在一个允许写入的测试项目中选择技能，发送：

> 使用 work-with-docs。在当前项目的 wwd-demo 目录，为下面已确认的规则建立简短 Markdown 使用说明和目录：草稿保存在本地；用户可导出副本。只使用这些事实，可以写文件。

确认能读取技能、中文正常显示、生成文件位置正确，且目录能打开正文。再发送：

> 只在聊天讨论：是否需要增加自动备份？暂不写文件，也不加入待讨论。

确认第二轮保留讨论边界。示例不代表任何真实产品已具备这些能力。

## 跨平台说明

保留中文文件名和 UTF-8 编码；用编辑器保存时避免转换为系统本地编码。技能自身不要求运行 PowerShell、Bash 或安装依赖；Agent 实际读写文件使用当前环境支持的工具。

库内 Markdown 链接使用相对路径和正斜杠。库外本地文件链接依赖接收者的设备与阅读器，不会随技能跨设备迁移。Obsidian 只是可选阅读器，其个人配置不在发布包内。

macOS/Linux 本地安装同样使用当前用户的 `~/.agents/skills/`，或项目内 `.agents/skills/`。本仓库提供可手动安装的独立技能，不包含插件市场发布配置。

## 官方依据

安装说明核对日期：2026-11-09。应用版本和组织配置可能影响本地技能入口。

- [Build skills：技能结构、本地发现目录与调用](https://developers.openai.com/codex/skills)
- [ChatGPT desktop app for Windows：技能支持及 Windows/WSL 环境](https://learn.chatgpt.com/docs/windows/windows-app)

