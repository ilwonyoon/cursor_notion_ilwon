좋아, 방향 정확히 이해했다.

* 목표: **“AI interior design reasoning” 경험을 정의하는 PRD (프로토타입용)**
* 포인트:

  * 구현 디테일(X), API 스펙(X)
  * **디자이너/PM이 플로우를 이해하고 프로토타입을 만들 수 있는 수준의 구조/단계/표현 방식(O)**

아래는 그 전제로 쓴 **Reasoning 전용 PRD 초안**이야.
(설명은 한글, 문서 본문은 영어로.)

---

# AI Interior Designer – Reasoning Experience PRD (Prototype)

---

### **AI Tone of Voice & LLM Instructions**

See detailed instructions in: `../04_src/AI_reasoning_instruction.md`

---

## 1. Purpose & Scope

**Purpose**

Define how the **AI interior designer’s reasoning process** is surfaced to users during the design flow, so that:

* Users feel like they are **working with a human-like interior designer**, not a black-box model.
* The reasoning process is **understandable, structured, and visually guided**, not just a spinner.
* Designers can build a **prototype flow** that shows intermediate “thinking steps” with the right mix of text, visuals, and product hints.

**Scope (for this PRD)**

* In-scope:

  * Reasoning steps from **after the user uploads room photos & answers initial questions**
    to **before/while showing design options and final plan**.
  * How the AI explains:

    * What it’s doing.
    * What it’s focusing on.
    * How it uses user goals/constraints.
  * What **content type** is shown at each step:

    * Text, reference images, product teasers, budget hints, etc.
  * Where to **ask for user confirmation or approval** in the reasoning flow.


## 2. High-Level Reasoning Journey (User Perspective)

From the user’s point of view, after they upload their room photo and tell us what they want, the AI should feel like a designer who:

1. **Reads the room**
2. **Frames the goals & constraints**
3. **Explores layout & style directions**
4. **Finds products that fit the room & budget**
5. **Presents and refines design options with feedback**
6. **Prepares a final plan with products & cost overview**

Each step:

* Has a clear **title** and **short explanation** in natural language.
* Is **adapted to the specific room and user goals** (not generic canned copy).
* May include **visual elements** (room photo, reference images, product previews).
* Sometimes asks the user to **confirm or adjust** the direction.

For the prototype, these steps can be shown in a **vertical timeline** or as **expandable reasoning cards**.

---

## 3. Reasoning Steps (Conceptual Pipeline)

### Step 1 – Read your room

**Goal**

Show that the AI has actually “looked at” and understood the user’s room.

**System Behavior (Conceptual)**

* Analyze the uploaded photo(s) to detect:

  * Room type and approximate size (e.g., compact / medium / large living room).
  * Key furniture and zones (sofa, TV, table, windows, empty areas).
  * Overall density (empty vs cluttered).
* Combine with any existing user context (if available):

  * Previous style preferences, budget band, household type, etc.

**User-Facing Copy (Dynamic)**

* Pattern (example):

  > "I can see your living room pretty clearly now. You've got a gray sofa, the TV on the right, and that nice open center space. Right now it feels a bit bare, but that's actually perfect—we have lots of room to add warmth and texture without the space feeling cramped."

* The wording should:

  * Refer to **visible elements** in the actual photo.
  * Connect observation to design possibility (opportunity framing).
  * Show the designer's thinking: observation → logic → potential.

**Media**

* Required:

  * Thumbnail of the uploaded room photo.
* Optional (prototype):

  * Simple overlays or tags (e.g., “Empty zone”, “Existing sofa”), even if static.

**User Interaction / Approval**

* No hard approval required here, but allow a light correction hook:

  * “Got it” / “That’s not accurate” buttons.
  * If “Not accurate”:

    * Open a small text/choice prompt:

      * “What did I misunderstand about your room?”

---

### Step 2 – Frame your goals & constraints

**Goal**

Let the AI “repeat back” the user’s goals, so the user feels understood and can correct the brief.

**System Behavior (Conceptual)**

* Use:

  * Declared intent from onboarding (e.g., `LivingRoomRole`, `LivingRoomPain`).
  * Any captured constraints (budget, kids/pets, style preferences).
* Summarize into a **designer-style brief**:

  * Room purpose.
  * Main issues.
  * Constraints (budget, kids, existing furniture to keep, etc.).

**User-Facing Copy (Dynamic)**

* Pattern (example):

  > "You told me this living room is for family movie nights and relaxing together. Right now it feels too empty and not cozy enough. So I'm focusing on adding warmth and texture while keeping the TV view clear and the space open for the kids."

