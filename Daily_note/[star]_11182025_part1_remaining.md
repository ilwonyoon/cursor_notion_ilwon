
# Ohouse AI – Mid-term Standalone Agentic Vision


##  Context: From Near-Term Onboarding to a Standalone Agentic App

In the near term, I’ve been finalizing the onboarding flows for Ohouse AI: users upload a room photo (e.g., a just-moved-in living room with basic furniture), answer a couple of questions, and we use that to shape a personalized shopping home. That flow is largely “done enough” for now.

The mid-term **standalone app vision** builds directly on that foundation:

* The **core concept** is an **AI interior chatbot** that understands your room and collaborates with you to design it.
* **UI-wise**, it’s intentionally simple and not dramatically different from the near-term flow:

  * You still upload photos of your room.
  * You still “talk to it” in a chat-like interface.
* The **main difference is not the mocks**; it’s the **behavior**:

  * Near-term: AI mostly **recommends a feed** of products and sections you can browse.
  * Mid-term: AI **does the job for you**, like an **agent**, and your work shifts from “figuring out what to ask” to **evaluating proposals and giving feedback**.

---

##  Core UX Shift: From Requesting to Evaluating

The **key difference** between near-term and mid-term is **how people use the tool**:

* Today, users:

  * Consume inspiration.
  * Use tools to create something themselves (e.g., Room Planner).
  * Manually request and assemble pieces.
* In the standalone agentic vision:

  * Users **describe what they want** and provide context.
  * The AI **creates design proposals** for them.
  * Users **evaluate, react, and iterate**, rather than writing the “perfect prompt”.

### From “What to Request” → “How to Give Feedback”

The biggest behavioral shift is:

* Not: “What should I request? How do I phrase this prompt?”
* But: **“How do I give feedback?”**

  * What do I like or dislike about this design?
  * What should change next?
  * How should this evolve in the next iteration?

The experience is still “creation,” but:

* Previously: **Creation = user using tools** directly.
* Now: **Creation = user conversing with a designer-like agent**, reviewing and refining proposals.

You still have a way to **manually touch the result** (like editing in a room planner), but the **core concept** is:

> “You review what’s presented, give feedback, and the AI does the next round.”

This is the **transition from consumption → self-creation → conversational co-creation**.

---

Standalone App Key Flows

## 1. Reasoning for AI interior designer

In the standalone app, the **user journey starts similarly**:

* Answer some questions.
* Upload photos of your room.

But instead of generating a **personalized feed**, the system:

* Generates **design results** for your room.
* Lets you **pick from (say) 3–4 top candidates**.
* Encourages you to refine those designs rather than “browse endless products”.

### Designing When and How the Agent Interacts

We need explicit logic for:

* **When to interrupt**:

  * When do we ask for permission?
  * When do we suggest a new iteration vs waiting for user input?
* **What kind of progress to show**:

  * We don’t want a black-box spinner.
  * We want meaningful **steps**.

I’m taking inspiration from tools like **Claude Code** and **Cursor**:

For Ohouse AI, we need to:

* Design the **agentic process UI**:

  * What intermediate states do we show while the AI is working?
  * How do we visually express:

    * “Analyzing your room.”
    * “Exploring layout options.”
    * “Matching products to your budget and taste.”
* Avoid overwhelming the user with internal details, but give:

  * Enough visibility to build confidence.
  * Clear sense that **real work is happening on their behalf**.


## 2. Feedback as the Center of the Experience

For this mid-term standalone app, the **feedback process is the critical second pillar** after AI reasoning.

You’re **not requesting by yourself** anymore:

* You **upload your room**.
* The AI proposes **multiple design options**.
* You **respond to what you see**:

  * “I like this one, but the rug is too dark.”
  * “I love the lighting here, but the wall feels empty.”
  * “This layout feels cramped; can we open it up?”

Feedback doesn’t end in a single session:

* If you **don’t like certain elements** or **love specific parts**, you talk about them and let the AI **switch or refine**.
* Over time, your feedback **flows into the next day / next iteration**:

  * The system should remember your preferences.
  * The next round of proposals should **reflect that evolving taste**.

The closing state of the journey looks like this:

* You have **several final design candidates** (e.g., four).
* Maybe you **like the second design best**, but you’re not 100% sure.
* You:

  * Ask the AI for **small refinements**, and/or
  * Ask **other people** for opinions (voting/crowd confidence).

At this point, the experience becomes:

* AI + **your feedback** + **crowd feedback** → **emotional confidence** to move.

---



### What to Show vs What to Hide

We also need to define:

* When there are **10 product recommendations**, do we:

  * Show all 10?
  * Show a **glimpse of the top 3–4** and keep the rest behind a tap?
* How do we **categorize the thought process** for display?

  * Example categories:

    * Space analysis.
    * Style matching.
    * Product search.
    * Cost alignment.
  * For each category:

    * What we show to users.
    * What stays internal.
    * What we log as **LLM instructions**.

This requires a clear mapping between:

* **Internal agent steps** (what the LLM + tools are doing).
* **External UX steps** (what we reveal, when, and how).

---

