# From Scarcity to Scale: Building an AI-Native UX Writing System

When I started leading UX writing at Ohouse, I faced a challenge that’s common in many fast-growing companies: we had only **one UX Writer** serving an organization of **over 400 product and engineering members**. She was talented and loved by everyone she worked with, but her impact was constrained by the structure. She wasn’t empowered to make strategic calls or to scale her craft across the company. Most of her work involved reviewing or fixing what others had already written — rather than shaping the user experience from the start.

This imbalance created frustration. Designers and PMs could freely change in-product content, while the sole UX Writer lacked the authority or tools to enforce consistency. On the marketing side, copywriters were doing their best to follow brand pitch guidelines, but the result was fragmented. Each team was writing in isolation, and the overall product tone of voice — the foundation of our brand experience — was inconsistent and difficult to maintain.

---

## Rethinking Scale Through AI

The turning point came when our CEO challenged me: *“What’s the measurable impact of UX writing at a company level?”*

That question forced me to reconsider how to **scale writing impact without scaling headcount**. Hiring more UX writers was the conventional path — one I had seen at Meta, where writing scaled through headcount and process. But here, that wasn’t feasible. So instead, I asked myself a different question:

> *What if one UX writer could achieve the impact of a hundred — not by working harder, but by working through AI?*

This was early 2024 — the moment when GPT models began to mature and “AI-assisted” workflows started to feel real. That’s when I began shaping a long-term vision: an **AI-native UX writing system** that could multiply the effectiveness of a single UX writer across every surface, every product line, and every business domain.

---

## Phase 1 — Establishing the Foundation: Defining the Tonal Voice

Before automating anything, we had to define what “good writing” meant for our brand. The first step was creating a **company-wide tone of voice framework** — one that could apply consistently across **content, commerce, and interior contractor** experiences.

Our tone needed to balance trust and approachability. Ohouse is a platform that helps users make major lifestyle decisions, from furnishing a home to hiring renovation contractors. Every word needed to project **reliability, clarity, and warmth**.

We worked cross-functionally with brand and product leadership to codify this voice into a shared standard — a **“Tone of Voice”**. Once approved by our CPOs, this became our company’s official voice guideline.

But one immediate problem emerged: **people loved the guideline but didn’t know how to apply it**.

That realization became the spark for the next phase — creating a system where anyone could write *as if* they were an expert UX Writer.

---

## Phase 2 — Amplifying Impact: GPT-S and the Ohouse UX Writing Book

The next challenge was clear: How do we help non-writers produce consistent, brand-aligned copy without needing direct review from the UX Writer every time?

This is where we built **GPTs (Ohouse UX Writing System)** — an internal GPT-powered assistant fine-tuned on our tone of voice, UX guidelines, and example copy across multiple domains.

We experimented with various AI writing tools on the market, but ultimately decided to build our own.
Why? Because **maintainability and adaptability** were key. Our tone of voice evolves with our brand; a static vendor model couldn’t keep up. We needed an internal system that could continuously learn and adapt.

So we built GPTs using our own curated dataset — a collection of “do’s and don’ts,” writing examples, and contextual annotations that mapped tone principles to specific UX scenarios.

We took a **deliberate, phased approach to adoption** — not a company-wide rollout.

**Phase 1: Strategic Selection**
The reality was that most teams were reluctant — they weren't actively looking for UX writing help. Rather than pushing the tool, we strategically identified the teams that **most wanted** UX Writer support and were willing to collaborate on building and testing new tools. These weren't random early adopters; they were teams we knew would benefit most and become credible advocates.

**Phase 2: Proof Building**
With these partner teams, we didn't just hand them a tool. We compared AI-generated copy with human-written versions, measured speed and quality, and gathered deep feedback. The results were promising: GPTs significantly reduced writing time, improved consistency, and increased internal satisfaction with copy reviews. The goal wasn't just to prove the tool worked — it was to **create measurable success stories that other teams could see and want to replicate**.

**Phase 3: Organic Scaling**
Once proof existed, the adoption curve shifted. We began receiving **inbound requests** from other teams asking to create their own **GPT-S versions** for their specific domains. Teams were now pulling the solution toward them, not waiting for us to push it.

The architectural approach we took was deliberate: **keep the core tone of voice framework consistent** across all versions, but **adapt the application patterns** to each domain's nuances — whether e-commerce flows, interior contractor messaging, or content discovery. This wasn't just customization; it was designing a system with centralized brand consistency and decentralized flexibility.

That's when I knew the adoption was working: when teams wanted to build their own versions and were willing to provide their domain-specific data to make it work.

---

## Phase 3 — Creating the UX Writing Archive: From Assistance to Automation

While GPTs improved consistency and accessibility, a deeper problem remained: **we had no visibility into how writing was performing after shipping**.

Was the tone consistent across products? Did changes improve user experience or metrics? Without data, we couldn’t quantify our impact or iterate intelligently.

That’s when we began the third phase — **building the UX Writing Archive**, an AI-driven automation layer that tracked all product text versions and their localization history.

We discovered that most of our in-product text was hard-coded — meaning we couldn’t track or update it systematically. To fix this, I worked with engineers to design a new infrastructure: a **plugin system** that automated key generation and stored text data in sync with product releases.

We hired an **AI workflow operator** to maintain these pipelines, ensuring every text update was automatically logged and versioned. This gave us a centralized dataset to analyze tone consistency, identify outdated strings, and eventually correlate text changes with performance metrics.

This shift — from *AI-assisted writing* to *AI-automated content management* — transformed how we managed language at scale. It also laid the groundwork for adaptive learning systems where models could evaluate and refine tone dynamically based on real-world outcomes.

---

