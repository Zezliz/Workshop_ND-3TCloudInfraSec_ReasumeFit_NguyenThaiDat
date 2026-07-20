---
title: "Event 2"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

# Summary Report: "FCAJ Community Day"

### Event Information
*   **Event Name:** FCAJ Community Day.
*   **Date:** 23-05-2026.
*   **Venue:** 26th Floor, Bitexco Financial Tower, 02 Hai Trieu Street, Ben Nghe Ward, Saigon, Ho Chi Minh City.
*   **Organizer:** FCAJ Community in coordination with AWS Study Group.

### Event Objectives
*   **Program Goals:** Not just to listen to seminars, the event is also a place for attendees to actively connect, network, and inspire one another.
*   **Key Messages:** Cover 6 sharing sessions spanning Artificial Intelligence (AI), Cloud Computing, and real-world practical stories in rigorous enterprise environments.
*   **Value for Attendees:** Recognize recruitment market demands, know how to provide correct contexts for AI, deeply understand Cloud cost optimization, and grasp mindsets for bringing AI into enterprise production instead of just building toy demos.

### Speakers
*   **Tinh Truong** – Platform Engineer at GoTymeX
*   **Thinh Nguyen** – DevOps Engineer | FCAJ Ambassador
*   **Anh Pham** – Cloud Consultant at G-AsiaPacific Vietnam
*   **Uyen Le** – GenAI Engineer at VIB
*   **Thao Nguyen** – GenAI Engineer at VIB
*   **Mai Nguyen** – GenAI Engineer at VIB
*   **Duc Dao** – Solutions Architect at Cloud Kinetics
*   **Vy Lam** – Senior Business Systems Analyst at VPBank

### Key Highlights
*   **Problem Overview:** 
    *   The IT industry is in transition. AI makes software development cheaper, which increases demand, but it strictly requires real engineering capability. 
    *   Sloppy copy-pasting ("Internet Builder") or prompting AI without context creates garbage. 
    *   CloudFront egress costs are often difficult to predict (danger of bill shock). 
    *   Integrating AI in enterprises faces major barriers regarding data leaks and compliance/security. 
    *   AI is always probabilistic—even with temperature set to 0 due to server-side optimization techniques.
*   **Introduced Solutions:**
    *   Equip yourself with practical business logic knowledge and build complete products instead of stopping at simple demos.
    *   Apply CloudFront "Flat-rate pricing" to control and fix monthly egress costs.
    *   Design Multi-Agent systems with clear roles (e.g., finance expert, risk expert agent) rather than overloading everything onto a Single Agent.
    *   Implement security Guardrails, prevent Prompt Injection, and establish Audit Trails in all enterprise AI systems.
*   **Technologies/Services/Tools:** Amazon CloudFront (CDN, DDoS protection, VPC Origin, MTLS), Amazon Q (AI Agent for Business Intelligence), LLMs, Model Context Protocol (MCP), Terraform, and CrewAI.
*   **Demos or Case Studies:**
    *   **Data Case Study:** Using Amazon Q to read Excel data files and automatically generate analytical dashboard charts (BI).
    *   **Hackathon Case Study:** The "UTM Morpo" project—an AI system that generates HTML UI code and allows users to drag, drop, and edit interfaces directly, completed in 36 hours.
    *   **Enterprise Case Study:** Using a Multi-Agent system to analyze credit eligibility for a Startup without traditional collateral assets at a bank.
*   **Key Notes:** University degrees and legacy skills do not lose value; they become stricter filters as market competition rises. Multi-Agent systems still require human-in-the-loop decisions rather than full autopilot mode.

### Key Takeaways
*   **Mindset and Methodology:** Need a business mindset and deep understanding of business context: Who is the AI serving, for what purpose, and when.
*   **Technical Knowledge:** Deeply understand how LLMs select words based on token scores (Logit/Softmax/Temperature). Master CloudFront security mechanisms like hiding origins using VPC Origin, and Mutual TLS (mTLS) requiring authentication from both server and client.
*   **Best Practices:** To prevent AI hallucination, provide highly detailed context specific to your organization/project, rather than generic web knowledge.
*   **Real-world Experience:** Never copy buggy code to AI, get it modified, and paste it straight into shared codebases without reviewing it first (Ctrl+C/Ctrl+V); this can destroy the enterprise's coding standards.

### Applying to Work
*   **What can be applied to current projects:** Apply session partitioning and refresh prompt contexts frequently to optimize AI outputs. Build guardrails to filter input and output data when working with LLMs.
*   **Technologies to experiment with:** Deploy Infrastructure as Code (IaC) using Terraform instead of manual operations. Experiment with Amazon Q to support BI data management or build Multi-Agents with the CrewAI framework.
*   **Workflow improvement ideas:** Implement audit systems in internal processes: every AI-driven decision must be confirmed by a human and logged for accountability.

### Event Experience
*   **Learning from speakers:** Absorbed serious, meticulous "Enterprise-grade" working mindsets from engineers at banks and large conglomerates.
*   **Hands-on exposure:** Observed speakers dissect an LLM model from its internal architecture to how its generated outputs vary between local environments and cloud APIs.
*   **Networking and connection:** Seized opportunities to network and cross-discuss among developers to find partners or broaden perspectives.
*   **Most impressive point:** No matter how smart AI is, in highly regulated industries like banking, the person standing trial for errors is still the human, not the AI.

### Lessons Learned
*   **Most important knowledge:** Software engineering foundations are critical. You must understand secure system encoding/decoding before you can safely integrate AI into enterprise applications.
*   **Real-world advice:** Building a system is not just about making it work; it must run securely, reliably, and serve the end-user's business needs.
*   **Next learning steps:** Deep explore AI Mindsets and AI adoption. Enhance skills in distributed architectures (Multi-Agent), infrastructure automation (Terraform), and security compliance standards to prepare for roles at large corporations.

---
### Event Photos
![FCAJ Community Day - Speaker Hung sharing on the Importance of Context](/images/4-EventParticipated/4.2-Event2/event2_1.png)
![FCAJ Community Day - Speaker Vy presenting Multi-Agent in banking](/images/4-EventParticipated/4.2-Event2/event2_2.png)
![FCAJ Community Day - UTM Team sharing their Hackathon journey](/images/4-EventParticipated/4.2-Event2/event2_3.png)
![FCAJ Community Day - Wide view of the attendees](/images/4-EventParticipated/4.2-Event2/event2_4.jpg)

> Overall, the event helped solidify and transform my perspective on CloudFront security solutions, real-world cost optimization, and advanced Multi-Agent architecture.