## 6. Results, Products, and the Role of Manual Tools

The **result view** in this vision is not just “a pretty render.”

For each generated design, we should expose:

* **Which products** are being used.
* **What materials** the user can buy.
* **What price ranges** they can expect for this design:

  * Not just a single item price, but a **sense of total spend** or bands.

This makes the design **actionable**:

* It’s not just inspiration; it’s a **shopping and execution starting point**.

### Room Planner and 3D Editing

Just like in the near-term Ohouse AI vision:

* The **Room Planner** exists as the equivalent of a **3D room editor**.
* If users want to **manually perfect** the room:

  * They can go into detailed editing, where **measurement accuracy matters**.
  * Unlike simple 2D visualization, a 3D editor needs precise size and placement.

But in the standalone agentic vision:

* The **core differentiation** is not in how people discover and swap products – those patterns are similar.
* The main difference is:

  * The AI does most of the **heavy creative lifting**.
  * Users step in when they want fine-tuning or precise layout.

We’ll still show manual flows briefly, but they are **supporting acts**, not the star.

---

## 7. Voting & Crowd Confidence: Emotional Assurance Layer

One unique component of this vision is the **voting / crowd feedback system**.

### It’s About Confidence, Not Just Trust

Users:

* Often have **preferences**, but not certainty.
* Want **confirmation from others**:

  * “Is this design good?”
  * “Does this look too much?”
  * “Is this rug size okay?”

The voting layer does several things:

1. **Gives users emotional confidence**

   * Users can submit their final candidates (e.g., four designs).
   * They can ask:

     * “Which one do you prefer?”
     * “Would you live in a space like this?”
   * The crowd response helps them feel **reassured** about their decision.

2. **Rewards participation**

   * People who **vote** can receive **free credits**.
   * That:

     * Incentivizes engagement.
     * Reroutes users’ desire to “play with AI interior design” more.
     * Builds a community loop around our product.

3. **Provides value to voters**

   * Voters get to see **multiple photo generations** (with the requester’s permission).
   * They can **save favorite designs** into their own collections.
   * This helps people who:

     * Aren’t sure where to start.
     * Want to browse what others are exploring.

4. **Serves as training data**

   * These responses:

     * Are **training material** for improving the model.
     * Help us understand what designs real people respond to.
   * The data is not just quantitative; it’s **emotional signal** about what feels right.

Net effect: This isn’t a static mock gallery. It’s a **social, confidence-building layer** on top of agentic design.

---

## 8. Business Model: Subscription, Affiliate, and Ads

The **core business model** for the standalone app is:

1. **Subscription + affiliate revenue**

   * Users pay a **subscription** for:

     * Unlimited or tiered design usage.
     * Access to advanced tools/features.
   * We earn **affiliate revenue** on products purchased through our flows.

2. **Transition to subscription + ads**

   * Over time, we move towards:

     * Subscription.
     * Plus **ads** or sponsored placements in a way that doesn’t compromise UX.

This creates:

* A **new revenue stream** beyond core commerce.
* A potentially **large TAM**:

  * Design assistance.
  * Decision confidence.
  * Execution guidance.

For both near-term and mid-term visions, I need to:

* Articulate:

  * Expected **business impact**.
  * Estimated **subscriptions**.
  * Revenue potential and model.
* Position this as:

  * A **“new mine” of revenue** for Ohouse, not just incremental GMV.

---

## 9. PropTech Extension: B2B Engine & CAC Machine

The last part is the **PropTech extension**, which is more business-oriented.

### Offering Tools to People Looking for a Home

Once we have:

* The **agentic flows**.
* The **design tools**.
* The **confidence and voting layers**.

We can offer this as a **tool for people evaluating properties**:

* Buying.
* Renting.
* Moving.

There are already PropTech services like **Matterport** that:

* Increase site engagement.
* Improve vacancy rates.
* Increase sale prices.

These services proved that:

* People want to **investigate spaces deeply online**.
* Better visualization and exploration correlate with **better business outcomes**.

### Our B2B Package

We can offer something more competitive:

* Our package is not limited to:

  * Just 3D tours.
  * Just visualization.
* We can combine:

  * AI agentic design.
  * Product match.
  * Engagement tracking.

We’re also building a **PTP-like set of tools** (internal naming aside) to:

* Track **unit engagement**:

  * How many people interact with each property.
  * How long they dwell on it.
* This information is **critical for property owners and managers**.

### Funnel Strategy: Free Play on Property Sites → Ohouse AI

The idea:

* Let users **play with the tool for free on property sites**:

  * Explore potential designs.
  * Visualize how they’d live in that space.
* Later, we invite them to:

  * Continue their journey on the **Ohouse AI site**.
  * Bring their designs and preferences with them.

This is:

* A **marketing and CAC strategy**:

  * PropTech integration becomes a **top-of-funnel acquisition** channel.
  * We pay for acquisition through improved partner outcomes and conversions.

It’s ambitious, and yes, there will be **competitors** working on pieces of this:

* Many focus narrowly on:

  * Specific visualization.
  * Specific subscription products.

But Ohouse has:

* A **full ecosystem**:

  * Content.
  * Commerce.
  * Contractors and interior services.
* A decade of experience solving **interior problems at scale** in Korea.

This gives us a **unique position** in the PropTech B2B space.

---

## 10. Strategic Timing: Korea, Global, and the Ceiling

We already see that:

* The **Korean interior commerce market has a ceiling**.
* That’s where we’re facing major challenges.

Even if we fully succeed in Korea:

* Entering the global market later means:

  * We’ll still have to **start from scratch** outside.
  * Competition will be **much stronger**.

There’s a Korean saying roughly equivalent to:

> “If you’re going to be hit, get hit first.”

Applied here:

* We’re going to face global expansion challenges anyway.
* The later we start, the **harder** and **more crowded** it gets.
* So I’m pitching this as:

  * A **global expansion narrative**.
  * Not something we do “after everything is safe”.

Practically:

* This is still a **vision pitch**.
* We won’t do everything at once.
* Based on traction and speed, we can later decide:

  * Whether to **start in Korea** first.
  * Or **start with a global branch**.

But the direction is: **don’t procrastinate on going global**.

---

## 11. Philosophy: Tools for AI, Not Just Tools for Users

The **core product concept** for Ohouse AI in this standalone vision is:

> We are building **more tools for the AI** to complete the job,
> not just more tools for the customer to manage themselves.

Concretely:

* We want to discover:

  * **What the customer truly needs** to bridge the gap between:

    * Visualization.
    * Execution of a **confident decision**.
* From there, we:

  * Develop tools that the AI can use:

    * Measurement.
    * Layout suggestions.
    * Product search.
    * Cost estimation.
    * Style translation.
  * Expose only the **right subset** to users.

We eventually want:

* A **Room Planner MCP** (multi-tool control point):

  * Users don’t have to “go play with multiple steps”.
  * We give the AI access to these tools in a **coherent framework**.
  * The **master AI agent** orchestrates them to complete the job.

Our role as humans (and as product designers) is:

* Not to build more knobs and sliders for users.
* But to build **capabilities and guardrails for the AI**, so it can:

  * Do more of the job.
  * While users mainly:

    * Provide direction.
    * Give feedback.
    * Make final decisions.

---

## 12. My Role, Team, and Collaboration

In this vision:

* I am the **main project lead for the pitch**:

  * The core concept was **coined by me**.
  * I am responsible for:

    * Setting the vision.
    * Structuring the narrative.
    * Connecting UX, AI, and business.

At the same time, this is **not a solo project**:

* **Supervisor**:

  * CPO (my manager) – the main senior sponsor and overseer.
* **Engineering**:

  * Engineering Manager.
  * Tech Lead managing the **Space AI team**.
  * ML Recommendation team:

    * We jointly defined:

      * Data vision.
      * Feasible technology.
      * Internal validation plans using existing tools.
* **Product owners**:

  * I’ve debated how explicitly to feature them.
  * The current framing:

    * I am the **project lead**.
    * Others are **contributors / collaborators / advisors**.
    * This makes it clear:

      * I own the vision.
      * But the work is inherently cross-functional.

In the portfolio, I intend to cover:

* Why I led this project.
* Why I ended up pitching it.
* How I collaborated with:

  * CPO.
  * Eng leads.
  * ML teams.
  * POs.
* The challenges we faced.
* The moment I developed **conviction that this is the right direction**.
* The major **takeaways** about:

  * AI product strategy.
  * Agentic UX.
  * Business expansion.

---

## 13. Ambition, Risk, and Conviction

I’m fully aware:

* There are many **what-ifs**.
* The technology is challenging.
* Competition will intensify.

But a few things feel stable:

1. **We’ve spent ~10 years** focused on interior space problems.
   We are one of the few tech companies at this scale in this domain.

2. **We’ve succeeded in South Korea**, even if we haven’t yet succeeded globally.
   That’s real expertise.

3. The AI wave is not going away:

   * Everything will be increasingly **empowered by AI**.
   * People will **gradually adopt** AI for jobs like interior design.
   * Their role will increasingly be:

     * Giving feedback.
     * Giving direction.
     * Not crafting perfect prompts.

4. If we don’t push this, **someone else will**:

   * Many companies already see this space.
   * We have:

     * Scale.
     * Data.
     * Multi-branch experience (content, commerce, contractors).

5. What customers fundamentally want:

   * **Someone to do the job for them**.
   * To **just talk and pay a reasonable price**.
   * Not to pay full interior design “billable hours” for everything.

The exact UX and tech **may not look exactly** like what I’m describing now.
But the **direction** feels right:

* Move from feed to agent.
* Move from prompts to feedback.
* Move from tools for users to tools for AI.
* Move from isolated inspiration to **end-to-end execution with emotional confidence**.

That’s the standard I think we should push toward, no matter how hard it is.

---

If you want, next step I can turn this into:

* A **portfolio narrative section** (“Mid-term Standalone Vision”)
  OR
* A **presentation outline** (e.g., 6–8 slides: Problem, Agentic UX, Feedback, Voting, Business Model, PropTech, My Role).
