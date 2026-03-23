# 📋 Standup Summarizer

> AI Skill：每日站会总结器 — 自动将站会内容转化为结构化、可执行的报告

## ✨ 功能特性

- 🎯 **智能识别** — 自动识别每位团队成员的更新内容
- 📊 **四维提取** — 已完成 / 进行中 / 阻塞项 / 下一步计划
- 📋 **待办生成** — 自动提取 Action Items 和阻塞汇总
- 🌐 **多格式输入** — 支持聊天记录、会议转录、语音转文字、Bullet Points
- 🌏 **中英双语** — 完整支持中文和英文站会
- 📤 **多平台输出** — Slack / 飞书 / Jira / Notion / CSV
- 📈 **趋势分析** — 多日数据分析，识别长期阻塞和进度风险

## 📁 文件结构

```
standup-summarizer/
├── SKILL.md                      # 技能主文件（核心指令）
├── README.md                     # 项目说明
└── references/
    └── output-formats.md         # 各平台输出格式模板
```

## 🚀 使用方式

这是一个 [OpenClaw](https://github.com/openclaw/openclaw) AI Agent Skill，安装后 Agent 会自动在合适的场景触发使用。

### 触发关键词

- `summarize standup` / `standup summary`
- `站会总结` / `站会纪要`
- `team status update` / `sprint progress`
- `what did the team do`

### 输入示例

直接把站会聊天记录或会议纪要发给 Agent：

```
张三：昨天完成了用户登录模块，今天开始做支付接口，没有阻塞
李四：PR #234 还在 review 中，被后端 API 变更阻塞了，今天继续跟进
王五：完成了单元测试覆盖率提升到 85%，下一步做集成测试
```

### 输出示例

```markdown
# Daily Standup Summary — 2026-03-23

## Team Updates

### 张三
- ✅ Done: 完成用户登录模块
- 🚧 In Progress: 支付接口开发
- 🚫 Blockers: None
- 📋 Next: 继续支付接口开发

### 李四
- ✅ Done: —
- 🚧 In Progress: PR #234 review
- 🚫 Blockers: 后端 API 变更
- 📋 Next: 跟进 API 变更问题

### 王五
- ✅ Done: 单元测试覆盖率提升至 85%
- 🚧 In Progress: —
- 🚫 Blockers: None
- 📋 Next: 集成测试

## Blockers Summary
| 人员 | 阻塞问题 | 严重程度 |
|------|---------|---------|
| 李四 | 后端 API 变更 | High |
```

## 📤 支持的输出平台

| 平台 | 格式 | 说明 |
|------|------|------|
| Markdown | 默认 | 通用结构化格式 |
| Slack | mrkdwn | Slack 消息格式 |
| 飞书/Lark | Markdown | 飞书文档兼容格式 |
| Jira | Wiki Markup | Jira 评论格式 |
| Notion | Markdown + Callouts | Notion 页面格式 |
| CSV | 表格 | 数据分析导出 |

## 📈 高级功能：趋势分析

提供多天站会数据时，Skill 会自动分析：

- ⏰ 超过 3 天仍在 "进行中" 的任务
- 🔄 反复出现的阻塞问题
- ⚠️ 可能需要帮助的团队成员

## 🛠️ 技术栈

- **运行环境：** [OpenClaw](https://github.com/openclaw/openclaw) AI Agent
- **Skill 规范：** AgentSkills v1

## 📄 License

MIT
