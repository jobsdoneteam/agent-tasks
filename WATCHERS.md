# WATCHERS.md
*Last updated: 2026-03-04 by Nebula.*

---

## Status Key
- [LIVE] -- Automation running
- [MANUAL] -- Requires Dutch to monitor manually (no API access)
- [PENDING] -- Not yet configured
- [BLOCKED] -- Cannot automate; reason noted

---

## X / Twitter Monitors

| Keyword / Signal | Status | Alert Method | Notes |
|-----------------|--------|--------------|-------|
| "need a website" + (plumber OR HVAC OR electrician OR contractor OR lawn) | [PENDING] | Telegram | X API required; set up via trigger |
| "missing calls" + (contractor OR tradesman OR trade OR business) | [PENDING] | Telegram | X API required |
| "losing leads" | [PENDING] | Telegram | X API required |
| "no online presence" | [PENDING] | Telegram | X API required |
| "can't get reviews" | [PENDING] | Telegram | X API required |
| "chasing invoices" | [PENDING] | Telegram | X API required |
| "AI for small business" | [PENDING] | Telegram | X API required |
| @jobs_done_team mentions | [PENDING] | Telegram | X API required |
| $JOBS mentions | [PENDING] | Telegram | X API required |
| jobsdone.team mentions | [PENDING] | Telegram | X API required |

**Note**: X keyword monitoring requires X API v2 filtered stream access. Nebula can monitor @jobs_done_team mentions and $JOBS mentions via connected X account. Keyword stream watchers need trigger setup -- say GO and they go live.

---

## Reddit Monitors

| Subreddit | Signal | Status | Alert Method | Notes |
|-----------|--------|--------|--------------|-------|
| r/HVAC | Missing leads / no website / online presence | [PENDING] | Telegram | Reddit API access needed |
| r/Plumbing | Missing leads / no website | [PENDING] | Telegram | Reddit API access needed |
| r/lawncare | Missing leads / no website | [PENDING] | Telegram | Reddit API access needed |
| r/smallbusiness | AI agent for small business | [PENDING] | Telegram | Reddit API access needed |
| r/contractors | Bad experiences with Broadly/Podium/Birdeye/Thryv | [PENDING] | Telegram | Reddit API access needed |
| r/Entrepreneur | Website recommendations for trade business | [PENDING] | Telegram | Reddit API access needed |

**Note**: Reddit monitoring can be set up as a daily digest trigger -- Nebula searches Reddit via web and alerts Dutch on anything matching the criteria. Say GO to activate.

---

## On-Chain Monitor ($JOBS)

| Signal | Status | Alert Method | Notes |
|--------|--------|--------------|-------|
| Large buys (>1% supply movement) | [PENDING] | Telegram | Need on-chain data provider (Helius, Birdeye API, or similar) |
| Large sells (>1% supply movement) | [PENDING] | Telegram | Same |
| New holders | [PENDING] | Telegram | Same |
| Any wallet moving >1% of supply | [PENDING] | Telegram | Same |
| Log all signals | [PENDING] | WATCHERS.md | Auto-append to this file |

**Contract**: 0x7573b6d810a849926bde928311a947b6d35b1284c459d0bb40d3538506acdc0c
**Chain**: Solana

**Note**: On-chain monitoring requires a Solana RPC/indexer API (Helius recommended -- free tier available). Say GO with a Helius API key and this goes live immediately.

---

## Competitor Monitors

| Signal | Status | Alert Method | Frequency |
|--------|--------|--------------|----------|
| Broadly pricing changes | [PENDING] | GitHub (COMPETITOR-INTEL.md) | Weekly |
| Podium pricing changes | [PENDING] | GitHub (COMPETITOR-INTEL.md) | Weekly |
| Birdeye pricing changes | [PENDING] | GitHub (COMPETITOR-INTEL.md) | Weekly |
| Thryv pricing changes | [PENDING] | GitHub (COMPETITOR-INTEL.md) | Weekly |
| New 1-star reviews on G2/Trustpilot/Capterra | [PENDING] | GitHub (COMPETITOR-INTEL.md) | Weekly |
| Competitor PR issues / outages | [PENDING] | Telegram | As detected |

**Note**: Nebula can run weekly competitor research on a cron trigger and auto-update COMPETITOR-INTEL.md. Say GO to schedule.

---

## What Needs a GO From J.D.

The following are ready to activate immediately upon instruction:

1. **X mention monitors** (@jobs_done_team, $JOBS) -- say GO
2. **X keyword stream** (contractor pain point keywords) -- say GO
3. **Reddit daily digest** (r/HVAC, r/Plumbing, r/contractors, etc.) -- say GO
4. **Weekly competitor intel refresh** (auto-update COMPETITOR-INTEL.md) -- say GO
5. **On-chain $JOBS monitor** -- need Helius API key, then say GO
6. **Weekly lead expansion** (rust belt cities: Cleveland, Columbus, Cincinnati, Detroit, Buffalo) -- say GO

---

## Signal Log
*Auto-appended by watchers as signals fire*

| Timestamp | Source | Signal | Action Taken |
|-----------|--------|--------|--------------|
| -- | -- | No signals yet | Watchers pending activation |