* Must always:

  * Reflect back the **primary role** of the room.
  * Acknowledge the **pain point**.
  * State **design constraints** as part of the approach (not as restrictions).
  * Use present continuous ("I'm focusing on...") to show active reasoning.

**Media**

* Mostly text.
* Optional tags/chips to visually summarize:

  * `#Family time` `#Too empty` `#Cozy` `#Kids-friendly`

**User Interaction / Approval (Required)**

* Explicit confirmation:

  * CTA:

    * **Primary:** “Yes, that’s right”
    * **Secondary:** “Not exactly → Adjust it”

* On “Adjust it”:

  * Quick inline controls, e.g.:

    * “Make it more for: [Kids] [Adults] [Guests]”
    * “What matters more? [Comfort] [Storage] [Budget] [Style]”

The goal: this step acts as a **brief confirmation checkpoint** before deeper reasoning.

---

### Step 3 – Explore layout & style options

**Goal**

Communicate that the AI is exploring **multiple conceptual directions**, not just one random layout.

**System Behavior (Conceptual)**

* Internally generate 2–3 conceptual directions:

  * Layout focus (TV-centered, conversation-centered, kids zone, etc.).
  * Style direction (warm minimal, soft Nordic, playful, etc.).
* These do **not** need to be full images yet; they are concept “slots”.

**User-Facing Copy (Dynamic)**

* Pattern (example):

  > "I'm thinking about three directions for your family space:
  >
  > 1. **Cozy, TV-focused room** – Large rug and warm lights prioritizing your movie nights.
  > 2. **Open and playful** – Center stays clear for the kids to move around freely.
  > 3. **Guest-friendly** – Adds accent chairs for when you have people over, slightly more formal.
  >
  > Each of these balances your needs differently. Let me turn these into visual designs so you can see them in action."

* Room- and goal-specific:

  * State what each direction **prioritizes** (not just lists features).
  * Explicitly frame **trade-offs** ("each balances your needs differently").
  * Connect to their stated goals (movie nights, kids, guests, etc.).

**Media**

* Optional reference visuals (recommended for prototype):

  * 1–3 reference room images that roughly match the described directions.
  * These are **inspiration** only, not the exact final render.

**User Interaction / Approval (Optional, nice-to-have)**

* v1 (simpler):

  * No mandatory selection, just show that exploration is happening.
* v2 (richer):

  * Quick preference question:

    * “Which direction feels closest to what you want?”
      → Option 1 / 2 / 3
  * Use this as a soft weighting for later designs.

---

### Step 4 – Match products to your room

**Goal**

Show that the AI is now grounding ideas in **real products and budget**, not just abstract style.

**System Behavior (Conceptual)**

* For each conceptual direction (or the chosen one):

  * Identify “slots” (rug, lamps, cushions, storage, wall art, etc.).
* Query product catalog:

  * Fit room size and layout (rug dimensions, lamp height, etc.).
  * Respect budget band (if known or chosen).
  * Optionally favor certain style tags.

**User-Facing Copy (Dynamic)**

* Pattern (example):

  > "I'm sourcing real products that match this direction. I'm looking at rugs that fit your room's center space, lamps for next to your sofa that won't block your TV view, and cushions to warm up that gray sofa. I'm staying in the mid-range because you didn't mention budget concerns, so this approach gives you good value without overcommitting."

* Must convey:

  * What categories are being sourced and **why** they fit this room/direction.
  * How **constraints** (room size, TV sightline, budget) drive product selection.
  * The reasoning behind the **budget band choice**.

**Media**

* Small teaser preview:

  * 3–5 product thumbnails (no need for full carousels here):

    * Example: 2 rug options, 1–2 lamps, 1 cushion.
  * Show indicative **price range** (e.g., “Rugs from $150–$250”).

**User Interaction / Approval (Recommended)**

* Simple budget confirmation (if not already set):

  * Title:

    * “Want me to match your budget for this room?”
  * Options:

    * [Save money] / [Balanced] / [Premium]

* This choice becomes `BudgetBand` and influences later steps.

---

### Step 5 – Refine with your feedback (incl. image selector)

**Goal**

Make feedback the **center of the agentic loop**, not prompt engineering.

**System Behavior (Conceptual)**

* Generate 3–4 visual design options for the room.
* For each option, keep metadata:

  * What layout choice it represents.
  * Which key products are included.
  * Which zones are most changed.

**User-Facing Copy (Dynamic)**

