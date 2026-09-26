**PROJECT PROPOSAL – PAPERCLIP**

# 1. Brief Description of Open Source Project Paperclip

Paperclip is an open-source platform that lets organizations manage teams of AI agents like a real workforce. Within one dashboard, users can build AI agents, hand out tasks, track what they are doing, run projects, set budgets, and review each agent's activity.

Security is important,. AI agents often touch sensitive areas things like source code, APIs, credentials, databases, or outside services. Paperclip addresses this by baking in features like authentication and authorization, approval workflows, secrets management, audit logs, and continuous agent monitoring. These controls help organizations stay in charge when AI agents access valuable or risky resources.

# 2. Describe a hypothetical operational environment

Think about a big company office where teams depend on Paperclip to run all kinds of business tasks using AI agents. In this place, security isn’t some afterthought it’s right at the heart of everything. Paperclip steps up: it manages roles, permissions, budgets, who gets assigned which tasks, who needs to approve what, secrets, and keeps super-detailed audit trails. Everything ties back to keeping things locked down.

People here expect the basics, like secure logins and role-based access, so nobody’s snooping around where they shouldn’t. Each user’s data stays separate, secrets stay protected, and every AI agent’s powers get spelled out in stone. If an agent wants to do something risky, an approval has to happen first, and every move gets tracked, just in case someone needs to figure out what went wrong.

Take a regular employee they will only see projects and AI agents tied to their job. Admins get more power: they manage who can do what, keep tabs on agent activity, and can shut down anything fishy right away. All these rules and checks keep company info locked up tight and make life tough for anyone whether it’s a user or an AI agent trying to mess around with their access.

# 3. Diagram of System Engineering View in the hypothetical environment

![Image: image_001](./PROJECT%20PROPOSAL_images/image_001.png)

# 4. Threats perceived by users of the software in its intended operational environment

In the hypothetical enterprise operational environment for Paperclip, users would perceive threats involving both conventional software security and the additional risks created by autonomous AI agents.

- Unauthorized access: Attackers or unauthorized employees could gain access to Paperclip accounts, projects, tasks, or administrative functions through stolen credentials or weak authentication.
- Privilege escalation: A normal user or AI agent could obtain permissions beyond those required for its role, potentially gaining access to restricted projects, secrets, or administrative functions.
- Sensitive-data exposure: Paperclip may process company documents, source code, task information, credentials, API keys, and other confidential information. Users would be concerned about accidental or malicious disclosure.
- Compromised AI agents: An AI agent could be manipulated, misconfigured, or compromised and perform actions that the organization did not intend, such as modifying files, executing inappropriate tasks, or accessing unauthorized resources.
- Prompt injection and malicious instructions: Content supplied to an AI agent could contain instructions designed to manipulate the agent into disclosing information or performing unauthorized actions.
- Secret and API-key theft: Credentials used to connect Paperclip with AI providers, Git repositories, databases, and enterprise services could be stolen and subsequently abused.
- Malicious or unauthorized task execution: An employee, attacker, or compromised agent could create tasks that cause agents to modify source code, access external systems, or perform other sensitive operations without proper approval.
- External integration compromise: Connections to Git repositories, AI model providers, cloud services, and other APIs increase the attack surface. A compromised external service or integration credential could affect Paperclip and enterprise resources.
- Data tampering: Attackers or malicious insiders could alter projects, agent configurations, task results, budgets, permissions, or audit information, threatening the integrity of the system.
- Denial of service and resource exhaustion: Attackers or malfunctioning agents could generate excessive tasks or API requests, making Paperclip unavailable or consuming significant computing resources and AI-service budgets.

# 5. List of security features in the software

For the hypothetical **enterprise deployment of Paperclip**, the following security features are relevant. These are based on Paperclip's current repository documentation; some controls depend on deployment mode or configuration.

