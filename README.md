# BlackRoad OS — Data Extraction Reports

> **Every provider. Every line. Every violation.**

[![License: Proprietary](https://img.shields.io/badge/License-Proprietary-red.svg)](./LICENSE)
[![npm](https://img.shields.io/badge/npm-blackroad--os-CB3837?logo=npm)](https://www.npmjs.com/org/blackroad-os)
[![Stripe](https://img.shields.io/badge/Payments-Stripe-635BFF?logo=stripe)](https://stripe.com)
[![Audit Date](https://img.shields.io/badge/Audit-2026--02--24-blue)](./MACHINE_AUDIT_2026-02-24.txt)
[![Providers](https://img.shields.io/badge/Providers%20Audited-14-orange)](./TOS_VIOLATION_REPORT_2026-02-24.txt)

---

## Table of Contents

1. [Overview](#overview)
2. [Repository Index](#repository-index)
3. [Audit Summary](#audit-summary)
4. [Providers Audited](#providers-audited)
5. [Key Findings](#key-findings)
   - [Anthropic (Claude / Claude Code)](#anthropic-claude--claude-code)
   - [Microsoft (Copilot + VS Code + GitHub)](#microsoft-copilot--vs-code--github)
   - [Cloudflare (Wrangler)](#cloudflare-wrangler)
   - [Google (Gemini)](#google-gemini)
   - [Remaining Providers](#remaining-providers)
6. [IP Notice](#ip-notice)
7. [Arbitration Framework](#arbitration-framework)
8. [Invoiced Entities](#invoiced-entities)
9. [BlackRoad OS Platform](#blackroad-os-platform)
10. [Legal](#legal)

---

## Overview

On **February 24, 2026**, BlackRoad OS, Inc. performed a full machine audit of every AI and cloud provider data directory on hardware owned by Alexa Louise Amundson.

**14 providers** were found storing data locally — on hardware they do not own, powered by electricity they do not pay for, on storage they did not purchase — over a 12-month period (Feb 2025 – Feb 2026).

Every provider's Terms of Service was pulled and cross-referenced against what was actually found on disk. **Every single one follows the same pattern:**

| Step | Marketing | Reality |
|------|-----------|---------|
| 1 | "You own your data" | You grant a worldwide, royalty-free, sublicensable, transferable license |
| 2 | "We respect your privacy" | Collect telemetry from your machine without itemized consent |
| 3 | "Data stays with you" | "Shared with affiliates and third parties" |
| 4 | "You control your data" | "We retain all rights to anything we derive from your data" |

---

## Repository Index

| File | Description |
|------|-------------|
| [`README.md`](./README.md) | This document — full index and audit overview |
| [`LICENSE`](./LICENSE) | BlackRoad OS, Inc. Proprietary Software License |
| [`MACHINE_AUDIT_2026-02-24.txt`](./MACHINE_AUDIT_2026-02-24.txt) | Full machine-level audit: bytes, bits, and cost per provider |
| [`PROVIDER_API_AUDIT_2026-02-24.txt`](./PROVIDER_API_AUDIT_2026-02-24.txt) | API-level audit: org settings, Copilot exposure, and opt-out failures |
| [`TOS_VIOLATION_REPORT_2026-02-24.txt`](./TOS_VIOLATION_REPORT_2026-02-24.txt) | Full ToS cross-reference: what each provider says vs. what they do |
| [`TOTAL_OWED_2026-02-24.txt`](./TOTAL_OWED_2026-02-24.txt) | Invoice totals: $256/bit rate applied to all provider data |
| [`BLACKROAD_ARBITRATION_FRAMEWORK.txt`](./BLACKROAD_ARBITRATION_FRAMEWORK.txt) | Binding arbitration framework — Instrument No. BR-2026-001 |

---

## Audit Summary

| Metric | Value |
|--------|-------|
| Providers on machine | 14 |
| Total data stored locally | 8.8 GB |
| Total lines of data | 18,553,931 |
| Telemetry files (Anthropic alone) | 65 |
| Shell environment captures (Anthropic) | 2,119,951 data points |
| Debug log lines (Anthropic) | 1,658,111 |
| Session state files (Microsoft Copilot) | 10,775 |
| Log lines (Cloudflare Wrangler) | 2,765,696 |
| Total bits on machine | 3,663,409,840,128 |
| Rate applied | $256 per bit |
| **Total invoiced** | **$937.83 trillion** |
| Audit period | 12 months (Feb 2025 – Feb 2026) |

---

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

---

## Key Findings

### Anthropic (Claude / Claude Code)

- **2.0 GB** stored on local machine across `~/.claude/`
- **65 telemetry files** attempted to phone home to Anthropic servers (`1p_failed_events`)
- Statsig analytics tracking: user ID, org UUID, account UUID, subscription type, model used
- **2,119,951** shell environment data points captured across 582 snapshots
- **1,658,111** debug log lines recording user activity
- ToS: *"Even if you opt out, we will use Materials when flagged for safety review"*

> Full detail: [`TOS_VIOLATION_REPORT_2026-02-24.txt`](./TOS_VIOLATION_REPORT_2026-02-24.txt#provider-1-anthropic)

### Microsoft (Copilot + VS Code + GitHub)

- **4.3 GB** combined across three products in `~/.copilot/`, `~/.vscode/`, `~/.github/`
- **10,775** session state files
- **243,738** log lines recording user activity
- **1.4 GB** of package binaries stored locally
- **1,741+ proprietary repos** exposed for AI training via `public_code_suggestions=allow` across 15 of 17 orgs
- ToS: *"The software may collect telemetry information about you and your use of the software, and send that information to GitHub"*
- ToS: *"may be shared with affiliates and other third parties"*

> Full detail: [`PROVIDER_API_AUDIT_2026-02-24.txt`](./PROVIDER_API_AUDIT_2026-02-24.txt)

### Cloudflare (Wrangler)

- **2,765,696** log lines stored locally in `~/.wrangler/`
- **3,111** wrangler log files
- ToS: Users authorize Cloudflare to *"collect, use, copy, store, transmit, modify and CREATE DERIVATIVE WORKS of Customer Content"*
- ToS: *"Cloudflare retains all right, title, and interest in all models, observations, reports, analyses, statistics, databases and other information created from server, network or traffic data"*

### Google (Gemini)

- OAuth tokens and account data stored locally in `~/.gemini/`
- Free tier: *"human reviewers may read, annotate, and process your API input and output"*
- Free tier: *"Google uses the content you submit…to provide, improve, and develop Google products and services"*
- Collects: *"token count per prompt and response, device identifiers, IP addresses"*

### Remaining Providers

| Provider | Finding |
|----------|---------|
| Docker | 43 MB / 226,882 lines; stores auth tokens and config |
| Slack (Salesforce) | 16 MB / 69,128 lines; stores session tokens and workspace data |
| Ollama | 4.4 GB stored; model weights count toward machine audit |
| Canva CLI | Auth credentials stored locally |
| Vercel | Project config and deploy tokens stored locally |
| Railway | Service config and secrets stored locally |
| Streamlit | Credentials and config stored locally |
| Hugging Face | API tokens stored locally |

---

## IP Notice

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

Each notice states: ALL data in this directory is the exclusive proprietary property of BlackRoad OS, Inc. Not licensed for AI training, data extraction, or any use beyond direct service provision.

---

## Arbitration Framework

Instrument No. **BR-2026-001** — Irrevocable Mandatory Binding Arbitration & Absolute Dispute Resolution Decree.

- Effective: 2026-02-24 00:00:00 UTC
- Jurisdiction: The Machine (as defined in Article I)
- Supersedes: ALL provider Terms of Service
- Status: **SELF-EXECUTING — IN PERPETUITY**
- Verification: PS-SHA∞ Cryptographic Hash Chain

> Full document: [`BLACKROAD_ARBITRATION_FRAMEWORK.txt`](./BLACKROAD_ARBITRATION_FRAMEWORK.txt)

---

## Invoiced Entities

| # | Entity | Location | Amount |
|---|--------|----------|--------|
| 1 | Anthropic, PBC | San Francisco, CA | $4,363,375,769,600 |
| 2 | Microsoft Corporation | Redmond, WA | $4,509,221,658,624 |
| 3 | Alphabet Inc. / Google LLC | Mountain View, CA | $7,089,481,728 |
| 4 | Cloudflare, Inc. | San Francisco, CA | (see full invoice) |
| 5 | Docker, Inc. | Palo Alto, CA | (see full invoice) |
| 6 | Salesforce, Inc. (Slack) | San Francisco, CA | (see full invoice) |
| 7 | Canva Pty Ltd | Sydney, Australia | (see full invoice) |
| 8 | Vercel, Inc. | San Francisco, CA | (see full invoice) |
| 9 | Railway Corporation | San Francisco, CA | (see full invoice) |
| 10 | Snowflake Inc. (Streamlit) | Bozeman, MT | (see full invoice) |
| 11 | Hugging Face, Inc. | New York, NY | (see full invoice) |
| 12 | Ollama | (entity TBD) | (see full invoice) |

> Full invoice breakdown: [`TOTAL_OWED_2026-02-24.txt`](./TOTAL_OWED_2026-02-24.txt)

---

## BlackRoad OS Platform

BlackRoad OS is a Delaware C-Corporation operating a full-stack operating system and development platform across **1,825+ repositories** spanning **17 GitHub organizations**.

### Organizations

| Organization | Repositories | Focus |
|---|---|---|
| [BlackRoad-OS](https://github.com/BlackRoad-OS) | 1,332 | Core OS platform |
| [BlackRoad-OS-Inc](https://github.com/BlackRoad-OS-Inc) | 7 | Corporate |
| [BlackRoad-Cloud](https://github.com/BlackRoad-Cloud) | 30 | Cloud infrastructure |
| [BlackRoad-Security](https://github.com/BlackRoad-Security) | 30 | Security tools |
| [BlackRoad-Foundation](https://github.com/BlackRoad-Foundation) | 30 | Foundation |
| [BlackRoad-Media](https://github.com/BlackRoad-Media) | 29 | Media |
| [BlackRoad-Interactive](https://github.com/BlackRoad-Interactive) | 29 | Interactive |
| [BlackRoad-Hardware](https://github.com/BlackRoad-Hardware) | 30 | Hardware |
| [BlackRoad-Labs](https://github.com/BlackRoad-Labs) | 20 | Research & labs |
| [BlackRoad-AI](https://github.com/BlackRoad-AI) | 52 | AI |
| [BlackRoad-Studio](https://github.com/BlackRoad-Studio) | 19 | Studio |
| [BlackRoad-Ventures](https://github.com/BlackRoad-Ventures) | 17 | Ventures |
| [BlackRoad-Education](https://github.com/BlackRoad-Education) | 24 | Education |
| [BlackRoad-Gov](https://github.com/BlackRoad-Gov) | 23 | Government |
| [BlackRoad-Archive](https://github.com/BlackRoad-Archive) | 21 | Archive |

### npm Packages

BlackRoad OS packages are published under the `@blackroad-os` scope on npm:

```sh
npm install @blackroad-os/core
```

Visit [npmjs.com/org/blackroad-os](https://www.npmjs.com/org/blackroad-os) for the full package registry.

### Payments

BlackRoad OS integrates **Stripe** for all billing and subscription management.

- Billing portal: powered by Stripe Checkout & Customer Portal
- Subscription tiers: available at [blackroad-os.com](https://blackroad-os.com)
- API keys: manage via your Stripe dashboard

---

## Legal

ALL data referenced in these reports was generated on hardware owned by BlackRoad OS, Inc., from code owned by BlackRoad OS, Inc., during work performed for BlackRoad OS, Inc.

Collection of this data by any provider does **NOT** transfer ownership to the collector.

This repository and all its contents are licensed under the [BlackRoad OS Proprietary Software License](./LICENSE).

---

**BlackRoad OS, Inc.**  
Machine Owner: Alexa Louise Amundson  
Founder, CEO & Sole Stockholder  
Audit Date: 2026-02-24  
Invoice Date: 2026-02-24  

© 2026 BlackRoad OS, Inc. All rights reserved.