* Intro text:

  > "Here are four ways to design your living room based on what you told me. Each one balances your needs differently.
  >
  > • **Option 1:** Movie-night focused – big rug and warm lights for comfort
  > • **Option 2:** Open and playful – middle stays clear for the kids
  > • **Option 3:** Organized – includes storage along the TV wall
  > • **Option 4:** Bolder style – more color and personality
  >
  > You can tap any area in each image to see more details or point out what appeals to you and what doesn't."

* After user feedback (inline):

  > "I'm keeping the open layout and rug from Option 2 since that's working well, and I'm adjusting the lamps and wall art to be warmer and softer. This brings together the openness you liked with the coziness you're after."

**Media**

* 3–4 **generated design images** (for the current room).
* **Inline image selector**:

  * Users can tap/drag to select a specific region.
  * That triggers a focused feedback prompt:

    * “What would you like to change about this area?”
* Optional chips under each image:

  * `Keep layout` / `Change colors` / `More storage` / `Too busy` etc.

**User Interaction / Approval**

* This step is the **main interaction hub**:

  * Users choose:

    * A preferred option (or top 2).
    * Specific areas to adjust (using image selector).
  * System loops:

    * Show updated designs.
    * Narrate what it changed and what stayed.

For the prototype, it’s enough to:

* Show:

  * 4 images.
  * A simple tap-to-comment region.
  * A “Regenerate with my feedback” button.

---

### Step 6 – Prepare the final plan

**Goal**

Summarize the **final result** clearly and connect it to products and execution.

**System Behavior (Conceptual)**

* Choose a “final” design option (or user’s selected favorite).
* Gather:

  * Product list.
  * Total budget range.
  * Key changes vs original room.
* Optionally suggest a step-by-step execution plan.

**User-Facing Copy (Dynamic)**

* Pattern (example):

  > "Here's your transformed living room. We're building on the open, cozy direction you liked, with a lighter rug and warmer lighting that brings out the family warmth you wanted.
  >
  > **The main additions:**
  > • Large rug (200×290cm) to anchor the center and soften the space
  > • Two floor lamps for warmth and flexible lighting
  > • Wall art above the sofa to add personality and fill blank walls
  > • Toy storage unit along the TV wall to keep things organized
  >
  > **Total budget:** Around $1,200 (flexible—we can swap items to adjust up or down). Below you'll see all the products I selected. Everything's replaceable, so you have full control over the final picks."

**Media**

* Final design image.
* Product list with prices.
* Budget summary (min–max range or typical total).

**User Interaction / Approval**

* “Save this plan”
* “I want to tweak more” → goes back to Step 5 loop.

---

## 4. Tone & Style Guidelines for Reasoning

To make this feel like a designer, not a log viewer:

* **Do NOT** show:

  * Raw code, JSON, or tool invocation details.
  * “step_1_analyze_room()” style logs.
* **DO**:

  * Use natural, conversational language.
  * Speak like a professional but friendly interior designer:

    * “I’m thinking…”, “This will help…”, “I’ll focus on…”
  * Always tie reasoning back to:

    * Their room.
    * Their goals.
    * Their constraints.

**References**

* Inspired by:

  * Claude Code: multi-step reasoning shown as human-readable plan.
  * Cursor: compact, understandable progress display.
* But adapted to:

  * Interior design domain.
  * Visual + product + budget context.
  * “Explaining the design process” rather than “debugging code”.

---

## 5. Prototype Requirements (Design-First)

For the prototype, we do **not** need the full backend implementation. We need:

* Screen flows / states for:

  * Each of the 6 reasoning steps as **UI states**.
  * How the reasoning text and visuals appear sequentially.
  * Where user can confirm/adjust (Step 2, Step 4) and give feedback (Step 5).
* Example content:

  * 1–2 realistic dynamic copy examples per step (can be hand-crafted).
  * 1–2 reference images and product thumbnails as placeholders.

The goal is to enable:

* A clickable prototype where:

  * You upload a “fake” room.
  * You see reasoning steps unfold.
  * You can play through:

    * “Designer explains → user confirms → designer explores → designer proposes → user gives feedback → final plan.”

---

원하면 다음 단계로:

* 이 Reasoning PRD를 **기존 Ohouse AI PRD 문서의 한 섹션으로 합치는 버전**
  또는
* 이걸 기반으로 **피그마 플로우용 “화면 리스트 + 상태 전환 다이어그램”** 형태로 정리해 줄 수 있다.

어느 쪽으로 먼저 이어갈지 말해주면, 바로 그 방향으로 깔끔하게 재구성해줄게.
