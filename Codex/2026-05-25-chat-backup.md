# Claude Code Session Backup — 2026-05-25

## Summary
Migrated three automation workflows from Codex to Claude Code, configured community news automation for Feishu, and set up auto-renewal for persistent scheduling.

## Automations Configured

### 1. Chat Backup (Daily 20:07)
- Backs up daily chat content to GitHub repo `AmberTreelet/codex`
- Cron ID: `22f8dc82`

### 2. Web3 Community News (Daily 06:03)
- Searches Web3/blockchain industry news (tech upgrades, protocol development, regulatory policy, security)
- Generates Chinese-language community news digest: 【Web3 行业资讯｜社区早报】
- Max 6 items, each with title, summary, community discussion value, source link
- Strict Feishu compliance: no token prices, no investment advice, no promotional content
- Pushes to Feishu webhook: 397392a2-ae0e-483f-bf0c-e9b939808699
- Cron ID: `be55a9fb`

### 3. AI Community News (Daily 06:13)
- Searches AI tech news (X, Reddit r/MachineLearning, r/LocalLLaMA, Hacker News, arXiv, The Verge)
- Generates Chinese-language community news digest: 【AI 科技资讯｜社区早报】
- Max 6 items, each with title, summary, community discussion value, source link
- Pushes to Feishu webhook: 89b2452d-ae2d-4417-a06e-84ebdd6d2a7b
- Cron ID: `2262452b`

### 4. Auto-Renewal (Every 3 days)
- Recreates all 4 cron jobs to prevent 7-day expiry
- Cron ID: `ac07af96`

## Technical Details
- Platform: Claude Code 2.1.150 via VS Code extension
- Permissions: WebSearch, WebFetch, Bash(curl *), Bash(git *), Bash(python3 *) all auto-allowed
- Durable cron: enabled
- Project: `/Users/1070674011qq.com`

## Test Results (2026-05-25)
- Web3 community news: Sent to Feishu successfully
- AI community news: Sent to Feishu successfully
- Chat backup: Pushed to GitHub successfully
- Cron test: Verified Full Disk Access permission for system cron
- Permission auto-allow: Configured and verified