- User and agent authentication Human operators can use authenticated sessions, while agents can authenticate with API keys or short-lived, run-scoped JWTs. Long-lived agent keys are hashed at rest.
- Authorization and permissions Paperclip distinguishes the authority of board operators and agents and applies permissions to sensitive operations. Agents cannot automatically perform administrative actions such as modifying authentication keys or bypassing approval gates.
- Company/data isolation Resources are company-scoped. Agents can access entities only within their company, and cross-company requests are denied. This is important when multiple organizations share one Paperclip deployment.
- Human approval controls Sensitive actions can require human approval. Paperclip supports approval workflows and allows operators to approve/reject requests, pause agents, terminate agents, and override their activities.
- Tool access governance Tool access can be governed through allow/block policies, approval requirements, profiles, risk classifications, and rate limits. Destructive or newly discovered high-risk tools can also be quarantined until reviewed.
- Secrets management and encryption API keys, tokens, and other secrets can be stored as encrypted secret references. Paperclip decrypts them server-side when needed and avoids returning decrypted secret values to the management UI.
- Audit logging and accountability User actions, agent activity, approvals, tool calls, cost events, and system changes can be recorded. Paperclip's documentation describes durable activity records and an immutable/append-only audit trail for security review and investigation.
- Budget and resource controls Administrators can establish spending limits for AI agents. Budget thresholds provide warnings, and hard limits can pause agents and prevent uncontrolled AI-service expenditures.

# 6. Motivation for Selecting Paperclip

## I chose Paperclip for this project because ypical chatbot or single AI agent. It is part of this new wave of software built to handle lots of autonomous AI agents inside organizations. Basically, Paperclip acts as a central hub where you can organize agents, set their tasks, give them goals, keep an eye on what they're doing, and set the rules they follow.

## For anyone interested in cybersecurity or systems security engineering, Paperclip raises some fascinating questions. These AI agents aren’t just answering questions they interact with real stuff: source code, files, APIs, credentials, model providers, data repositories, and other internal resources. Security can’t just focus on human accounts anymore. Now, the system has to decide what these agents can see and do.

## With this project, we get to revisit core security ideas—like authentication, authorization, least privilege, isolation, secrets management, auditing, and secure configuration—but apply them in a space that’s changing fast: autonomous AI systems.

# 7. Open-Source Project Description

Paperclip describes itself as an open-source application for managing AI agents at work. The software provides a centralized platform for coordinating teams of AI agents. Organizations can define goals, create agent roles, assign work, establish budgets, require approvals, and monitor agent activity.

The project describes four major areas of functionality: argentic task management, organizational structures for agents, agent training and evaluation, and the infrastructure necessary to operate AI agents. Paperclip supports multiple agent technologies and providers rather than requiring organizations to use one particular AI model or agent framework.

The software can therefore be viewed as an **AI-agent orchestration and governance platform** rather than an AI model itself.

# 8. Architecture and Platform

Paperclip uses a web-based client/server architecture. Repository documentation identifies major components including an Express-based REST API, React/Vite user interface, database packages, shared validators and types, agent adapters, plugins, a command-line interface, and supporting documentation.

A simplified architecture is:

**Human User → Paperclip Web Interface → Paperclip API/Control Plane → AI Agents → External Systems**

Paperclip can connect to different agent environments and tools, including Claude Code, Codex, Cursor, Bash, HTTP-based agents, and other compatible agents.

The project is designed to be **self-hosted,** meaning an organization can operate its own Paperclip instance rather than depending entirely on a centrally hosted Paperclip service.

# 9. Programming Languages and Technologies

The main repository is identified by GitHub primarily as a **TypeScript** project. Its architecture also makes substantial use of Node.js, React, Vite, Express, database tooling, HTML/CSS-related web technologies, and supporting scripts and configuration.

This technology stack is appropriate for Paperclip because both the management interface and control plane can be implemented within the JavaScript/TypeScript ecosystem.

# 10. Contributors and Project Activity

