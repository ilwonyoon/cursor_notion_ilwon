# Ohouse AI Standalone App: Agentic Vision

## Context: Sequential Strategy for Global Impact

### Near-term (Korea, Existing User Base)
**Purpose:** Proof of concept + foundation tech validation
- Upload photo + 2 intent questions → AI generates personalized shopping home
- Primary goal: Validate AI reasoning, intent capture, and product matching at scale
- Market: Korea with 10M+ existing Ohouse users (CAC ~0)
- Timeline: 3-6 months to prove impact and iterate on tech quality

### Standalone (Global Expansion, New Users)
**Purpose:** New interaction model + TAM expansion
- Upload photo + conversation → AI proposes 3-4 complete designs → user gives feedback → iterate
- Primary goal: Create new experience for global market; reuse proven tech stack from near-term
- Market: Global (no existing user base; user acquisition required)
- Timeline: 6-12 months post near-term launch; leverages battle-tested foundation

### Design Philosophy Continuity
Both experiences share the same core principle: **"AI as proposer, user as evaluator"** (not "user as requester").

**Near-term:** Photo + explicit questions → AI proposes categories + products → user explores
**Standalone:** Photo + conversation → AI proposes complete designs → user iterates

Different interaction complexity, same behavioral shift. Standalone reuses proven tech (photo analysis, intent understanding, product matching) but applies it to a more ambitious interaction model.

**Why this sequence matters:**
- Near-term proves the tech works (Korean market, existing users)
- Standalone scales the model globally with lower risk (foundation already validated)
- Combined they position Ohouse as "AI-native design platform," not just e-commerce

---

# Part 1: Value Proposition

## The Behavioral Shift: Requesting → Evaluating

### Traditional Model (Today)
- **User effort**: Consume inspiration → Use tools → Manually request → Assemble pieces
- **User mental model**: "What should I ask for? How do I phrase this correctly?"
- **Creation mode**: Direct tool usage (e.g., Room Planner)

### Agentic Model (Standalone)
- **User effort**: Describe intent + upload room → Review proposals → Give feedback → Iterate
- **User mental model**: "What do I like/dislike? What should change?"
- **Creation mode**: Conversational co-creation with AI agent

### Core Value Shifts

| Dimension | Near-term (Feed) | Standalone (Agentic) |
|-----------|-----------------|----------------------|
| **User role** | Consumer/Curator | Decision maker/Evaluator |
| **AI role** | Recommender | Designer-like Agent |
| **Interaction** | Browse endless feed | Review bounded options + refine |
| **Effort model** | "Perfect my prompt" | "Give clear feedback" |
| **Outcome** | Inspiration | Actionable design + confidence |

### Why This Matters

1. **Reduced friction**: Users don't need to "figure out what to ask"
2. **Human agency**: Users maintain creative control through feedback loops
3. **Speed**: AI does creative heavy lifting; users focus on refinement
4. **Confidence**: Conversational iteration builds trust; voting adds reassurance

---

# Part 2: Key Flows to Create

## Flow 1: Agentic Reasoning & Design Generation

**What happens**: AI analyzes room + user goals, generates 3-4 design candidates

**Key design challenge**: Show meaningful progress without overwhelming users

**Implementation pattern** (inspired by Claude Code/Cursor):
- Display intermediate reasoning steps:
  - "Analyzing your room..." (space detection, furniture, zones)
  - "Exploring layout options..." (3 distinct directions)
  - "Matching products to your budget and taste..." (product sourcing)
- Build user confidence that real work is happening
- Avoid black-box spinner

**Output**: 3-4 complete design proposals ready for review

---

## Flow 2: Review & Understand AI Proposals

**What happens**: User sees each design with full context (products, materials, budget)

**Key information to expose**:
- Specific products being used
- Material options available
- Total spend ranges (not individual items)
- Actionable execution starting point

**Optional: Manual editing**
- Room Planner integration for users who want precise 3D adjustments
- Secondary tool, not primary interaction
- Used when users want fine-tuning or exact measurements

**Output**: User selects preferred direction(s) or identifies what they like/dislike

---

## Flow 3: Feedback Loop & Design Refinement

**What happens**: User gives feedback → AI regenerates designs → User evaluates → Repeat

**Feedback interaction patterns**:
- "I like this one, but the rug is too dark"
- "I love the lighting here, but the wall feels empty"
- "This layout feels cramped; can we open it up?"

**Memory & persistence**:
- System remembers user preferences across sessions
- Next round of proposals reflects evolving taste
- Creates long-term relationship, not one-shot interaction

**Termination state**: User has 4 final candidates but uncertain → needs external validation

**Output**: Refined designs + ready for confidence layer

---

## Flow 4: Voting & Crowd Confidence (Emotional Assurance)

**What happens**: User submits final candidates for community voting to build decision confidence

**Voting layer functions**:

1. **User benefit**: Emotional confidence
   - Submit final 4 candidates
   - Ask: "Which do you prefer?" / "Would you live here?"
   - Crowd feedback reassures decision

2. **Community benefit**: Incentivized participation
   - Voters earn free credits
   - Drives engagement with AI design exploration
   - Builds community loop

3. **Voter value**: Inspiration + curation
   - Access to multiple photo generations (with permission)
   - Save favorite designs into personal collections
   - Helps uncertain users browse + explore

4. **Business value**: Training data
   - Captures what designs resonate emotionally
   - Improves model understanding of taste/culture
   - Not just quantitative—captures emotional signal

**Output**: User gains confidence + makes final selection

---

# Part 3: Supporting Context

## Business Model

**Revenue streams**:
1. Subscription (unlimited or tiered design usage + advanced features)
2. Affiliate revenue (products purchased through flows)
3. Future: Ads/sponsored placements (non-intrusive)

**New TAM** beyond core commerce:
- Design assistance
- Decision confidence
- Execution guidance

---

## Design Principles

1. **Conversational, not transactional**: Feels like working with a designer, not a tool
2. **Bounded options, not endless browsing**: 3-4 designs vs. infinite feed
3. **Feedback is the core**, not prompting: User focuses on reaction, not phrasing
4. **Transparency + confidence building**: Show reasoning + leverage crowd
5. **Iteration without reset**: System learns from feedback across sessions

