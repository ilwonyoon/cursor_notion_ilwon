## **Visual Search — Shifting from Tag Quantity to Discovery Confidence**

**A design-led strategic initiative executed by cross-functional teams (Product Design, ML/Recommendation, Content, Search).**

---

## **Summary**

Identified that users couldn't efficiently find products matching their spaces due to visual tag noise, while creators dropped off during upload. Led Visual Search initiative to shift discovery from tag quantity to relevance confidence. Repositioned ML feature as Phase 1 of strategic transition, navigating Content team concerns through reframing and guardrail metrics. Phase 2 validation proved hypothesis—fewer, smarter tags increased discovery effectiveness and GMV growth despite tag reduction.

---

### **Problem**

By 2023, Ohouse's product discovery depended on manual product tags — small "+" icons overlaid on community photos.
While effective for short-term GMV, this model had reached critical limits:

Users faced **visual noise** (1-20+ tags per photo), making it harder to quickly identify products relevant to their own spaces.
Creators experienced high drop-off during tag upload, limiting content growth.
The Content team's KPIs (tag CTR, GMV attribution) conflicted with long-term UX improvements, creating organizational gridlock.

User research revealed the core issue: **users wanted to efficiently find products that fit their spaces**, but our solution—adding more tags—actually made the problem worse. We were optimizing for tag quantity when the real need was relevant, personalized discovery.

Meanwhile, the Recommendation ML team proposed adding Visual Search as a new feature, leveraging existing computer vision capabilities. However, their framing positioned it as an **incremental addition** rather than addressing the underlying tag dependency problem.

---

### **Actions**

Repositioned Visual Search by reframing it from "incremental feature" to **Phase 1 of a strategic transition toward AI-driven discovery**, partnering across Content, Search, ML, and Product teams.

- Deployed Visual Search in the **upload flow** (not search/browse) to reduce creator friction first, preventing direct competition with existing tag CTR while building organizational trust.

- Navigated Content team resistance by reframing the proposal: Visual Search would **expand discovery beyond what tags could cover**—unlocking products that weren't tagged—rather than replacing existing tags. Co-created guardrail metrics (maintain tag CTR, measure upload completion) and committed to weekly data reviews for transparency.

- Rather than waiting for full ML-driven personalization (which required significant investment), proposed testing a **proxy approach first**: high-signal products (most purchased, most saved, best-selling). This de-risked the hypothesis—"fewer, smarter tags"—before committing to larger ML investment.

- Framed the initiative as a **3-phase roadmap**: Phase 1 (creator friction removal) → Phase 2 (validate fewer tags) → Phase 3 (full personalization).

---

### **Results**

**Phase 1 Launch:**
Upload completion rate increased significantly, directly reducing creator friction.
Content uploads grew, expanding discoverable inventory without sacrificing tag CTR (maintained within guardrail).

**Phase 2 Validation:**
The proxy approach validated the core hypothesis—**fewer, smarter tags performed better**: GMV increased despite reduced tag volume, and guardrail metrics remained stable.
This proved that "tag quantity ≠ discovery quality" and secured organizational commitment to invest in true personalization and expand reduced-tag approach to other surfaces.

**Organizational Impact:**
Shifted Ohouse's product philosophy from "maximize tag impressions" to "maximize discovery confidence."
Established a validated roadmap for personalization investment and cross-surface tag reduction.
Search and Recommendation teams integrated Visual Search learnings into their own strategies.

---

### **Reflection**

Visual Search demonstrated that **strategic framing unlocks organizational investment**.

The challenge wasn't designing the feature—it was aligning teams with competing KPIs around a long-term vision.
By positioning the launch as Phase 1, reframing from "replace tags" to "expand discovery," and co-creating guardrail metrics with stakeholders, I transformed resistance into collaboration.

If I could redo this, I'd involve the Search team earlier—running parallel experiments would have validated the hypothesis faster and built more organizational momentum.
I'd also create more visceral customer evidence (videos of creators struggling with tags) to complement the data; emotion + data would have been more persuasive for skeptics.

More importantly, it established a repeatable pattern:
**When introducing transformative technology, protect existing value while building toward the future.**
This approach became a template for other AI-driven initiatives, showing how design leadership can navigate short-term business pressure without sacrificing strategic vision.

---

## **Interview Preparation: Potential Questions & Talking Points**

### **Q1: "You mentioned the Content team's KPIs conflicted with this initiative. Walk me through how you got them on board."**

**Why they'll ask:**
Leadership IC roles require navigating stakeholder conflict without direct authority. They want to see political savvy and coalition-building.

