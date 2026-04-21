<!-- Wide cinematic hero banner — agentic AI across multi-cloud infrastructure -->
<p align="center">
  <a href="https://www.devopsarg.com">
    <img src="assets/hero-banner.webp" alt="DevOps ARG — autonomous AI agents flowing across multi-cloud infrastructure, gorilla badge in the foreground" width="100%" />
  </a>
</p>

<h1 align="center">We build autonomous AI agents that run your infrastructure</h1>

<p align="center">
  <em>Infrastructure that fixes itself. MTTR from 45 minutes to 3. Deploys on Fridays.</em>
</p>

<p align="center">
  <a href="https://www.devopsarg.com">
    <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=22&pause=1200&color=C9A227&center=true&vCenter=true&width=880&lines=Agentic+AI+for+infrastructure+that+fixes+itself;Autonomous+agents+that+detect%2C+diagnose+%26+remediate;MTTR+from+45+min+to+3+min+%E2%80%94+agents+do+the+work;Cloud-agnostic+%C2%B7+AWS+%C2%B7+Azure+%C2%B7+GCP+%C2%B7+Cloudflare;%242.1M%2B+cloud+costs+saved+across+client+engagements;We+deploy+on+Fridays.+Always+build.+Never+burn." alt="Tagline animado" />
  </a>
</p>

<p align="center">
  <a href="https://www.devopsarg.com"><img src="https://img.shields.io/badge/Website-devopsarg.com-0D1B3E?style=for-the-badge&labelColor=C9A227" /></a>
  <a href="https://www.devopsarg.com/en/blog/"><img src="https://img.shields.io/badge/Field_Notes-Case_studies-0D1B3E?style=for-the-badge&labelColor=C9A227" /></a>
  <a href="mailto:hello@devopsarg.com"><img src="https://img.shields.io/badge/Email-hello@devopsarg.com-0D1B3E?style=for-the-badge&labelColor=C9A227" /></a>
  <img src="https://komarev.com/ghpvc/?username=devops-arg&color=C9A227&style=for-the-badge&label=PROFILE+VIEWS" />
</p>

<p align="center">
  <code>150+ projects shipped</code> · <code>$2.1M+ cloud costs saved</code> · <code>99.99% uptime delivered</code> · <code>~3 min avg MTTR</code> · <code>2,400+ incidents auto-resolved</code>
</p>

---

## 🤖 Agentic AI is the main act

We build **autonomous AI agents** that monitor, diagnose, and remediate infrastructure — without a human on the other end. Agents that write RCAs after an incident closes. Agents that flag oversized instances inside a Terraform PR. Deploy copilots that score release risk from the diff and historical rollback rate. Chat interfaces that replace Cost Explorer.

Humans govern policy. Machines do the rest.

### How we build agents (the stack)

| Layer | What it does | What we use |
|-------|--------------|-------------|
| **Reasoning** | Multi-round agentic loops with reflection — not single-shot prompts. The agent plans, calls tools, checks, re-plans, up to N rounds with a hard cap. | Claude · CrewAI · LangGraph |
| **Knowledge** | RAG over runbooks, postmortems, Slack threads, incident timelines, IaC modules. | Qdrant · pgvector · embeddings |
| **Observability** | Eyes and ears — agents need telemetry to reason. | OpenTelemetry · Prometheus · Grafana · Datadog |
| **Execution** | Concrete tools the agent calls: AWS/GCP/Azure APIs, `kubectl`, Terraform, GitHub Actions triggers. | boto3 · k8s SDK · IaC CLIs |
| **Guardrails** | Read-only IAM by construction, policy-as-code on every action, human-in-the-loop for destructive ops. | AWS managed policies · OPA · approval gates |

### The pattern behind every agent we ship

1. Dedicated **read-only identity** per agent — the setup script verifies writes are rejected before we proceed.
2. **Tool registry** with typed schemas — every capability is an explicit function with a description; the LLM picks from the list.
3. **Multi-round loop** with a reflection step asking *"do we have enough data?"* — catches half-baked answers before they reach the user.
4. **Mock/demo mode** — every agent ships with a fictional profile so you can pitch it without connecting a live account.
5. **Streaming trace panel** — the user sees each tool call, each result, each intermediate thought. No spinner theater.

---

## 🔥 Featured projects