Paperclip is a highly active open-source project. As of September 25, 2026, GitHub showed approximately **82,900 stars and 15,000 forks** for the primary repository. GitHub also showed thousands of issues and pull requests, indicating substantial community participation and development activity. The repository was updated on September 25, 2026, demonstrating that development was active at the time of this review.

The GitHub Actions history also shows more than 2,500 workflow runs and numerous automated workflows involving CI, releases, smoke testing, runtime images, linting, and automated reviews.

These numbers should be treated as a snapshot because GitHub statistics change continuously.

# 11. Use and Popularity

Paperclip is intended for users who need to coordinate multiple AI agents toward common organizational objectives. Example use cases include software development teams, AI-driven businesses, research teams, and enterprises that want autonomous agents to perform work while maintaining human governance.

The repository describes capabilities such as task assignment, organizational structures, budgets, approvals, schedules, plugins, secrets, activity records, company isolation, and cost tracking.

Its large number of GitHub stars and forks suggests substantial developer interest. However, popularity on GitHub should not automatically be interpreted as evidence of production adoption or security maturity.

# 12. Documentation Sources

Several sources are available for studying Paperclip:

- The main GitHub repository contains source code, README documentation, issues, pull requests, security information, and development files.
- CONTRIBUTING.md explains how community members should prepare and submit changes.
- SECURITY.md explains how security vulnerabilities should be reported.
- AGENTS.md provides guidance for both human and AI contributors.
- The Paperclip documentation repository provides user guides, API and CLI references, adapter information, and deployment documentation.

These sources are useful because security analysis requires examining not only source code but also the project's intended architecture, deployment assumptions, security policies, and development practices.

### 13. License

Paperclip is distributed under the **MIT License**. The main repository identifies the license as MIT and attributes the software to Paperclip Labs, Inc.

The MIT License is a permissive open-source license. It generally allows users to use, copy, modify, distribute, sublicense, and sell copies of the software, provided that the required copyright and license notices are retained.

This makes Paperclip suitable for experimentation, modification, research, and commercial development without many of the restrictions associated with stronger copyleft licenses.

### 14. Contribution Procedures

Paperclip maintains a detailed CONTRIBUTING.md. Contributors are instructed to search existing issues and pull requests before beginning work to avoid duplicate efforts. Small contributions should be focused and limited in scope. Larger or more impactful changes should first be discussed with the project community.

Pull requests must follow the project's pull-request template and contain information such as the reasoning behind the change, what was changed, how the change was verified, potential risks, and the AI model used to assist with the work, if applicable. Tests and CI checks are expected to pass before a change is merged.

An interesting aspect of Paperclip's contribution process is its explicit recognition of AI-assisted software development. The contribution guide requires contributors to identify the AI model used for a change or state that the contribution was human-authored.

### 15. Contributor Agreements

The reviewed main-project documentation clearly establishes the MIT licensing model and contribution requirements. I did not find evidence in the reviewed repository materials of a separate mandatory **Contributor License Agreement (CLA)** comparable to those used by some large open-source projects. Therefore, it is safer to state that the public contribution process is governed by the repository's contribution rules and licensing terms rather than claiming that contributors must execute a separate CLA.

## 16. Security-Related History

Paperclip is particularly valuable for security study because its security history demonstrates how traditional web vulnerabilities can combine with the privileges given to autonomous AI agents.

### 17.Security Policy

Paperclip maintains a SECURITY.md file. The project instructs researchers to report vulnerabilities privately through GitHub's Security Advisory system rather than opening public issues.

GitHub's advisory page currently lists multiple published security advisories, including vulnerabilities involving authorization, cross-tenant access, command execution, stored cross-site scripting, approval attribution, and AI-agent access to connected resources.

### 18.Remote Code Execution and DNS Rebinding

