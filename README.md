# Cuts

**"Cursor for cloud infrastructure" because DevOps deserves better tooling too.**

[![Version](https://img.shields.io/github/v/release/cutsdotdev/Cuts?style=flat-square)](https://github.com/cutsdotdev/Cuts/releases)
[![Download for macOS](https://img.shields.io/badge/macOS-Download-black?style=flat-square&logo=apple)](https://github.com/cutsdotdev/Cuts/releases)
[![Download for Windows x64](https://img.shields.io/badge/Windows%20x64-Download-blue?style=flat-square&logo=windows)](https://github.com/cutsdotdev/Cuts/releases)
[![Download for Windows ARM64](https://img.shields.io/badge/Windows%20ARM64-Download-blue?style=flat-square&logo=windows)](https://github.com/cutsdotdev/Cuts/releases)
[![macOS Code Signed](https://img.shields.io/badge/macOS-Code%20Signed-success?style=flat-square&logo=apple)](#verify-macos-code-signing-and-notarization)
[![Windows Code Signed](https://img.shields.io/badge/Windows-Code%20Signed-success?style=flat-square&logo=windows)](#verify-windows-code-signing)
[![VirusTotal Scanned](https://img.shields.io/badge/VirusTotal-Scanned-success?style=flat-square&logo=virustotal)](#verify-virustotal-scans)

[![AWS](https://img.shields.io/badge/AWS-Integrated-orange?style=flat-square&logo=amazonaws)](#connecting-cloud-providers)
[![Azure](https://img.shields.io/badge/Azure-Integrated-0078D4?style=flat-square&logo=microsoftazure)](#connecting-cloud-providers)
[![GCP](https://img.shields.io/badge/GCP-Integrated-4285F4?style=flat-square&logo=googlecloud)](#connecting-cloud-providers)
[![Supabase](https://img.shields.io/badge/Supabase-Integrated-3ECF8E?style=flat-square&logo=supabase)](#connecting-cloud-providers)
[![Kubernetes (beta)](https://img.shields.io/badge/Kubernetes-Beta-326CE5?style=flat-square&logo=kubernetes)](#connecting-cloud-providers)

![Cuts demo](images/demo.gif)

---

## Quick Start

1. **Download** — [GitHub Releases](https://github.com/cutsdotdev/Cuts/releases) (macOS · Windows x64 · Windows ARM64) · Linux coming soon
2. **Connect** — Use the Quick Connect tab to pick profiles from your cloud providers and then watch your resources sync in seconds.

---

## Table of Contents

- [What is Cuts?](#what-is-cuts)
- [Features](#features)
  - [Resource Index](#resource-index)
  - [Console Talk](#console-talk)
  - [Scripts](#scripts)
  - [Dashboards](#dashboards)
  - [Stacks](#stacks)
  - [Knowledge (cloud only)](#knowledge-cloud-only)
- [Security](#security)
- [Connecting Cloud Providers](#connecting-cloud-providers)
- [AI Setup (BYOK)](#ai-setup-byok)
- [Verify Signatures and Scans](#verify-signatures-and-scans)
- [Links](#links)

---

## What is Cuts?

Cuts is a desktop app for anyone who manages cloud infrastructure. It connects to your AWS, GCP, Azure, GitHub, GitLab, Supabase, and Kubernetes (beta) accounts and gives you:

- A unified search across all connected accounts
- An AI assistant that sees your real, live resources. Ask complex questions or make quick adjustments (with risk assessments and explicit approval required).
- Create and share scripts and dashboards. You don't have to learn a new API because the CLI is the API.

Fully local. Your credentials stay on your machine. Bring your own AI API key.

---

## Features

### Resource Index

Unified search across all connected cloud accounts. Instant lookups.

**How to use it:**

1. Connect a cloud provider via Quick Connect.
2. Resources appear in the left pane as they're indexed.
3. Press `Cmd+P` (macOS) or `Ctrl+P` (Windows) to search. Type names, services, or even add your own personalized names and tags to resources.
4. Group related resources into Stacks, add additional links to resources, pin them, and more.

---

### Console Talk

AI chat that knows your live infrastructure. Ask questions in your native language and get real CLI commands back. Every non-query command requires your approval before it runs and gives you a clear risk assessment so that you understand just what will happen.

**How to use it:**

1. Go to **Settings → AI** and add your API key (OpenAI, Anthropic, or Google).
2. Open Console Talk from the sidebar.
3. Ask a question like _"Which Lambda functions in us-east-1 haven't been invoked in 30 days?"_
4. Review the suggested command. Approve or edit before execution.

Bring your own key (BYOK). Keys stay on your machine and go directly to the provider.

Example questions:

- _AWS Cloudfront has a flat pricing plan for distributions. Based on the last six months of usage is it worth switching any of my distributions over to flat rate pricing?_
- _Why can't @my-api-lambda access the internet? I think it's something to do with the VPN._
- _Which GCP Cloud Functions are using Python 3.7, and what steps do I need to take to upgrade them to a supported runtime?_
- _Help me run a security audit on this Azure account. Where should we start?_

Example mutations:

- _Throttle @my-api-lambda to 0 immediately_
- _Restart @my-gce-instance_
- _Add a Cloudwatch alarm to @my-dynamo-table for read/write throughput exceeding 1,000 requests per minute_

---

### Scripts

Build, test, and run operational scripts. Local execution with a run history.

**How to use it:**

1. Open the Scripts panel.
2. Write or paste a script. Use the AI chat to help.
3. Run it locally. Edit, iterate, save.

---

### Dashboards

Build real-time monitoring dashboards using CLI commands you already know. Seven card types: list (table), chart (line, bar, pie, scatter), stat, KPI, gauge, explainer, and mutation. Multi-cloud, side-by-side.

**How to use it:**

1. Create a new Dashboard.
2. Add cards backed by a CLI command (e.g., `aws cloudwatch get-metric-data`). Use the AI chat to help.
3. Pick a visualization type: list, chart, stat, KPI, gauge, explainer, or mutation.
4. Add actions to charts. Is the CPU usage higher than you want it to be? Restart the server with one click.

---

### Stacks

Group related resources into named collections. Your payment service's Lambda + RDS + Redis, in one view.

**How to use it:**

1. Create a new Stack from the Settings sidepanel.
2. Search for resources and then add them to as many stacks as you want.

---

### Knowledge (cloud only)

Team Q&A linked to actual resources. Someone asks _"Why is this Lambda set to a concurrency of 100?"_, answer once and the answer stays attached to that resource for everyone.

**How to use it:**

1. Open any resource and go to the Knowledge tab.
2. Ask or answer a question.
3. The answer is visible to every team member viewing that resource.

_Requires a cloud plan._

---

## Security

- Code Signed on Mac and Windows.
- VirusTotal Scans posted with every release.
- Provider credentials never leave your machine.
- Bring your own AI API keys and make AI API calls from your machine.
- Commands execute locally on your machine using your CLI permissions.
- Every destructive or mutating action requires explicit approval.
- No network requests to Cuts are made unless you pay for a cloud connected account.
- For cloud accounts, only resource IDs, account IDs, regions, and service types are stored in our database. We don't store your resource configuration or metadata.

For more details, see the [security documentation](https://cuts.dev/security).

---

## Connecting Cloud Providers

Open **Quick Connect** from the sidebar. Cuts discovers your local CLI profiles and credentials automatically.

| Provider   | Auth Method                                                                                                                          |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| AWS        | Local CLI profiles (`~/.aws`)                                                                                                        |
| GCP        | Local CLI profiles or service accounts                                                                                               |
| Azure      | Local CLI profiles or service principals                                                                                             |
| Supabase   | Local CLI profiles or personal access token                                                                                          |
| Kubernetes | (beta) Attach your AWS, GCP, and Azure clusters or connect with local kubectl context, a kubeconfig file, or a service account token |
| GitHub     | _coming soon to local workspace mode_                                                                                                |
| GitLab     | _coming soon to local workspace mode_                                                                                                |

---

## AI Setup (BYOK)

1. Go to **Settings → AI**.
2. Add your API key for OpenAI, Anthropic, or Google.

Keys are stored locally on your machine and sent directly to the provider's API. Cuts never proxies or stores your AI keys.

---

## Verify Signatures and Scans

### Verify Windows Code Signing

Run either command after downloading a Windows installer:

```powershell
Get-AuthenticodeSignature .\cuts-x64.exe | Format-List Status, SignerCertificate, TimeStamperCertificate
```

```powershell
signtool verify /pa /v .\cuts-x64.exe
```

You should see a valid Authenticode signature, a trusted certificate chain, and a trusted timestamp.

### Verify macOS Code Signing and Notarization

Run these checks for the macOS DMG installer you downloaded:

```bash
spctl -a -vv --type open cuts.dmg
xcrun stapler validate cuts.dmg
```

You should see Gatekeeper acceptance plus a valid notarization ticket.

### Verify VirusTotal Scans

1. Compute the SHA-256 hash for your downloaded file.
2. Compare it against the release notes checksum.
3. Open the matching VirusTotal report.

**macOS/Linux:**

```bash
shasum -a 256 cuts.dmg
```

**Windows (PowerShell):**

```powershell
Get-FileHash .\cuts-x64.exe -Algorithm SHA256
```

Use the resulting hash at:

`https://www.virustotal.com/gui/file/<sha256>`

---

## Links

[Website](https://cuts.dev) · [Integrations](https://cuts.dev/integrations) · [Issues](https://github.com/cutsdotdev/Cuts/issues)

---

_I built the tool I wish I had at work. I hope you find it useful and easy to use._