<table>
  <tr>
    <td width="50%" valign="top">
      <h3>🧮 <a href="https://github.com/devops-arg/finops-agent">finops-agent</a></h3>
      <p><strong>Conversational FinOps agent.</strong> Chat with your AWS account in plain English. Multi-round reasoning with Claude, 15 tool handlers across Cost Explorer / EC2 / RDS / EKS / Cost Optimization Hub. Ships with a <code>create-read-only.sh</code> that provisions a dedicated IAM user and <em>verifies writes are blocked</em>.</p>
      <p>
        <img src="https://img.shields.io/badge/Claude-D97757?style=flat-square&logo=anthropic&logoColor=white" />
        <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
        <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" />
        <img src="https://img.shields.io/badge/AWS-FF9900?style=flat-square&logo=amazon-aws&logoColor=white" />
        <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
      </p>
      <a href="https://github.com/devops-arg/finops-agent">
        <img src="https://github-readme-stats.vercel.app/api/pin/?username=devops-arg&repo=finops-agent&theme=midnight-purple&border_color=C9A227&title_color=C9A227&icon_color=C9A227" />
      </a>
      <p><a href="https://www.devopsarg.com/en/blog/ai-finops-chat-your-aws-account/">→ Read the case study</a></p>
    </td>
    <td width="50%" valign="top">
      <h3>🚧 Extracting next</h3>
      <p>These are running in client engagements — extracting and hardening into public repos.</p>
      <ul>
        <li><strong>sre-incident-copilot</strong> — RAG-powered SRE agent with Qdrant. Ask <em>"auth-service is timing out, what did we do last time?"</em> and it pulls from indexed postmortems, runbooks, and Datadog metrics to draft a remediation plan. Case study: <a href="https://www.devopsarg.com/en/blog/rag-powered-sre-agent-gaming-company/">gaming company that cut MTTR 12x</a>.</li>
        <li><strong>ai-incident-responder</strong> — Claude-driven agent that reads PagerDuty alerts + logs + recent deploys and drafts the RCA before the human wakes up. Case study: <a href="https://www.devopsarg.com/en/blog/building-ai-incident-responder-with-claude/">2,400+ incidents auto-resolved</a>.</li>
        <li><strong>deploy-risk-scorer</strong> — pre-merge copilot that scores deployment risk from the PR diff, historical rollback rate, and blast radius.</li>
        <li><strong>cost-anomaly-explainer</strong> — correlates cost spikes with CloudTrail events to explain <em>why</em> your bill jumped.</li>
      </ul>
      <p>⭐ Watch the org to get notified as each repo ships.</p>
    </td>
  </tr>
</table>

---

## ☁️ Cloud-agnostic, not cloud-locked

Our agents and platforms are designed to run wherever your workloads live. We don't evangelize a single cloud — we match architecture to the problem.

<p align="center">
  <img src="https://img.shields.io/badge/AWS-FF9900?style=for-the-badge&logo=amazon-aws&logoColor=white" />
  <img src="https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoft-azure&logoColor=white" />
  <img src="https://img.shields.io/badge/GCP-4285F4?style=for-the-badge&logo=google-cloud&logoColor=white" />
  <img src="https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=cloudflare&logoColor=white" />
</p>

### AI & agent toolchain

<p align="center">
  <img src="https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logo=anthropic&logoColor=white" />
  <img src="https://img.shields.io/badge/CrewAI-000000?style=for-the-badge" />
  <img src="https://img.shields.io/badge/LangGraph-1C3C3C?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Qdrant-DC382D?style=for-the-badge" />
  <img src="https://img.shields.io/badge/pgvector-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenTelemetry-000000?style=for-the-badge&logo=opentelemetry&logoColor=white" />
</p>

### Platform & cloud-native stack

<p align="center">
  <img src="https://skillicons.dev/icons?i=kubernetes,docker,terraform,python,go,bash,postgres,redis,grafana,prometheus,nginx,linux&perline=12" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Argo_CD-EF7B4D?style=flat-square&logo=argo&logoColor=white" />
  <img src="https://img.shields.io/badge/Flux-5468FF?style=flat-square&logo=flux&logoColor=white" />
  <img src="https://img.shields.io/badge/Karpenter-232F3E?style=flat-square&logo=amazon-aws&logoColor=FF9900" />
  <img src="https://img.shields.io/badge/WASM-654FF0?style=flat-square&logo=webassembly&logoColor=white" />
  <img src="https://img.shields.io/badge/OpenTofu-FFDA18?style=flat-square&logo=opentofu&logoColor=black" />
  <img src="https://img.shields.io/badge/Pulumi-8A3391?style=flat-square&logo=pulumi&logoColor=white" />
  <img src="https://img.shields.io/badge/Backstage-9BF0E1?style=flat-square&logo=backstage&logoColor=black" />
  <img src="https://img.shields.io/badge/Falco-00AEC7?style=flat-square" />
  <img src="https://img.shields.io/badge/eBPF-F8D12F?style=flat-square&logoColor=black" />
  <img src="https://img.shields.io/badge/Sigstore-1A1A1A?style=flat-square" />
  <img src="https://img.shields.io/badge/OPA-7B42BC?style=flat-square&logo=openpolicyagent&logoColor=white" />
</p>

---

## 🏗 Everything else we do

Once the AI layer is in, it needs a real platform underneath. Here's the rest of what we ship:

- **Platform engineering** — Internal Developer Platforms that turn ticket-based ops into self-service golden paths. Developers click "deploy," not "open a Jira." IaC with OpenTofu, Pulumi, or Crossplane — whatever fits.
- **Kubernetes & GitOps** — self-healing clusters with Karpenter, WASM workloads at the edge, GitOps with ArgoCD + Flux. Managed clusters serving 50M+ requests/day.
- **Cloud architecture & edge** — multi-region, multi-cloud, edge-native. Event-driven on Cloudflare Workers, AWS Lambda, Azure Functions. Active-active across continents, sub-100ms latency globally.
- **DevSecOps & Zero Trust** — Sigstore for supply chain, Falco + eBPF for runtime, policy-as-code in every PR. SOC 2, ISO 27001, PCI-DSS automated. 14K+ threats blocked, 890 CVEs auto-patched across engagements.
- **FinOps & GreenOps** — real-time cost impact before every deploy. RI/SP optimization, spot orchestration, carbon-aware scheduling. **$2.1M+ saved** — your CFO becomes your biggest fan.

---

## 📚 Case studies from the field

Every post is a real engagement with real numbers. No listicles. Real YAML, real tradeoffs, honest "what we'd do differently" sections.

| Post | What happened |
|------|---------------|
| 🤖 [**We shipped an AI FinOps agent (open source)**](https://www.devopsarg.com/en/blog/ai-finops-chat-your-aws-account/) | Built a Claude-powered chat interface for AWS costs so engineers stop ignoring Cost Explorer. Live at [finops-agent](https://github.com/devops-arg/finops-agent). |
| 🎮 [**RAG-powered SRE agent**](https://www.devopsarg.com/en/blog/rag-powered-sre-agent-gaming-company/) | Gaming platform's incident copilot — Qdrant + Claude + Datadog RAG. MTTR cut 12x. |
| 🔔 [**Building an AI incident responder**](https://www.devopsarg.com/en/blog/building-ai-incident-responder-with-claude/) | Claude-driven agent that reads alerts, logs, and deploys to draft RCAs autonomously. 2,400+ incidents. |
| 🔎 [**OpenTelemetry for fintech**](https://www.devopsarg.com/en/blog/opentelemetry-distributed-tracing-fintech/) | Distributed tracing across a payments pipeline. 45-minute incident hunts → 4-minute root cause. |
| 📰 [**Predictive pre-scaling for breaking news**](https://www.devopsarg.com/en/blog/predictive-prescaling-kubernetes-breaking-news/) | News site that stopped melting at 9 AM — KEDA + Prophet forecasting. |
| 🔐 [**Blockchain security audit**](https://www.devopsarg.com/en/blog/blockchain-startup-security-audit-case-study/) | 72 findings, 3 criticals in a DeFi startup. IAM cleanup in 2 weeks. |
| 💸 [**Karpenter spot + scale-to-zero**](https://www.devopsarg.com/en/blog/karpenter-spot-scale-to-zero/) | 68% compute savings with a single node pool. Zero developer friction. |

All posts available in [English](https://www.devopsarg.com/en/blog/) and [Castellano](https://www.devopsarg.com/es/blog/).

---

## 📊 GitHub stats

<p align="center">
  <img height="180" src="https://github-readme-stats.vercel.app/api?username=devops-arg&show_icons=true&theme=midnight-purple&border_color=C9A227&title_color=C9A227&icon_color=C9A227&include_all_commits=true&count_private=false" />
  <img height="180" src="https://github-readme-stats.vercel.app/api/top-langs/?username=devops-arg&layout=compact&theme=midnight-purple&border_color=C9A227&title_color=C9A227&langs_count=8" />
</p>

---

## 🤝 Work with us

We take **a few engagements per quarter** — 4–12 week platform sprints, fractional CTO / platform-lead, or ongoing SRE retainers. **The initial infrastructure assessment is free** — no strings.

<p align="center">
  <a href="https://www.devopsarg.com/#contact"><img src="https://img.shields.io/badge/🚀_Free_assessment-Book_a_call-C9A227?style=for-the-badge&labelColor=0D1B3E" /></a>
  <a href="https://www.devopsarg.com"><img src="https://img.shields.io/badge/💬_Chat_with_deploy--bot-devopsarg.com-C9A227?style=for-the-badge&labelColor=0D1B3E" /></a>
  <a href="mailto:hello@devopsarg.com"><img src="https://img.shields.io/badge/✉️_Email-hello@devopsarg.com-C9A227?style=for-the-badge&labelColor=0D1B3E" /></a>
</p>

---

<p align="center">
  <img src="assets/logo-small.webp" alt="DevOps ARG badge" width="96" />
  <br/>
  <sub>Based in Buenos Aires. Working with teams across the Americas and EU.</sub>
  <br/>
  <sub><strong>Always build. Never burn.</strong></sub>
</p>