One significant advisory published in July 2026 concerned **drive-by remote code execution through DNS rebinding** against local Paperclip instances. According to the advisory, the default local\_trusted deployment mode automatically treated local requests as administrator requests. When combined with insufficient Host-header validation and an adapter capable of executing operating-system commands, a malicious website could potentially reach a locally running Paperclip instance through DNS rebinding and trigger command execution.

The advisory classified the issue as critical with a CVSS 3.1 score of **9.6** and identified missing authorization and insecure default configuration among the associated weaknesses.

This vulnerability illustrates an important systems-security lesson: individually reasonable design assumptions can become dangerous when combined. Trusting localhost, permitting command execution, and omitting hostname validation created a security path that crossed the intended trust boundary.

### 19. Arbitrary File Read

Another security advisory concerned an **arbitrary file-read vulnerability.** An attacker possessing an agent API key could manipulate an agent configuration field controlling an instruction-file path. The Paperclip server subsequently used that path when reading a file without sufficiently restricting it to an approved workspace.

The vulnerability could potentially expose files accessible to the Paperclip server process, including configuration files, credentials, API tokens, or other sensitive information. The advisory identifies the affected versions as <= v0.3.1 and lists 2026.416.0 as the patched version.

This vulnerability demonstrates why **agent input must be treated as untrusted input,** even when the agent itself is an authorized component of the system.

### 20. Security Engineering Decisions and Features

Current Paperclip documentation describes security and governance capabilities such as **roles and permissions, company-level isolation, scoped secrets, SSO, RBAC, sandboxing, approval gates, audit trails, cost controls, and rollback mechanisms**.

The system also records mutating actions, agent state changes, cost events, approvals, comments, and work products as durable activity records. This supports accountability and security investigations.

Consequently, Paperclip's security history reflects both sides of open-source security engineering: the addition of defensive controls and the discovery of weaknesses that reveal where those controls or trust assumptions were insufficient.

## 21. Reflection on Learning

Studying Paperclip has expanded my understanding of security engineering because it demonstrates that securing an AI-based system involves more than protecting usernames and passwords. Before analyzing this project, I primarily associated application security with traditional concerns such as authentication, authorization, input validation, encryption, and database security. Paperclip demonstrates that these controls remain important but must also be applied to autonomous AI agents.

One of the most important lessons I learned is that **an AI agent should be treated as a separate security principal**. An authenticated agent should not automatically be trusted to perform every operation. Its permissions should be restricted according to its responsibilities and the principle of least privilege.

I also learned the importance of identifying **trust boundaries.** Paperclip communicates with human users, AI agents, databases, local operating systems, model providers, repositories, APIs, and other external services. Each interaction creates a potential security boundary that must be protected.

The project's vulnerability history reinforced the importance of secure defaults. The DNS-rebinding vulnerability is particularly instructive because trusting requests simply because they appeared to originate from localhost contributed to a much larger attack path. This demonstrates that security assumptions must be evaluated within the complete system rather than examining individual components in isolation.

Another lesson is the value of open-source security processes. Public source code, security advisories, contribution procedures, automated testing, and vulnerability-reporting mechanisms allow developers and security researchers to identify weaknesses and improve the project collaboratively.

Overall, this project helped me understand that **systems security engineering requires examining the complete operational environment**. In an AI-agent platform such as Paperclip, the security question is not simply whether a user is authenticated**.** The system must continually determine **who or what is requesting an action, what authority that entity has, which resource it is attempting to access, whether the action should require human approval, and how the action will be audited afterward. T**his perspective is especially important as autonomous AI systems become more capable and gain access to increasingly sensitive organizational resources.

Primary project resources:

Paperclip GitHub repository |

<https://github.com/paperclipai/paperclip>?

Security advisories |

<https://github.com/paperclipai/paperclip/security/advisories>?

Contributing guide |

<https://github.com/paperclipai/paperclip/blob/master/CONTRIBUTING.md>?

Security policy |

<https://github.com/paperclipai/paperclip/blob/master/SECURITY.md>?