**Talking points:**
- **Acknowledge legitimate concern:** "The Content team's worry was valid—they owned GMV from content, and reducing tags felt like reducing revenue."
- **Reframing strategy:** "I reframed Visual Search from 'replace tags' to 'expand discovery.' Tags cover maybe 5-10 products per photo; Visual Search could surface any product visible in the image. This wasn't cannibalization—it was expansion."
- **Trust-building mechanism:** "We co-created guardrail metrics together. If tag CTR dropped beyond -5%, we'd pause. Weekly data reviews kept it transparent."
- **Outcome:** "By Phase 2, the Content team became champions—they saw GMV increase despite fewer tags and realized this validated their long-term strategy."

---

### **Q2: "Phase 2 showed GMV increased despite fewer tags. What would you do next if you were still there?"**

**Why they'll ask:**
Can you think beyond the current project? Do you see the broader strategic arc?

**Talking points:**
- **Phase 3 vision:** "True personalization—using ML to show different users different products based on browsing history, purchase behavior, and space style preferences."
- **Strategic sequencing:** "But before heavy ML investment, I'd expand Phase 2 learnings to other high-traffic surfaces: Search results, Home feed, Product Detail pages. Validate 'fewer, smarter tags' works at scale before committing infrastructure resources."
- **Success criteria:** "Prove that personalized tag reduction increases GMV across multiple surfaces, then build the business case for dedicated ML resources."
- **Why this matters:** "This is how you de-risk big bets—validate incrementally, build proof points, then scale investment."

---

### **Q3: "What would you do differently if you could do this project again?"**

**Why they'll ask:**
Self-awareness and learning orientation. Can you critique your own work?

**Talking points:**
- **Involve Search earlier:** "I'd run parallel experiments in Search alongside the upload flow. We siloed Phase 1 to reduce risk, but in retrospect, simultaneous testing would have validated the hypothesis faster and created more organizational momentum."
- **Make the problem more visceral:** "We had strong data, but I'd complement it with customer voice artifacts—videos of creators giving up during tag upload, user quotes about discovery frustration. Data convinces analysts; emotion + data convinces executives."
- **Prototype Phase 3 earlier:** "Even if we couldn't build full personalization immediately, I'd create a high-fidelity prototype to show stakeholders the end vision. It would have made the 3-phase roadmap feel more tangible."

---

### **Q4: "How did you decide to deploy in the upload flow instead of search or browse?"**

**Why they'll ask:**
They want to understand your strategic decision-making process and how you prioritize.

**Talking points:**
- **The alternatives:** "We had three options: (1) Search results (highest traffic), (2) Content Detail Page (direct tag competition), (3) Upload flow (lowest traffic but highest friction point)."
- **My reasoning:** "I chose upload flow because it addressed the root cause—creator friction—without threatening existing tag performance. If we launched in Search first, we'd be competing with tags immediately, triggering Content team resistance before proving value."
- **Strategic sequencing:** "By starting where we could win clearly (creator experience), we built proof points and trust before entering contested territory."
- **Pushback:** "The Search team wanted to start with Search results because of traffic volume. I convinced them that 'Phase 1 = validate, Phase 2 = scale' would ultimately get us there faster with less political friction."

---

### **Q5: "What did you learn about working with ML teams on this project?"**

**Why they'll ask:**
Tier 0 and Tier 1 companies want to know you understand AI/ML product challenges.

**Talking points:**
- **Designing ahead of capability:** "ML personalization wasn't ready for Phase 1. I learned to design for AI capabilities that don't exist yet—we validated the UX direction (fewer tags) while ML caught up."
- **Proxy strategies:** "When you can't wait for perfect ML, find a 'good enough' proxy. High-signal products (most purchased, saved, sold) approximated personalization and let us test the core hypothesis."
- **Setting realistic expectations:** "ML teams often focus on model accuracy; designers need to translate that into 'good enough for users.' We aligned on 'good enough to beat random tags' as our Phase 2 bar, not 'perfect personalization.'"
- **Cross-functional empathy:** "I learned to speak ML team's language—precision, recall, confidence scores—so we could have real tradeoff conversations instead of talking past each other."

---

### **Q6: "How would you apply this approach at [target company]?"**

**Why they'll ask:**
Can you translate your experience to their context?

#### **For Tier 0 (OpenAI, Anthropic, Perplexity):**
**Talking points:**
- "At an AI-first company, this approach scales: validate UX direction with proxy solutions while research/ML builds the real capability. Don't wait for perfect AI—ship 'good enough AI' that improves UX now."
- "The guardrail metrics model is critical for responsible AI. When deploying new models, define thresholds with stakeholders upfront: 'If accuracy drops below X, we roll back.' Build trust through transparency."
- "Visual Search taught me to design for progressive enhancement—baseline experience works without AI, enhanced experience unlocks with better models."

