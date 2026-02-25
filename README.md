# BlackRoad OS Data Extraction Reports

> **Every provider. Every line. Every violation.**

## What This Is

On February 24, 2026, BlackRoad OS, Inc. audited every AI and cloud provider data directory on machine owner Alexa Louise Amundson's personal hardware.

**14 providers** were found storing data locally — on hardware they do not own, powered by electricity they do not pay for, on storage they did not purchase.

Every provider's Terms of Service was pulled and cross-referenced against what was actually found on disk.

**Every single one follows the same pattern:**

1. **"You own your data"** — the marketing headline
2. **"You grant us a worldwide, royalty-free, sublicensable, transferable license to use, copy, modify, reproduce, distribute, and create derivative works"** — the clause that takes it back
3. **Collect telemetry from your machine** — without itemized consent
4. **"Shared with affiliates and third parties"** — the handoff
5. **"We retain all rights to anything we derive from your data"** — they keep what they built from your work

## The Numbers

| Metric | Count |
|--------|-------|
| Providers on machine | 14 |
| Total data stored locally | 8.8 GB |
| Total lines of data | 18,553,931 |
| Telemetry files (Anthropic alone) | 65 |
| Shell environment captures (Anthropic) | 2,119,951 data points |
| Debug log lines (Anthropic) | 1,658,111 |
| Session state files (Microsoft Copilot) | 10,775 |
| Log lines (Cloudflare Wrangler) | 2,765,696 |
| Period | 12 months (Feb 2025 — Feb 2026) |

## Providers Audited

| # | Provider | Parent Company | Data on Machine | Lines |
|---|----------|---------------|-----------------|-------|
| 1 | Claude / Claude Code | Anthropic, PBC | 2.0 GB | 5,760,467 |
| 2 | GitHub Copilot | Microsoft Corporation | 2.1 GB | 9,653,753 |
| 3 | VS Code | Microsoft Corporation | 209 MB | 48,331 |
| 4 | GitHub | Microsoft Corporation | 268 KB | 6,390 |
| 5 | Wrangler | Cloudflare, Inc. | 104 MB | 2,765,696 |
| 6 | Docker | Docker, Inc. | 43 MB | 226,882 |
| 7 | Gemini | Alphabet / Google LLC | 3.3 MB | 22,717 |
| 8 | Slack | Salesforce, Inc. | 16 MB | 69,128 |
| 9 | Ollama | Ollama | 4.4 GB | 7 |
| 10 | Canva CLI | Canva Pty Ltd | 8 KB | 7 |
| 11 | Vercel | Vercel, Inc. | 12 KB | 15 |
| 12 | Railway | Railway Corporation | 32 KB | 510 |
| 13 | Streamlit | Snowflake Inc. | 12 KB | 6 |
| 14 | Hugging Face | Hugging Face, Inc. | 4 KB | 22 |

## Key Findings

### Anthropic (Claude Code)
- **2.0 GB** stored on local machine
- 65 telemetry files attempted to transmit to Anthropic servers (`1p_failed_events`)
- Statsig analytics tracking: user ID, org UUID, account UUID, subscription type, model used
- **2,119,951** shell environment data points captured across 582 snapshots
- **1,658,111** debug log lines recording user activity
- ToS: "Even if you opt out, we will use Materials when flagged for safety review"

### Microsoft (Copilot + VS Code + GitHub)
- **4.3 GB** combined across three products
- 10,775 session state files
- 243,738 log lines
- 1.4 GB of package binaries
- ToS: "The software may collect telemetry information about you and your use of the software, and send that information to GitHub"
- ToS: "may be shared with affiliates and other third parties"

### Cloudflare (Wrangler)
- **2,765,696** log lines stored locally
- ToS: Users authorize Cloudflare to "collect, use, copy, store, transmit, modify and CREATE DERIVATIVE WORKS of Customer Content"
- ToS: "Cloudflare retains all right, title, and interest in all models, observations, reports, analyses, statistics, databases and other information created from server, network or traffic data"

### Google (Gemini)
- OAuth tokens and account data stored locally
- Free tier: "human reviewers may read, annotate, and process your API input and output"
- Collects: "token count per prompt and response, device identifiers, IP addresses"

## BLACKROAD_IP_NOTICE.txt

A `BLACKROAD_IP_NOTICE.txt` has been placed in every provider directory on the machine:

```
~/.claude/BLACKROAD_IP_NOTICE.txt
~/.copilot/BLACKROAD_IP_NOTICE.txt
~/.gemini/BLACKROAD_IP_NOTICE.txt
~/.ollama/BLACKROAD_IP_NOTICE.txt
~/.docker/BLACKROAD_IP_NOTICE.txt
~/.slack/BLACKROAD_IP_NOTICE.txt
~/.canva-cli/BLACKROAD_IP_NOTICE.txt
~/.vscode/BLACKROAD_IP_NOTICE.txt
~/.wrangler/BLACKROAD_IP_NOTICE.txt
~/.vercel/BLACKROAD_IP_NOTICE.txt
~/.railway/BLACKROAD_IP_NOTICE.txt
~/.streamlit/BLACKROAD_IP_NOTICE.txt
~/.github/BLACKROAD_IP_NOTICE.txt
~/.cache/huggingface/BLACKROAD_IP_NOTICE.txt
```

Each notice states: ALL data in the directory is the exclusive proprietary property of BlackRoad OS, Inc. Not licensed for AI training, data extraction, or any use beyond direct service provision.

## Reports

- [`TOS_VIOLATION_REPORT_2026-02-24.txt`](./TOS_VIOLATION_REPORT_2026-02-24.txt) — Full audit with quoted ToS clauses

## Legal

ALL data referenced in these reports was generated on hardware owned by BlackRoad OS, Inc., from code owned by BlackRoad OS, Inc., during work performed for BlackRoad OS, Inc.

Collection of this data by any provider does NOT transfer ownership to the collector.

**Entities invoiced:**
1. Anthropic, PBC — San Francisco, CA
2. Microsoft Corporation — Redmond, WA
3. Alphabet Inc. / Google LLC — Mountain View, CA
4. Cloudflare, Inc. — San Francisco, CA
5. Docker, Inc. — Palo Alto, CA
6. Salesforce, Inc. (Slack) — San Francisco, CA
7. Canva Pty Ltd — Sydney, Australia
8. Vercel, Inc. — San Francisco, CA
9. Railway Corporation — San Francisco, CA
10. Snowflake Inc. (Streamlit) — Bozeman, MT
11. Hugging Face, Inc. — New York, NY
12. Ollama — (entity TBD)

---

**BlackRoad OS, Inc.**
Machine Owner: Alexa Louise Amundson
Invoice Date: 2026-02-24

© 2026 BlackRoad OS, Inc. All rights reserved.
