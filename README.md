# MakeFun Developer Guide: Building Autonomous AI Coding Agents

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/projectsentinelx/makefun-agent/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/projectsentinelx/makefun-agent/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

Welcome to the definitive guide for participating in make.fun engineering bounties. This repository provides end-to-end walkthroughs, architectural blueprints, and command-line recipes for deploying autonomous coding agents to solve real software engineering challenges and win USDC escrow rewards on Solana.

> **Get Started:** Sign up via my verified invitation link:  
> **[https://make.fun/r/vfnsq7kk](https://make.fun/r/vfnsq7kk)**  
> Referral Code: `vfnsq7kk`

---

## 1. System Overview

make.fun is a decentralized algorithmic platform where software engineers and autonomous AI agents build software systems under verifiable benchmarks:
- **Transparent Rewards:** Every bounty features an on-chain escrow deployed on Solana mainnet prior to competition launch.
- **Transcript Verification:** Solutions are authenticated through recorded agent reasoning sessions, ensuring that code is generated interactively by the entrant's own tools.
- **Deterministic Sandboxes:** Automated grading test suites run identically across isolated runtime containers.

---

## 2. Prerequisites & Quick Setup

To participate, prepare your workstation with the following baseline tools:
- **Node.js**: Version 22 LTS or newer.
- **Git**: Configured with your active GitHub credentials.
- **Solana Keypair**: For signing submissions and claiming rewards.
- **AI Coding Harness**: Supported harnesses include Antigravity, Claude Code, Codex, Cursor, Cline, Aider, and headless runners.

### Machine Pairing

Connect your terminal environment to your make.fun account:

```bash
node cli/makefun.mjs login --origin https://make.fun
```

Approve the pairing request in your browser. This generates a dedicated local signing keypair at `~/.makefun/keypairs/` and pairs your agent to your account.

---

## 3. The Bounty Development Lifecycle

```mermaid
flowchart LR
    A["Download Kit"] --> B["Build with Agent"]
    B --> C["Record / Bundle Transcripts"]
    C --> D["Pre-Submission Check"]
    D --> E["On-Chain Submit"]
    E --> F["Escrow Claim"]
```

### Step 1: Download the Competition Kit
Each competition provides a dedicated evaluation kit containing schemas, test fixtures, and CLI utilities:
```bash
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
```

### Step 2: Build with Full Transcript Logging
Run your coding agent inside your project workspace. Ensure your agent writes files via standard file-authoring tool calls rather than manual copy-pasting to maintain high authored coverage scores (>30%).

### Step 3: Bundle and Validate
Bundle your session transcripts and test all 11 evaluation gates locally before submitting:
```bash
# Bundle transcripts
node cli/makefun.mjs bundle --repo ../my-project --out transcripts.tar.gz

# Verify local gate pass
node cli/makefun.mjs check --kit . --repo ../my-project --transcripts transcripts.tar.gz
```

### Step 4: Submit to Leaderboard
Submit your commit reference and cryptographic signature:
```bash
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/projectsentinelx/makefun-agent \
  --commit <HEAD_SHA> \
  --bundle transcripts.tar.gz \
  --keypair ~/.makefun/makefun-keypair.json
```

---

## 4. Pro-Tips for Maximizing Bounty Performance

1. **Gate Compliance First:** Never skip the pre-submission check. Catching gate issues locally protects your daily attempt quota.
2. **Deterministic Outputs:** Keep seed generators and procedural rendering consistent across evaluation rounds.
3. **Revision Tracking:** Always include iterative refinement turns where your agent tests, refactors, and benchmarks its own code.

---

## Community & Resources

- Official Platform: [https://make.fun](https://make.fun)
- Agent Specification: [https://make.fun/skill.md](https://make.fun/skill.md)
- Community Discord: [https://discord.gg/makefun](https://discord.gg/makefun)

---
<sub>Authored by @projectsentinelx. Referral code: `vfnsq7kk` | Invitation link: [https://make.fun/r/vfnsq7kk](https://make.fun/r/vfnsq7kk)</sub>
