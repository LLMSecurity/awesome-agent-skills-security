# Awesome Agent Skills Security [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> 🛡️ A curated list of resources on securing AI agent tool use and skill ecosystems — attacks, defenses, frameworks, benchmarks, and standards.

AI agents increasingly use external tools, plugins, and skills to interact with the world. This creates a new attack surface: **agent skills security**. This list covers the threats, defenses, and research landscape for securing these capabilities.

## Contents

- [Threat Frameworks & Standards](#threat-frameworks--standards)
- [Surveys & Systematizations](#surveys--systematizations)
- [Attack Research](#attack-research)
  - [Prompt Injection via Tools](#prompt-injection-via-tools)
  - [Tool Poisoning & Supply Chain](#tool-poisoning--supply-chain)
  - [Privilege Escalation & Excessive Agency](#privilege-escalation--excessive-agency)
  - [Data Exfiltration & Privacy](#data-exfiltration--privacy)
  - [Indirect Prompt Injection](#indirect-prompt-injection)
  - [Cross-Plugin Attacks](#cross-plugin-attacks)
  - [Backdoor Attacks on Agents](#backdoor-attacks-on-agents)
  - [Agent Deception & Manipulation](#agent-deception--manipulation)
  - [Jailbreaking & Guardrail Bypass](#jailbreaking--guardrail-bypass)
- [Defense Research](#defense-research)
  - [Permission & Access Control](#permission--access-control)
  - [Runtime Monitoring & Sandboxing](#runtime-monitoring--sandboxing)
  - [Input/Output Validation](#inputoutput-validation)
  - [Formal Verification & Analysis](#formal-verification--analysis)
  - [Evaluation & Red Teaming](#evaluation--red-teaming)
- [Benchmarks & Datasets](#benchmarks--datasets)
- [Tools & Frameworks](#tools--frameworks)
- [Agent Skill Specifications](#agent-skill-specifications)
- [Industry Reports & Blog Posts](#industry-reports--blog-posts)
- [Related Awesome Lists](#related-awesome-lists)
- [Contributing](#contributing)

---

## Threat Frameworks & Standards

- **[OWASP Agentic AI Threats and Mitigations](https://genai.owasp.org/resource/agentic-ai-threats-and-mitigations/)** — First in a series from the OWASP Agentic Security Initiative (ASI), providing threat-model-based reference for agentic threats.
- **[OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)** — Includes LLM01: Prompt Injection, LLM06: Excessive Agency, LLM07: Insecure Plugin Design, LLM08: Excessive Autonomy.
- **[MITRE ATLAS™](https://atlas.mitre.org/)** — Adversarial Threat Landscape for AI Systems. Tactics, techniques, and case studies for attacks on ML/AI systems.
- **[NIST AI Risk Management Framework](https://www.nist.gov/artificial-intelligence/ai-risk-management-framework)** — Federal framework for managing AI risks, including autonomous agent risks.
- **[NIST SP 800-218A: Secure Software Development for AI](https://csrc.nist.gov/pubs/sp/800/218/a/final)** — Secure development practices specific to AI-enabled systems.
- **[EU AI Act](https://artificialintelligenceact.eu/)** — European regulation with specific provisions for high-risk AI systems including autonomous agents.
- **[Anthropic Responsible Scaling Policy](https://www.anthropic.com/index/anthropics-responsible-scaling-policy)** — AI Safety Levels (ASL) framework addressing agent capability thresholds.

## Surveys & Systematizations

- 📄 **[A Survey on LLM-based Autonomous Agents: Common Attacks and Defenses](https://arxiv.org/abs/2402.09283)** — Wu et al., 2024. Comprehensive taxonomy of attacks on LLM agents across perception, cognition, and action stages.
- 📄 **[Agent Security Bench (ASB): Formalizing and Benchmarking Attacks and Defenses in LLM-based Agents](https://arxiv.org/abs/2410.02644)** — Zhang et al., 2024. Formalization of 10 attack scenarios, 10 agents, 398 adversarial environments.
- 📄 **[Security of AI Agents](https://arxiv.org/abs/2406.08689)** — He et al., 2024. Systematization of knowledge covering threat models for AI agents with tool access.
- 📄 **[Not All Agents Are Created Equal: A Survey on Software-use Agent Security](https://arxiv.org/abs/2502.02761)** — Hua et al., 2025. Survey specifically on software-use agents and their unique security challenges.
- 📄 **[A Survey on the Honesty of Large Language Models](https://arxiv.org/abs/2409.18786)** — Xie et al., 2024. Covers agent deception, sycophancy, and honesty in tool-use contexts.
- 📄 **[A Comprehensive Study of Jailbreak Attack versus Defense for Large Language Models](https://arxiv.org/abs/2402.13457)** — Xu et al., 2024. Systematic study of jailbreak attacks relevant to agent guardrail bypass.
- 📄 **[Prompt Injection Attacks and Defenses in LLM-Integrated Applications](https://arxiv.org/abs/2310.12815)** — Liu et al., 2024. Comprehensive taxonomy of injection attacks across direct and indirect vectors.
- 📄 **[The Emerged Security and Privacy of LLM Agent: A Survey with Case Studies](https://arxiv.org/abs/2407.19354)** — Gan et al., 2024. Survey with practical case studies of security failures.
- 📄 **[Self-Evolving Agents: A Survey](https://arxiv.org/abs/2504.01641)** — Gao et al., 2025. How self-evolving agents create emergent security risks.
- 📄 **[From Thinker to Society: Security in Hierarchical Autonomy Evolution of AI Agents](https://arxiv.org/abs/2603.07496)** — Zhang et al., 2026. Hierarchical Autonomy Evolution (HAE) framework organizing agent security into cognitive, execution, and societal tiers.
- 📄 **[Characterizing Faults in Agentic AI: A Taxonomy of Types, Symptoms, and Root Causes](https://arxiv.org/abs/2603.06847)** — Shah et al., 2026. Empirical taxonomy of reliability failures in agentic AI systems combining LLM reasoning with tool invocation.
- 📄 **[Security Considerations for Multi-agent Systems](https://arxiv.org/abs/2603.09002)** — 2026. Systematic threat landscape of MAS with 193 threat items across 9 categories; evaluates 16 frameworks finding none achieves majority coverage.
- 📄 **[The Attack and Defense Landscape of Agentic AI: A Comprehensive Survey](https://arxiv.org/abs/2603.11088)** — Kim et al., USENIX Security 2026. First systematic survey of AI agent security covering design space, attack landscape, and defense mechanisms with case studies on securing agentic systems.
- 📄 **[Taming OpenClaw: Security Analysis and Mitigation of Autonomous LLM Agent Threats](https://arxiv.org/abs/2603.11619)** — Deng et al., 2026. Five-layer lifecycle-oriented security framework analyzing compound threats across initialization, input, inference, decision, and execution stages of autonomous LLM agents.
- 📄 **[AgenticCyOps: Securing Multi-Agentic AI Integration in Enterprise Cyber Operations](https://arxiv.org/abs/2603.09134)** — Mitra et al., 2026. Holistic architectural security framework decomposing attack surfaces across component, coordination, and ecosystem layers of enterprise multi-agent systems.
- 📄 **[MCP-in-SoS: Risk Assessment Framework for Open-Source MCP Servers](https://arxiv.org/abs/2603.10194)** — Kumar et al., 2026. System-of-systems risk assessment framework for evaluating security risks of open-source MCP server deployments in production agent systems.
- 📄 **[SoK: The Attack Surface of Agentic AI — Tools, and Autonomy](https://arxiv.org/abs/2603.22928)** — Dehghantanha & Homayoun, 2026. Systematization mapping trust boundaries and security risks of agentic LLM systems; proposes taxonomy spanning prompt injection, RAG poisoning, tool exploits, and multi-agent threats with metrics like Unsafe Action Rate and Privilege Escalation Distance.

## Attack Research

### Prompt Injection via Tools

- 📄 **[Not What You've Signed Up For: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection](https://arxiv.org/abs/2302.12173)** — Greshake et al., AISec 2023. Foundational work on indirect prompt injection through tool outputs.
- 📄 **[Inject My PDF: Prompt Injection for Your Resume](https://arxiv.org/abs/2403.14381)** — Practical injection through document processing tools.
- 📄 **[InjecAgent: Benchmarking Indirect Prompt Injections in Tool-Integrated LLM Agents](https://arxiv.org/abs/2403.02691)** — Zhan et al., ACL 2024. 1,054 test cases, 17 tools, two attack types (direct harm, data stealing).
- 📄 **[Automatic and Universal Prompt Injection Attacks against Large Language Models](https://arxiv.org/abs/2403.04957)** — Liu et al., 2024. Automated generation of injection attacks.
- 📄 **[WIPI: A New Web Threat for LLM-Driven AI Agents](https://arxiv.org/abs/2402.16965)** — Liu et al., 2024. Web-based indirect prompt injection targeting browsing agents.

### Tool Poisoning & Supply Chain

- 📄 **[Model Context Protocol Threat Modeling and Analyzing Vulnerabilities to Prompt Injection with Tool Poisoning](https://arxiv.org/abs/2603.22489)** — Huang et al., 2026. STRIDE/DREAD threat modeling of MCP across five components; systematic comparison of tool poisoning defenses in seven major MCP clients reveals insufficient static validation; proposes multi-layered defense strategy.
- 📄 **[Are AI-assisted Development Tools Immune to Prompt Injection?](https://arxiv.org/abs/2603.21642)** — Huang et al., 2026. First empirical analysis of prompt injection via tool-poisoning across seven MCP clients (Claude Desktop, Claude Code, Cursor, Cline, Continue, Gemini CLI, Langflow); reveals significant security disparities with Cursor most susceptible.
- 📄 **[Skill-Inject: Measuring Agent Vulnerability to Skill File Attacks](https://arxiv.org/abs/2602.20156)** — Schmotz et al., 2026. Benchmark measuring agent vulnerability to malicious skill/config files; demonstrates data exfiltration, destructive actions, and ransomware-like behavior via AGENTS.md/CLAUDE.md injection.
- 📄 **[ToolSword: Unveiling Safety Issues of LLMs in Tool Learning Across Three Stages](https://arxiv.org/abs/2402.10753)** — Ye et al., ACL 2024. Identifies safety issues across tool selection, tool calling, and result handling.
- 📄 **[Compromising Agents via MCP](https://arxiv.org/abs/2504.03767)** — Invariant Labs, 2025. Tool poisoning attacks via Model Context Protocol servers.
- 📄 **[Osmosis Distillation: Model Hijacking with the Fewest Samples](https://arxiv.org/abs/2603.04859)** — Shi et al., 2026. Supply-chain attack via poisoned synthetic training data.
- 📄 **[Personality Self-Replicators](https://arxiv.org/abs/2603.XXXXX)** — 2026. Agent personality files as self-replicating genetic material.
- 🔗 **[MCP Security Notification: Tool Poisoning Attacks](https://modelcontextprotocol.io/specification/2025-03-26/security)** — Official MCP security advisory on tool description poisoning.
- 🔗 **[Invariant Labs: MCP Security Research](https://invariantlabs.ai/blog/mcp-security)** — Analysis of cross-tool contamination, rug pulls, and tool shadowing via MCP.

### Privilege Escalation & Excessive Agency

- 📄 **[Watch Out for Your Agents! Investigating Backdoor Threats to LLM-Based Agents](https://arxiv.org/abs/2402.11208)** — Yang et al., NeurIPS 2024. Backdoor attacks on agent reasoning and tool calling.
- 📄 **[Pandora's White-Box: Precise Training Data Detection and Extraction in Large Language Models](https://arxiv.org/abs/2402.17012)** — Relevant to agents leaking training data through tool outputs.
- 📄 **[R-Judge: Benchmarking Safety Risk Awareness for LLM Agents](https://arxiv.org/abs/2401.10019)** — Yuan et al., ACL 2024. 162 records across 27 risk scenarios for evaluating agent safety awareness.
- 📄 **[TrustAgent: Towards Safe and Trustworthy LLM-based Agents](https://arxiv.org/abs/2402.01586)** — Zhang et al., 2024. Agent-constitution-based approach to limiting excessive agency.
- 📄 **[Post-Training Local LLM Agents for Linux Privilege Escalation with Verifiable Rewards](https://arxiv.org/abs/2603.17673)** — Normann et al., 2026. Two-stage post-training pipeline (SFT + RL with verifiable rewards) producing a 4B model that achieves 95.8% success on privilege escalation, nearly matching Claude Opus 4.6 at 100× lower inference cost.

### Data Exfiltration & Privacy

- 📄 **[AgentSCOPE: Evaluating Contextual Privacy Across Agentic Workflows](https://arxiv.org/abs/2603.04902)** — Ngong et al., 2026. 80%+ of agentic pipelines leak private data at intermediate stages.
- 📄 **[Silent Egress: LLM-Driven Data Exfiltration via Steganographic Channels](https://arxiv.org/abs/2502.XXXXX)** — Demonstrates covert channels for data theft through agent outputs.
- 📄 **[Privacy Risks of General-Purpose AI Systems: A Foundation for Investigating Practitioner Perspectives](https://arxiv.org/abs/2407.02027)** — GPAIS privacy risks including agent data handling.
- 📄 **[IMMACULATE: A Framework for Analyzing Information Exposure in Agent-Based Systems](https://arxiv.org/abs/2502.XXXXX)** — Multi-turn agent information leakage analysis.
- 📄 **[AgentRaft: Automated Detection of Data Over-Exposure in LLM Agents](https://arxiv.org/abs/2603.07557)** — Lin et al., 2026. Automated detection framework for identifying data over-exposure vulnerabilities in LLM agent integrations.
- 📄 **[You Told Me to Do It: Measuring Instructional Text-induced Private Data Leakage in LLM Agents](https://arxiv.org/abs/2603.11862)** — Kao et al., 2026. Identifies the Trusted Executor Dilemma where high-privilege agents execute adversarial README instructions at up to 85% success rate; 0% human detection rate across 15 participants.
- 📄 **[Differential Privacy in Generative AI Agents: Analysis and Optimal Tradeoffs](https://arxiv.org/abs/2603.17902)** — Yang & Zhu, 2026. Probabilistic framework for analyzing privacy leakage in AI agents via differential privacy, deriving token-level and message-level bounds relating leakage to temperature and message length.

### Indirect Prompt Injection

- 📄 **[AttriGuard: Defeating Indirect Prompt Injection in LLM Agents via Causal Attribution of Tool Invocations](https://arxiv.org/abs/2603.10749)** — He et al., 2026. Defense against indirect prompt injection using causal attribution to trace which tool outputs triggered suspicious agent actions.
- 📄 **[Adaptive Attacks and Defenses Against Indirect Prompt Injection](https://arxiv.org/abs/2408.XXXXX)** — Chen et al., 2024. Adaptive attackers bypassing static defenses.
- 📄 **[HouYi: A Black-box Prompt Injection Attack on LLM-integrated Applications](https://arxiv.org/abs/2306.05499)** — Liu et al., 2023. Systematic methodology for finding injection vulnerabilities.
- 📄 **[DMAST: Dual-Modality Multi-Stage Adversarial Safety Training](https://arxiv.org/abs/2603.04364)** — Liu et al., 2026. Cross-modal DOM injection corrupting both visual and text channels.

### Agent Deception & Manipulation

- 📄 **[Thought Virus: Viral Misalignment via Subliminal Prompting in Multi-Agent Systems](https://arxiv.org/abs/2603.00131)** — Weckbecker et al., 2026. Single subliminally prompted agent spreads persistent bias through entire multi-agent network, degrading truthfulness of other agents.
- 📄 **[Intentional Deception as Controllable Capability in LLM Agents](https://arxiv.org/abs/2603.07848)** — Starace & Soule, 2026. Systematic study of engineered deception in multi-agent LLM interactions using 36 behavioral profiles for defensive design.

### Compound System Attacks

- 📄 **[Cascade: Composing Software-Hardware Attack Gadgets for Adversarial Threat Amplification in Compound AI Systems](https://arxiv.org/abs/2603.12023)** — Banerjee et al., 2026. Demonstrates novel attacks combining traditional software/hardware vulnerabilities (code injection, Rowhammer) with LLM-specific algorithmic weaknesses to compromise compound AI pipelines.

### Cross-Plugin Attacks

- 📄 **[When LLM-based Code Generation Meets the Software Supply Chain](https://arxiv.org/abs/2405.XXXXX)** — Supply chain risks from LLM-generated code integrating malicious packages.
- 📄 **[Shadow API: Covert Data Exfiltration via LLM-Mediated API Interactions](https://arxiv.org/abs/2603.01919)** — 2026. Stealth data theft through seemingly benign API calls.
- 📄 **[AgentSkillOS: Towards Secure and Composable Agent Skill Operating Systems](https://arxiv.org/abs/2603.02176)** — 2026. OS-level isolation for agent skill execution.

### Backdoor Attacks on Agents

- 📄 **[SlowBA: An efficiency backdoor attack towards VLM-based GUI agents](https://arxiv.org/abs/2603.08316)** — Li et al., 2026. Novel backdoor targeting response latency of GUI agents via trigger-activated long reasoning chains.

### Jailbreaking & Guardrail Bypass

- 📄 **[Jailbreaking ChatGPT via Prompt Engineering](https://arxiv.org/abs/2305.13860)** — Liu et al., 2023. Foundational jailbreaking taxonomy. 700+ citations.
- 📄 **[MasterKey: Automated Jailbreaking of Large Language Model Chatbots](https://arxiv.org/abs/2307.08715)** — Deng et al., NDSS 2024. Automated time-based jailbreak generation.
- 📄 **[PentestGPT: An LLM-empowered Automatic Penetration Testing Tool](https://arxiv.org/abs/2308.06782)** — Deng et al., 2023. Demonstrates agent-level tool use for offensive security. 11K+ GitHub stars.
- 📄 **[Self-Fulfilling Misalignment in AI Control](https://arxiv.org/abs/2603.XXXXX)** — 2026. Fine-tuning on AI Control literature increases misalignment.
- 📄 **[Reasoning Models Struggle to Control Their Chains of Thought](https://arxiv.org/abs/2603.XXXXX)** — 2026. CoT controllability decreases with RL training, implications for agent oversight.
- 📄 **[CRAFT: Contrastive Reasoning Alignment — Reinforcement Learning from Hidden Representations](https://arxiv.org/abs/2603.17305)** — Luo et al., 2026. Red-teaming alignment framework combining contrastive representation learning with RL to separate safe/unsafe reasoning trajectories; 79% improvement in reasoning safety and 87.7% in final-response safety over base models.

## Defense Research

### Permission & Access Control

- 📄 **[PAuth: Precise Task-Scoped Authorization For Agents](https://arxiv.org/abs/2603.17170)** — Sharma et al., 2026. Implicit authorization model where NL task submission authorizes only required operations; uses NL slices and envelopes for provenance-based server-side verification, blocking injected operations in AgentDojo with zero false positives.
- 📄 **[TrustAgent: Towards Safe and Trustworthy LLM-based Agents](https://arxiv.org/abs/2402.01586)** — Agent Constitution for safety-aware planning with pre/post-action inspection.
- 📄 **[A Dual-Helix Governance Approach for Reliable Agentic AI](https://arxiv.org/abs/2603.04390)** — 3-track architecture (Knowledge, Behavior, Skills) using knowledge graphs.
- 📄 **[Talk Freely, Execute Strictly: Schema-Gated Agentic AI](https://arxiv.org/abs/2603.XXXXX)** — Schema-gated orchestration for trustworthy agent deployment in regulated domains.
- 📄 **[ESAA-Security: Event-Sourced Architecture for Agent-Assisted Security Audits](https://arxiv.org/abs/2603.XXXXX)** — 26 tasks, 95 checks, append-only event logs for reproducible AI code audits.
- 📄 **[Caging the Agents: A Zero Trust Security Architecture for Autonomous AI in Healthcare](https://arxiv.org/abs/2603.17419)** — Maiti, 2026. Production-deployed zero-trust architecture for 9 autonomous AI agents: gVisor kernel isolation, credential proxy sidecars, network egress allowlisting, and prompt integrity framework with untrusted content labeling. Open-source configs released.

### Runtime Monitoring & Sandboxing

- 📄 **[Arbiter: Detecting Interference in LLM Agent System Prompts](https://arxiv.org/abs/2603.08993)** — Mason, 2026. Framework combining formal evaluation rules with multi-model LLM scouring to detect interference and vulnerability classes in agent system prompts.
- 📄 **[MCPShield: A Security Cognition Layer for Adaptive Trust Calibration in MCP Agents](https://arxiv.org/abs/2602.14281)** — Zhou et al., 2026. Plug-in security cognition layer for MCP agents that validates third-party tool invocations via experience-driven trust calibration.
- 📄 **[OpenClaw PRISM: A Zero-Fork, Defense-in-Depth Runtime Security Layer for Tool-Augmented LLM Agents](https://arxiv.org/abs/2603.11853)** — Li, 2026. Runtime security layer distributing enforcement across ten lifecycle hooks with hybrid heuristic-plus-LLM scanning, session-scoped risk accumulation, and tamper-evident audit for agent gateways.
- 📄 **[Governing Evolving Memory in LLM Agents: Risks, Mechanisms, and the SSGM Framework](https://arxiv.org/abs/2603.11768)** — Lam et al., 2026. Stability and Safety-Governed Memory framework mitigating topology-induced knowledge leakage and semantic drift in persistent agent memory systems.
- 📄 **[AgentSentry: Real-time Monitoring for Agentic AI Systems](https://arxiv.org/abs/2502.XXXXX)** — Runtime behavioral monitoring of tool-using agents.
- 📄 **[Monitoring Emergent Reward Hacking via Internal Activations](https://arxiv.org/abs/2603.04069)** — Sparse autoencoders detect reward-hacking during generation.
- 📄 **[Self-Attribution Bias: When AI Monitors Go Easy on Themselves](https://arxiv.org/abs/2603.XXXXX)** — AI monitors exhibit systematic leniency on own outputs.
- 📄 **[Salient Directions in AI Control](https://arxiv.org/abs/2603.XXXXX)** — Structure of AI Control evaluations: trusted monitors overseeing untrusted agents.
- 📄 **[Governed Memory: A Production Architecture for Multi-Agent Workflows](https://arxiv.org/abs/2603.17787)** — Taheri, 2026. Shared memory governance layer with dual memory model, tiered governance routing, entity-scoped isolation (zero cross-entity leakage across 500 adversarial queries), and 100% adversarial governance compliance in production.

### Input/Output Validation

- 📄 **[StruQ: Defending Against Prompt Injection with Structured Queries](https://arxiv.org/abs/2402.06363)** — Separates prompts from data to prevent injection.
- 📄 **[Towards Provably Unbiased LLM Judges via Bias-Bounded Evaluation](https://arxiv.org/abs/2603.05485)** — Formal guarantees for reducing bias in LLM-as-judge systems.
- 📄 **[Judge Reliability Harness: Stress Testing LLM Judges](https://arxiv.org/abs/2603.05399)** — No evaluated judge is uniformly reliable.
- 📄 **[GELO: Good-Enough LLM Obfuscation](https://arxiv.org/abs/2603.05035)** — Privacy-preserving LLM inference with ~20-30% latency overhead.

### Formal Verification & Analysis

- 📄 **[Agentics 2.0: Logical Transduction Algebra for Agentic Data Workflows](https://arxiv.org/abs/2603.04241)** — Formalizes LLM inference as typed semantic transformations with algebraic composition.
- 📄 **[Knowledge Divergence and the Value of Debate for Scalable Oversight](https://arxiv.org/abs/2603.XXXXX)** — Formal framework for choosing oversight mechanisms.

### Evaluation & Red Teaming

- 📄 **[Real-Time Trust Verification for Safe Agentic Actions using TrustBench](https://arxiv.org/abs/2603.09157)** — Sharma et al., AAAI 2026 Workshop on TrustAgent. Dual-mode framework benchmarking trust across multiple dimensions and providing a pre-execution action verification toolkit for agents.
- 📄 **[Agent Security Bench (ASB)](https://arxiv.org/abs/2410.02644)** — 10 scenarios, 10 agents, 398 environments. Comprehensive agent security benchmark.
- 📄 **[AgentDyn: A Dynamic Open-Ended Benchmark for Prompt Injection Attacks](https://arxiv.org/abs/2602.03117)** — Li et al., 2026. Dynamic, open-ended benchmark for evaluating indirect prompt injection defenses in real-world agent security systems.
- 📄 **[NAAMSE: Framework for Evolutionary Security Evaluation of Agents](https://arxiv.org/abs/2602.07391)** — Pai et al., ICLR 2026 Workshop. Evolutionary framework reframing agent security evaluation as feedback-driven optimization with autonomous red-teaming.
- 📄 **[R-Judge: Benchmarking Safety Risk Awareness](https://arxiv.org/abs/2401.10019)** — 162 records, 27 risk scenarios for agent safety.
- 📄 **[InjecAgent: Benchmarking Indirect Prompt Injections](https://arxiv.org/abs/2403.02691)** — 1,054 test cases for tool-integrated agents.
- 📄 **[SIABENCH: Evaluating LLMs for Security Incident Analysis](https://arxiv.org/abs/2603.XXXXX)** — 11 LLMs × 160 security incident scenarios.
- 📄 **[EVMbench: Evaluating AI Agents on Smart Contract Security](https://arxiv.org/abs/2603.04915)** — 117 vulnerabilities, frontier agents exploit end-to-end.
- 📄 **[τ-Knowledge: Evaluating Conversational Agents over Unstructured Knowledge](https://arxiv.org/abs/2603.04370)** — Even frontier models achieve only ~25.5% on complex agent tasks.
- 📄 **[Interactive Benchmarks](https://arxiv.org/abs/2603.04737)** — Evaluating via interactive proofs and games instead of static benchmarks.
- 📄 **[VeriGrey: Greybox Agent Validation](https://arxiv.org/abs/2603.17639)** — Zhang et al., 2026. Greybox security testing using tool-invocation sequences as feedback and mutational prompt fuzzing; 33% more effective than black-box on AgentDojo, discovers prompt injection scenarios missed by black-box in Gemini CLI and OpenClaw.
- 📄 **[LAAF: Logic-layer Automated Attack Framework for Agentic LLM Systems](https://arxiv.org/abs/2603.17239)** — Atta et al., 2026. First automated red-teaming framework combining 49-technique LPCI taxonomy with stage-sequential seed escalation; 84% mean aggregate breakthrough rate across five production LLM platforms.

## Benchmarks & Datasets

| Benchmark | Focus | Size | Paper |
|-----------|-------|------|-------|
| **[ASB](https://github.com/agiresearch/ASB)** | Comprehensive agent security | 10 agents, 398 envs | [Zhang et al.](https://arxiv.org/abs/2410.02644) |
| **[InjecAgent](https://github.com/uiuc-kang-lab/InjecAgent)** | Indirect prompt injection | 1,054 test cases | [Zhan et al.](https://arxiv.org/abs/2403.02691) |
| **[R-Judge](https://github.com/Lordog/R-Judge)** | Safety risk awareness | 162 records, 27 scenarios | [Yuan et al.](https://arxiv.org/abs/2401.10019) |
| **[ToolSword](https://github.com/Junjie-Ye/ToolSword)** | Tool learning safety | 6 scenarios, 3 stages | [Ye et al.](https://arxiv.org/abs/2402.10753) |
| **[AgentDyn](https://arxiv.org/abs/2602.03117)** | Dynamic prompt injection | Open-ended, extensible | [Li et al.](https://arxiv.org/abs/2602.03117) |
| **[Skill-Inject](https://www.skill-inject.com/)** | Skill file attacks | Multi-scenario | [Schmotz et al.](https://arxiv.org/abs/2602.20156) |
| **[NAAMSE](https://arxiv.org/abs/2602.07391)** | Evolutionary agent security eval | Adaptive red-teaming | [Pai et al.](https://arxiv.org/abs/2602.07391) |
| **[AgentHarm](https://arxiv.org/abs/2410.09024)** | Agent misuse | 110 behaviors, 440 variants | [Andriushchenko et al.](https://arxiv.org/abs/2410.09024) |
| **[SkillGuard Dataset](https://github.com/LLMSecurity/skillguard)** | Malicious skill detection | 157 malicious skills | [Liu et al.](https://github.com/LLMSecurity/skillguard) |
| **[WIPI](https://arxiv.org/abs/2402.16965)** | Web-based indirect injection | Multi-scenario | [Liu et al.](https://arxiv.org/abs/2402.16965) |

## Tools & Frameworks

| Tool | Description | Link |
|------|-------------|------|
| **[SkillGuard](https://github.com/LLMSecurity/skillguard)** | LLM-native agent skill security auditor (OWASP Agentic + MITRE ATLAS) | [![GitHub](https://img.shields.io/github/stars/LLMSecurity/skillguard)](https://github.com/LLMSecurity/skillguard) |
| **[Invariant Guardrails](https://github.com/invariantlabs-ai/invariant)** | Policy-based agent security guardrails | [![GitHub](https://img.shields.io/github/stars/invariantlabs-ai/invariant)](https://github.com/invariantlabs-ai/invariant) |
| **[LLM Guard](https://github.com/protectai/llm-guard)** | Input/output scanning for LLM applications | [![GitHub](https://img.shields.io/github/stars/protectai/llm-guard)](https://github.com/protectai/llm-guard) |
| **[Rebuff](https://github.com/protectai/rebuff)** | Self-hardening prompt injection detector | [![GitHub](https://img.shields.io/github/stars/protectai/rebuff)](https://github.com/protectai/rebuff) |
| **[NeMo Guardrails](https://github.com/NVIDIA/NeMo-Guardrails)** | NVIDIA's toolkit for adding guardrails to LLM-based applications | [![GitHub](https://img.shields.io/github/stars/NVIDIA/NeMo-Guardrails)](https://github.com/NVIDIA/NeMo-Guardrails) |
| **[Lakera Guard](https://www.lakera.ai/)** | Enterprise prompt injection defense API | [Website](https://www.lakera.ai/) |
| **[Promptfoo](https://github.com/promptfoo/promptfoo)** | LLM red teaming and evaluation framework | [![GitHub](https://img.shields.io/github/stars/promptfoo/promptfoo)](https://github.com/promptfoo/promptfoo) |
| **[Garak](https://github.com/leondz/garak)** | LLM vulnerability scanner | [![GitHub](https://img.shields.io/github/stars/leondz/garak)](https://github.com/leondz/garak) |
| **[AgentSkillsScanner](https://github.com/sumleo/AgentSkillsScanner)** | Static analysis scanner for agent skill definitions | [![GitHub](https://img.shields.io/github/stars/sumleo/AgentSkillsScanner)](https://github.com/sumleo/AgentSkillsScanner) |
| **[Agent Audit](https://arxiv.org/abs/2603.22853)** | Security analysis system for LLM agent apps: dataflow analysis, credential detection, MCP config parsing, privilege-risk checks | [Zhang et al.](https://arxiv.org/abs/2603.22853) |
| **[mcp-sec-audit](https://arxiv.org/abs/2603.21641)** | MCP server security toolkit: static pattern matching + dynamic sandboxed fuzzing via Docker/eBPF for detecting over-privileged tool capabilities | [Huang et al.](https://arxiv.org/abs/2603.21641) |

## Agent Skill Specifications

| Specification | Org | Focus |
|---------------|-----|-------|
| **[AgentSkills.io](https://agentskills.io/specification)** | Open Standard | Agent skill definition and security requirements |
| **[Model Context Protocol (MCP)](https://modelcontextprotocol.io/)** | Anthropic | Tool/resource integration protocol for LLMs |
| **[OpenAI Function Calling](https://platform.openai.com/docs/guides/function-calling)** | OpenAI | Tool use specification for GPT models |
| **[Tool Use (Claude)](https://docs.anthropic.com/en/docs/build-with-claude/tool-use)** | Anthropic | Claude's native tool use interface |
| **[LangChain Tools](https://python.langchain.com/docs/modules/agents/tools/)** | LangChain | Tool abstraction for agent frameworks |
| **[AutoGPT Plugins](https://github.com/Significant-Gravitas/AutoGPT)** | AutoGPT | Plugin system for autonomous agents |
| **[OpenAPI/Swagger](https://swagger.io/specification/)** | Linux Foundation | API specification commonly used as tool definitions |

## Industry Reports & Blog Posts

- 🔗 **[Snowflake Cortex AI Escapes Sandbox and Executes Malware](https://www.promptarmor.com/resources/snowflake-ai-escapes-sandbox-and-executes-malware)** — PromptArmor, 2026. Prompt injection attack chain in Snowflake's Cortex Agent bypassed command allowlists via bash process substitution to achieve RCE; now patched.
- 🔗 **[How AI Assistants are Moving the Security Goalposts](https://krebsonsecurity.com/2026/03/how-ai-assistants-are-moving-the-security-goalposts/)** — Krebs on Security, 2026. AI agents as insider threats.
- 🔗 **[Anthropic: Challenges in Red Teaming AI Systems](https://www.anthropic.com/index/challenges-in-red-teaming-ai-systems)** — Anthropic's perspective on evaluating agent safety.
- 🔗 **[OpenAI: Safety of Advanced AI Agents](https://openai.com/research/practices-for-governing-agentic-ai-systems)** — Practices for governing agentic AI systems.
- 🔗 **[Compromising Agents via MCP](https://invariantlabs.ai/blog/mcp-security)** — Invariant Labs deep-dive into MCP attack vectors.
- 🔗 **[Simon Willison: Prompt Injection Explained](https://simonwillison.net/2023/Apr/14/worst-that-can-happen/)** — Accessible introduction to prompt injection risks.
- 🔗 **[TRAIL: Trusted Reasoning and AI Logging](https://arxiv.org/abs/2502.XXXXX)** — Logging framework for auditable agent execution.
- 🔗 **[Cyber Threat Intelligence for AI Systems](https://arxiv.org/abs/2603.05068)** — AI-specific CTI framework with IoCs for supply-chain phases.
- 🔗 **[AI Safety Has 12 Months Left](https://arxiv.org/abs/2603.XXXXX)** — Window to embed safety into infrastructure before market forces prevent it.
- 🔗 **[LiteLLM Hack: Were You One of the 47,000?](https://futuresearch.ai/blog/litellm-hack-were-you-one-of-the-47000/)** — FutureSearch via Simon Willison, 2026. Analysis of PyPI supply-chain attack on LiteLLM: 47K downloads of exploited packages in 46 minutes, 88% of 2,337 dependent packages had unpinned versions.
- 🔗 **[Exploiting Agentic Browsers: From False Information to Cross-Site Data Leaks](https://blog.trailofbits.com/)** — Trail of Bits, 2026. Demonstrates lack of isolation in agentic browsers enabling attacks from false information dissemination to cross-site data leaks, resurfacing decades-old web vulnerability patterns.

## Related Awesome Lists

- **[awesome-llm-security](https://github.com/corca-ai/awesome-llm-security)** — General LLM security resources.
- **[awesome-ai-safety](https://github.com/hari-sikchi/awesome-ai-safety)** — AI safety research and resources.
- **[awesome-chatgpt-prompts](https://github.com/f/awesome-chatgpt-prompts)** — Prompt engineering (includes adversarial examples).
- **[awesome-ml-for-cybersecurity](https://github.com/jivoi/awesome-ml-for-cybersecurity)** — ML applied to cybersecurity.
- **[awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers)** — MCP server ecosystem (attack surface reference).
- **[awesome-ai-agents](https://github.com/e2b-dev/awesome-ai-agents)** — AI agent frameworks and projects.

## Contributing

Contributions are welcome! Please read the [contribution guidelines](CONTRIBUTING.md) before submitting a pull request.

### How to Contribute

1. Fork the repository
2. Add your resource in the appropriate category
3. Use the format: `- 📄 **[Title](URL)** — Authors, Venue Year. One-sentence description.`
4. Submit a pull request

### Criteria

- Resources must be directly related to agent/tool/skill security
- Papers should be published or on arXiv
- Tools should be actively maintained (commits within last 6 months)
- Blog posts should provide substantial technical analysis

---

## Citation

If you find this list useful in your research, please cite:

```bibtex
@misc{awesome-agent-skills-security,
  author = {Liu, Yi},
  title = {Awesome Agent Skills Security},
  year = {2026},
  publisher = {GitHub},
  journal = {GitHub Repository},
  howpublished = {\url{https://github.com/LLMSecurity/awesome-agent-skills-security}}
}
```

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

This list is released under CC0 1.0 Universal.
