# Output Format Templates

## Slack Format

Use Slack mrkdwn syntax:

```
*🗓 Daily Standup — {date}*

*👤 {name}*
✅ {done items}
🚧 {in progress items}
🚫 {blockers}
📋 {next items}

---
*⚠️ Blockers Requiring Attention:*
• {blocker} — {owner}
```

## Feishu/Lark Format

Use Feishu-compatible markdown:

```markdown
# 每日站会纪要 — {date}

## 团队更新

### {name}
- ✅ 已完成：{done items}
- 🚧 进行中：{in progress items}
- 🚫 阻塞项：{blockers}
- 📋 下一步：{next items}

## 待办事项
- [ ] {action} — 负责人：{name}

## 阻塞汇总
| 人员 | 阻塞问题 | 严重程度 |
|------|---------|---------|
| {name} | {issue} | 高/中/低 |
```

## Jira Comment Format

Use Jira wiki markup:

```
h2. Daily Standup — {date}

h3. {name}
* (/) *Done:* {done items}
* (!) *In Progress:* {in progress items}  
* (x) *Blockers:* {blockers}
* (->) *Next:* {next items}

h3. Action Items
|| Action || Owner || Due ||
| {action} | {name} | {date} |
```

## Notion Format

Use Notion-compatible markdown with callouts:

```markdown
# Daily Standup — {date}

## {name}

> ✅ **Done**
> - {done items}

> 🔨 **In Progress**  
> - {in progress items}

> ⚠️ **Blockers**
> - {blockers}

> 📋 **Next**
> - {next items}

---

## Action Items
- [ ] {action} → @{name}
```

## CSV Export Format

For data analysis:

```
date,person,category,item
{date},{name},done,{item}
{date},{name},in_progress,{item}
{date},{name},blocker,{item}
{date},{name},next,{item}
```
