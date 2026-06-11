# feasibility-gate · 可行性与合规闸门

> 给用 AI agent 开发程序的小白/新手兜底的一道硬性闸门：在动手写代码**之前**，先把关"开发难度、运维难度、中国大陆合规审核"，把会让人彻底卡死的问题提前拦下来，引导到**最简单、最容易自己跑起来和部署**的方案。

适用 [Claude Code](https://code.claude.com)、以及任何兼容 [agentskills.io](https://agentskills.io) SKILL.md 标准的 agent（Cursor / Codex / Gemini CLI 等）。

当前版本：**v1.1.0**（见 [CHANGELOG](./CHANGELOG.md)）

## 它解决什么

小白用 AI 做东西，最常卡死的不是"写不出代码"，而是：

- 写完了**不会装、不会跑、不会部署**
- **选错技术栈/框架**，走了一堆弯路
- 做到一半才发现功能需要**营业执照 / ICP 备案 / 支付资质 / 内容审核**，前面全白做

这个 skill 在头脑风暴出方案之后、写代码之前介入，逐项打分 + 查合规红线 + 给出最简方案。

## 安装

### 方式一：插件市场（推荐，支持自动更新）

在 Claude Code 里执行：

```
/plugin marketplace add warsen-lab/feasibility-gate
/plugin install feasibility-gate@feasibility-gate
```

### 方式二：手动复制

把 `skills/feasibility-gate/` 文件夹复制到你的 `~/.claude/skills/` 下即可。

## 使用

装好后它会按描述自动触发；也可以直接对 Claude 说：

> 用 feasibility-gate 帮我把关这个方案：我想做一个 XX

## 更新

本 skill 内置版本检查：每个会话首次调用时，会拉取本仓库的 `VERSION` 与本地版本比对，发现新版会提醒你更新（拉取失败/离线则静默跳过，不影响使用）。

收到提醒后更新：

```
# 插件方式安装的：
/plugin marketplace update feasibility-gate
/plugin update feasibility-gate

# 手动安装的：重新拉取本仓库，覆盖 ~/.claude/skills/feasibility-gate/
```

## 维护者发版清单

每次发新版，**同步改这三处**并保持一致，再 commit + push + 打 tag：

1. `skills/feasibility-gate/SKILL.md` frontmatter 的 `version`
2. 根目录 `VERSION` 文件
3. `CHANGELOG.md` 增加版本条目

```bash
git tag v1.1.0 && git push --tags
```

> 注意：版本检查读取的是 `main` 分支的 `VERSION` 文件，push 到 main 后用户即可被提醒。

## 需要人帮一把

如果方案确实需要办理资质或部署复杂、超出自助范围，可加作者微信 **warsenliu** 协助。

## 许可

[MIT](./LICENSE)
