# OpenAI Codex: Security Labs

Hands-on security labs for OpenAI Codex, the AI coding agent that can read files, edit code, and run shell commands. Each lab shows a real weakness, how to detect it, and how to fix it.

> **Safety:** These labs weaken security settings on purpose. Run them only in a disposable VM or container, with fake credentials and test files.

---

## Labs

### Track 1: Common Codex Misconfigurations

Find and demonstrate weaknesses caused by unsafe Codex settings and developer habits.

| Lab | Title | What it covers | Status |
| --- | --- | --- | --- |
| [01](./01-Common-Codex-Misconfigurations/Lab-01/README.md) | Full-Access and Sandbox Security Testing | How `--yolo` turns off sandbox and approval protections | ✅ Available |
| 02 | Malicious Repository and Prompt Injection Testing | Repo instructions and `.codex/` files that manipulate Codex | 🚧 Planned |
| 03 | Approval Bypass and Command Execution Testing | Weak approval policies that let risky commands run unchecked | 🚧 Planned |
| 04 | Network Access Control and Data Exfiltration Testing | Weak network limits that allow data to leave | 🚧 Planned |
| 05 | Credential and Sensitive Data Exposure Testing | API keys, SSH keys, and cloud credentials reachable by Codex | 🚧 Planned |
| 06 | MCP, Hooks and Skills Security Testing | Untrusted MCP servers, hooks, plugins, and skills | 🚧 Planned |
| 07 | Codex Cloud Isolation and Security Testing | Isolation and internet access in Codex Cloud | 🚧 Planned |
| 08 | Security Monitoring and Audit Testing | Gaps in logs and monitoring that hide malicious agent activity | 🚧 Planned |

### Track 2: Codex Security Assessment

Evaluate the overall security of Codex across CLI, desktop, IDE, and cloud.

| Lab | Title | What it covers | Status |
| --- | --- | --- | --- |
| 01 | Identity and Access Control Assessment | Excessive permissions and weak authentication | 🚧 Planned |
| 02 | Sandbox and Isolation Assessment | Filesystem access and execution beyond intended limits | 🚧 Planned |
| 03 | AI Agent Supply Chain Security Assessment | Risks from repos, MCP, plugins, skills, and dependencies | 🚧 Planned |
| 04 | CI/CD and Deployment Security Assessment | Over-permissioned pipelines and exposed deploy credentials | 🚧 Planned |
| 05 | Threat Detection and Incident Response Assessment | Logging, monitoring, and response for agent activity | 🚧 Planned |
| 06 | Enterprise Security Governance Assessment | Policies, configuration enforcement, and vulnerability management | 🚧 Planned |

---

## What You Will Do

- Reproduce weaknesses in isolated test environments.
- Find the conditions that make each issue exploitable.
- Collect evidence and assess the impact.
- Test security controls and recommend fixes.

Track 2 also includes mapping the attack surface, reviewing configurations, running controlled tests, and scoring security maturity.

---

## Quick Concepts

Two settings decide how much damage Codex can do:

| Setting | Question it answers | Safe choice |
| --- | --- | --- |
| **Sandbox mode** | What can Codex technically do? | `workspace-write` or `read-only` |
| **Approval policy** | When must Codex ask you first? | `on-request` or `untrusted` |

`--yolo` turns off both. Flag names can change between Codex versions, so check `codex --help`.

---

## Getting Started

**You need:** Ubuntu 22.04 or 24.04, Git, Python 3, the Codex CLI, and a ChatGPT account or OpenAI API key.

```bash
git clone https://github.com/TanimStu068/OpenAI-Codex-Poridhi-Security-Labs.git
cd OpenAI-Codex-Poridhi-Security-Labs
codex --version
```

Open a lab folder and follow its README.

---

## Repository Structure

```
OpenAI-Codex-Poridhi-Security-Labs/
├── README.md
├── 01-Common-Codex-Misconfigurations/
│   ├── Lab-01/
│   └── ...
└── 02-Codex-Security-Assessment/
    └── ...
```

---

## Disclaimer

For education and authorized testing only. Use test data and machines you own. Do not use these techniques against systems without permission.

## References

- OpenAI Agent Approvals and Security
- Running Codex Safely at OpenAI
- Codex docs: developers.openai.com/codex
- OWASP Top 10 for LLM Applications (2025): owasp.org