#### **For Tier 1 (AI startups):**
**Talking points:**
- "Startups need speed. Phase 2's proxy approach is classic startup thinking: validate cheaply before betting big. I'd apply this to any new AI feature—find the simplest version that tests the hypothesis."
- "At a startup, the Content team dynamic would be different—fewer silos, more direct decision-making—but the principle holds: protect existing value while building new value."
- "I'd move faster on Phase 3. At Ohouse, we were cautious; at a startup, I'd prototype full personalization in parallel with Phase 1 to compress the timeline."

#### **For Tier 2 (Meta, Netflix, Doordash):**
**Talking points:**
- "At scale, the hardest part isn't the design—it's aligning teams with different KPIs. The guardrail metrics framework became reusable for other high-risk initiatives at Ohouse."
- "I'd invest in design ops: document the playbook (reframe competition as expansion, co-create metrics, weekly transparency reviews) so other teams can run similar transitions independently."
- "At Meta/Netflix scale, I'd also think about regional rollout—test in one market, validate, then expand. The phased approach scales geographically too."

---

### **Q7: "Tell me about a time you had to choose between being 'right' and being 'a good leader.'"**

**Why they'll ask:**
Leadership IC roles require balancing conviction with collaboration.

**Talking points:**
- **The situation:** "I believed we should launch Visual Search in Search results first (highest traffic = fastest validation). But the Content team saw it as a direct threat to their KPIs."
- **The choice:** "I could have pushed my conviction—'I'm right, let's do Search first'—but that would have created lasting friction and potentially killed the project."
- **What I chose:** "I chose to be a good leader: start in upload flow (Content team's comfort zone), build trust, prove value, *then* expand to Search in Phase 2. It took longer, but we got there with the org aligned instead of divided."
- **What I learned:** "Being right doesn't matter if you can't bring people with you. Leadership is about finding paths that get to the right outcome while building coalition, not just asserting correctness."

---

### **Q8: "How would your team describe your leadership on this project?"**

**Why they'll ask:**
They want to understand your leadership style and self-awareness.

**Talking points (be authentic to your actual style):**
- **Strategic framing:** "They'd say I'm good at reframing problems—I took 'add Visual Search feature' and turned it into 'strategic transition roadmap,' which unlocked executive investment."
- **Stakeholder translator:** "I translate across functions—I helped designers understand Content team's GMV concerns and helped the Content team see how Visual Search expands (not threatens) their KPIs."
- **Risk mitigation:** "They'd say I'm cautious but pragmatic—Phase 1 in upload flow was lower-risk, but I pushed for Phase 2 proxy testing when full ML wasn't ready rather than waiting indefinitely."
- **Areas for growth:** "They might say I could move faster—I sequenced phases conservatively, but with hindsight, we could have parallelized more experiments."

---

### **Additional Talking Points to Have Ready:**

**On metrics:**
- Be ready to approximate numbers if asked: "Upload completion increased approximately 15-20%" or "Content uploads grew roughly 10-15% in the first quarter"
- If you don't have exact numbers: "At the time, we tracked upload completion rate and content volume growth, but I don't have the exact figures memorized. What I do remember clearly is that GMV increased in Phase 2 despite tag reduction, which was the critical proof point."

**On team development:**
- "I ran workshops with designers and ML team to build mutual understanding—designers learned about model confidence scores, ML team learned about UX degradation strategies."
- "This project helped junior designers learn stakeholder management—they saw firsthand how to navigate competing KPIs."

**On failure/struggle:**
- "Phase 1 took longer than expected because we underestimated the integration complexity with the existing tag system. Next time, I'd involve engineering earlier in scoping."
- "Some creators didn't adopt Visual Search immediately—we learned we needed better onboarding and education, not just launching the feature."

---

## **Key Messages to Reinforce:**

1. **"This wasn't about designing Visual Search—it was about aligning an organization with competing KPIs around a long-term vision."**

2. **"The hardest leadership challenge was transforming stakeholder resistance into collaboration through reframing, guardrail metrics, and transparency."**

3. **"Phase 2's proxy approach showed strategic pragmatism: validate hypotheses cheaply before betting big on ML investment."**

4. **"This established a repeatable pattern for introducing transformative technology: protect existing value while building toward the future."**

5. **"I learned that being right doesn't matter if you can't bring people with you—leadership is finding paths to the right outcome while building coalition."**