## Phase 4 — Toward AI-Native: Connecting Systems and Closing the Loop

Once we had both Claude Skills and the UX Writing Archive, the next challenge was **integration**.

The limitation of Claude Skills alone: **they can't persistently store or access company data**. Claude Skills were AI-assisted — they could write well, but they had no memory of what we'd written before, no access to our archive, no way to check consistency against everything shipped.

**The shift came when we connected Claude Skills to our database through Cursor and cloud-based workflows.** Now the system could:
- **Read the entire UX Writing Archive** (every text decision we'd made before)
- **Write in context** (understanding what came before)
- **Generate consistently** (applying tone of voice not just as a rule, but as a lived pattern)

This transformed the system from **AI-assisted writing** (Claude Skills giving suggestions) to **AI-native writing** (a system that knows our entire history and maintains consistency autonomously).

The final goal — which we're now moving toward — is to connect performance logs to this system. By linking each piece of copy to behavioral or conversion metrics, we can let AI evaluate and optimize content autonomously over time. We're currently adding evaluators to the system, but this phase is still in progress.

This progression shows the full arc:

* **AI-assisted writing** (Claude Skills)
* **AI-automated management** (UX Archive)
* **AI-native evaluation** (self-improving system tied to performance data — *in progress*)

---

## The One-Person Model: AI as Force Multiplication

What made this project particularly powerful wasn't just the system we built — it was how we executed it.

**The reality:** One UX Writer. No dedicated engineering support. The vision and strategy came from my leadership, but the execution was owned by a single UX Writer working alongside an AI workflow operator.

This wasn't a constraint we worked around — it was the constraint that proved the model works.

By combining:
- **Clear strategic vision** (from design leadership)
- **Operational infrastructure** (the UX Writing Archive and Claude Skills)
- **AI literacy** (understanding how to augment human work)

...we didn't scale the UX writing team. We democratized UX writing itself.

Nearly 100 team members — designers, PMs, engineers, content strategists — now had access to a **personal AI-assisted UX writing capability**. They could write with the brand voice, get real-time feedback, and maintain consistency without needing to wait for a single UX Writer's review.

One UX Writer set the vision and maintained quality standards. But the *execution* scaled across the entire organization.

This is the blueprint: **AI-native workflows don't require scaling headcount. They distribute capability directly to the people who need it.**

And because this model is system-based, not person-based, any company can replicate it. Replace "UX writing" with "product design," "content strategy," or "customer research" — the framework remains the same.

---

## The Human Role in the AI Era

A key principle throughout this journey has been **augment, not replace** — and this required a clear distinction about what should be automated.

I categorized UX writing into two types:

**Additive Features (Automate):** Notification copy, UI microcopy, transactional messages, helper text — essential but not core to the product experience. These are where AI automation shines, freeing the UX Writer's time and ensuring consistency at scale.

**Core Product Narrative (Human-Led):** The writing that carries emotion, nuance, and meaning. The "word spacing like a poet would deliver" — the moments that define how users *feel* about the product, not just what they understand. This is where UX Writers focus their craft: high-stakes user flows, brand-defining moments, and the narrative that builds trust.

This isn't about replacing UX Writers. It's about **liberating them from the repetitive work so they can focus on the creative, emotional, strategic work** that only humans can do.

I see the future of UX writing not as automation of language, but as elevation of expression. The writer becomes less of a copy machine and more of a *curator of meaning*, shaping the emotional resonance that AI can't replicate.

---

## Why This Matters Beyond UX Writing

I started with UX writing for two strategic reasons:

**1. Technical:** Language is the natural domain of large language models. Text is where LLMs are natively strongest — far more mature than video, image, or audio generation. This made UX writing the ideal proving ground for AI-native workflows.

**2. Expertise:** I deeply understand UX writing strategy, frameworks, and execution. This wasn't just about applying a tool; it was about **setting a full vision and executing it end-to-end**. Because I could articulate the problem clearly, design the solution systematically, and measure impact rigorously, the project had credibility and could become a blueprint for other disciplines.

This combination — technical fit + personal expertise — made UX writing the strongest candidate to prove the AI-native framework works.

But the framework itself applies to any discipline that involves creative judgment and repetitive execution:

1. **Assist:** Use AI to scale individual output.
2. **Automate:** Build infrastructure to track, adapt, and evolve that output.
3. **Go Native:** Integrate AI into the core workflow so that it learns, measures, and improves autonomously.

For Ohouse, UX writing was the proving ground. But this model applies to product design, user research, content strategy, and beyond.

---

## Reflection

This project started as a tactical response to resource limits, but it evolved into something more fundamental: **a philosophy of designing for scale through intelligence, not manpower**.

What we built — Claude Skills, the UX Writing Archive, and the evolving AI-native writing ecosystem — represents a blueprint for the future of creative organizations. It's how a single designer or writer can impact an entire company when empowered with the right systems and mindset.

But I want to be honest about where we are: **we're getting there, but we're not there yet.**

Phase 1 (tone of voice) is complete. Phase 2 (Claude Skills adoption) is in production and growing. Phase 3 (UX Writing Archive) is operational. But Phase 4 — connecting performance metrics to autonomous evaluation — is still in progress. We're adding evaluators, but the fully self-improving system we envision isn't finished.

This is the actual, lived product. Not a theoretical model. Not a polished case study. It works, it's creating impact, but it's also still evolving. That's the honest assessment.

We're still early, but this is the path forward:
from **AI-assisted** to **AI-native**,
from **manual effort** to **self-improving systems**,
and from **individual craft** to **collective intelligence**.

---

Would you like me to now turn this into a **LinkedIn article draft** or a **Medium longform version (~4,000 words)** with optimized pacing, subheadings, and quotes for publication?
