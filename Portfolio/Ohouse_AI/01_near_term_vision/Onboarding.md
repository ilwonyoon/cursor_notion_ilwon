# PRD: Ohouse AI – Space Personalization Onboarding & Intent Capture (Prototype, Part 1)

## Product Overview

**Feature Name:** Ohouse AI – Space Personalization Onboarding & Intent Capture (Prototype, Part 1)

**Prototype Scenario:** Living Room (extensible to Bedroom, Home Office, Kitchen, etc.)

**One-line Description:** Users upload a space photo and answer two lightweight questions during AI analysis so that Ohouse AI can understand how they want to use the space and what feels most lacking, without adding friction to the experience.

**Owner:** AI Product Squad / Product Design (TBD)

**Status:** Prototype – near-term pitch, demo, and usability testing

### Scope of Part 1

This document covers only:
- Photo upload for a specified space
- AI analysis loading state
- Two-question intent capture (Role + Pain) during loading
- Basic interaction rules and data model for these questions
- Prototype uses "Living Room" as the test scenario

**Out of scope:**
- Downstream experiences such as category selection, personalized shopping home, inline surveys, and filters (Part 2)
- Multi-space flows and space-type selection (future iteration)

---

## Problem & Opportunity

### User Problems

**Users see many beautiful spaces online but struggle to:**
- Translate those ideas to their own space
- Know which problem to tackle first (ambiance, storage, layout, functionality, etc.)

**When personalization is missing or vague, the experience feels generic:**
- Recommendations are not clearly tied to how they live or what bothers them most

**Traditional forms or surveys feel heavy:**
- Users don't want to fill long forms before seeing value
- They are especially sensitive to friction right after upload

### Opportunity

**Use the AI analysis waiting time (15–20 seconds) as a natural moment to:**
1. Ask two simple questions about how they want to use their space
2. Capture what feels most lacking in the space

**Build a foundation for space-based personalization:**
- These two signals (Role + Pain) will drive later steps in Part 2:
  - Category prioritization
  - Section titles and copy
  - Product ranking and recommendations

**Improve perceived intelligence and empathy of Ohouse AI:**
- The system feels like it is listening to the user's needs, not just analyzing the photo

---

## Goals & Non-goals

### Goals (Part 1)

1. **Low-friction onboarding** – Let users upload a space photo and answer 2 questions without feeling like they are filling a form

2. **Capture high-signal intent** – Collect two key pieces of information during analysis:
   - **SpaceRole:** how they want to use the space
   - **SpacePain:** what feels most lacking right now

3. **Prepare for downstream personalization** – Ensure the captured data can be used by downstream systems (Part 2) to:
   - Select categories and sections
   - Generate copy that reflects the user's goals and pain

4. **Validate UX feasibility** – Confirm that users can comfortably answer 2 questions in ~15–20 seconds without confusion or drop-off

### Non-goals (Part 1)

- Defining or implementing category selection UI
- Designing the personalized space shopping home
- Implementing inline survey modules (budget, household, etc.)
- Full ML-based prioritization or ranking logic
- Space-type selection or multi-space onboarding flows

*(These items will be covered in PRD Part 2 and future iterations)*

---

## Target Users & Use Cases

### Target Users

- **Age:** 20–40
- **Context:** Has or is setting up a space with basic furniture (e.g., sofa, TV stand, bed, desk)
- **Pain:** Feels that the space is empty, unfinished, or not comfortable/functional enough

### Key Use Cases (for Part 1 – Living Room Prototype)

| Use Case | Scenario |
|----------|----------|
| **Empty but functional** | "I just moved in. I have a sofa and TV, but the room feels empty. I want it to feel cozy for family time and watching TV." |
| **Embarrassed to host** | "The living room works, but it looks unfinished. I feel shy inviting friends and want to improve it." |
| **Kids and safety/storage concerns** | "I have kids, toys, and clutter. I want a safer, more organized living room." |

*Part 1 focuses on how we ask and what we ask during the AI analysis phase to capture these space-specific needs. The system is designed to work with different space types (Bedroom, Home Office, Kitchen) in future iterations.*

---

## User Flow (Part 1)

```
1. Start Ohouse AI for a space
   └─ User taps an entry point (e.g., "Design my [space] with AI")

2. Upload or confirm space photo
   ├─ User takes a photo or selects one from the gallery
   └─ System validates that this is a room/indoor space image (basic checks for prototype)

3. Space analysis in progress (15–20 seconds)
   ├─ AI starts analyzing the photo
   └─ Two question blocks appear sequentially or stacked:
       ├─ Q1 – Space role (how they want to use it)
       └─ Q2 – Main pain point (what's missing)

4. Analysis completes
   ├─ Photo uploaded and analyzed
   ├─ SpaceRole and SpacePain captured (or empty if skipped)
   └─ Control passes to Part 2 flow (category selection and personalized shopping home)
```

---

## Detailed UX & Functional Requirements

### Step 1 – Greeting Message

**Entry Condition:** User has just tapped into the Ohouse AI space experience

**Goal:** Set a friendly, approachable tone and signal what's about to happen

**Copy & Tone:**
- Keep it short and casual (conversational, like advice from a friend)
- Signal the AI is here to help, not interrogate
- Set realistic expectations without overpromising
- Space-agnostic but can be contextual (e.g., "living room" for living room prototype)

**Primary Message:**

*"Hey! Let's find pieces that actually feel like you.*

*Show us a photo of your room, and AI will discover items that match your taste, then help you see how they'd look in your space.*

*Ready? Let's snap a photo or upload from your gallery."*

---

### Step 2 – Space Photo Upload

**Entry Condition:** User has opted into the Ohouse AI space experience

**Requirements:**
- Allow users to:
  - Take a new photo of their space, OR
  - Select an existing photo from their device
- Show a simple preview so users can confirm the photo
- **Basic validation** (lightweight for prototype):
  - If the image is clearly not an indoor space, show a gentle prompt
  - Example: *"This doesn't look like an indoor space. Please upload a photo of your room."*
- After confirmation, start analysis and transition to the loading + questions screen

---

### Step 3 – Room Analysis & Question Capture

**State:** AI is analyzing the uploaded room photo (target: 15–20 seconds)

#### Overall UX Principles

- The loading state should feel active and purposeful, not like a blank wait
- Question blocks must be:
  - Easy to understand at a glance
  - Answerable in a few seconds
  - Clearly skippable if the user doesn't want to answer

#### 3.1 Loading UI

**Components:**
- Visual loader (e.g., animated icon or subtle progress indicator)
- Context message:
  - *"While we understand your room, let me ask a couple of questions to get to know you better."*
- Short helper copy (mid-loading):
  - *"We're understanding your living room…"*
  - *"Analyzing your room and layout…"*

**Key principle:** The loader and questions should appear on the same screen so the user understands that:
- The system is working
- Their answers will help improve the result
- They're part of a collaborative process, not just waiting

---

#### 3.2 Question 1 – Space Role

**Goal:** Understand how the user wants to use this space in their daily life

**Copy:**
- **Title:** "What would you do here?"
- **Subtitle:** "Choose up to 2 that fit you best"

**Interaction:** Chip-style multi-select, maximum 2 selections

**Example Options (Living Room Prototype):**
- Unwind with family
- Have friends over
- Kids' playtime
- Movie nights
- Coffee & chat
- Study & work

**Copy Rationale:**
- **"What would you do here?"** – Activity-based framing helps users visualize real usage
- **"Fit you best"** – Empowering language that validates their actual lifestyle
- **Consistent option format** – All options use "verb + context" for easy scanning and selection


**UX Notes:**
- Chips should be ordered so the most common roles appear first
- Options should be contextualized by space type (Living Room ≠ Bedroom ≠ Home Office)
- When the user selects 2, additional taps should either:
  - Deselect the earliest selected chip, OR
  - Show a small toast: *"You can choose up to 2"*

---

#### 3.3 Question 2 – Main Pain Point

**Goal:** Capture what feels most lacking or frustrating in the current space

**Copy:**
- **Title:** "What's most lacking right now?"
- **Subtitle:** "Pick the one that feels true"

**Interaction:** Single-select chips

**Example Options (Living Room Prototype):**
- Feels too empty
- Doesn't feel cozy
- Storage & organization
- Lighting & windows
- Not kid-friendly
- Hesitant to have guests

**Copy Rationale:**
- **"What's most lacking right now?"** – Direct, concise (25 chars), validates frustration without judgment
- **"Pick the one that feels true"** – Matches Q1 subtitle style, simpler language
- **Consistent option format** – All parallel structure, balance of feeling-based and objective language
- **Clearer language** – "Lighting & windows" more specific than "Light / curtains are not right"

**UX Notes:**
- Options should be phrased in user language, not design jargon
- The emotional tone should be empathetic, not judgmental
- Pain points may vary by space type (Bedroom ≠ Home Office ≠ Living Room)

---

### Step 4 – Analysis Complete & Recommendation Message

**Goal:** Present AI analysis insights + room improvement suggestions based on photo + user intent

**Message:**

Here's what we found in your living room.

Your space has great natural light and a solid foundation—sofa and TV in the right spots. But the middle of the room feels empty, and the walls need some personality.

Based on wanting cozy family time, here's what could transform this:
- Soft rugs and throws to anchor the middle zone and make movie nights cozier
- Warm lighting around your sofa to soften the room
- Wall art or frames to give the blank walls some character

Let's build out these categories next.

**Copy Rationale:**
- **"Here's what we found"** – Collaborative tone, matches greeting message ("Hey! Let's find pieces")
- **"Solid foundation" + honest observations** – Empowering (confidence) + Honest (real observations)
- **Action-linked suggestions** – Each suggestion tied directly to user's stated intent (cozy family time)
- **"Let's build out"** – Maintains "we" collaborative energy into next step

---

### Step 5 – Category Selection

**Entry Condition:** User has reviewed analysis and improvement suggestions

**Goal:** Let user choose which product categories to focus on for this room

**Copy:**
- **Title:** "Which categories matter most for your living room?"
- **Subtitle:** "Pick up to 5. We'll create a personalized shopping page just for this room."

**Example Categories (Living Room):**
- Cushions & cushion covers
- Throws & blankets
- Rugs & carpets
- Curtains & blinds
- Floor & table lamps
- Wall art & frames
- Decorative objects
- Indoor plants & planters
- Sofa tables & coffee tables
- Lounge / accent chairs
- TV stands & media units
- Sideboards & consoles

**Interaction:**
- Multi-select with visible counter: "X of 5 selected"
- Primary CTA: "Create my shopping page" (enabled when ≥1 selected)
- Toast on 6th tap: "You can choose up to 5 categories"

---

### Step 6 – Personalized Shopping Home

**Entry Condition:** User has selected 1-5 categories

**Goal:** Show curated product recommendations aligned with room analysis + selected categories

**Page Structure:**

1. **Top context** – Room photo + room label + personalization subtitle
2. **Starter grid** – 4 high-priority product tiles (aligned with analysis + selections)
3. **Category carousels** – One horizontal carousel per selected category
4. **Smart recommendations** – Additional categories suggested by AI (e.g., storage if room is cluttered)
5. **Inline personalization** – Optional lightweight questions (budget, household type)

**Example Subtitle:**
*"Making your living room cozier for family time. Filtered by your selections."*

**Carousel Example – If user selected "Rugs & Carpets":**

*Title:* "Soft rugs to anchor your family zone"
*Subtitle:* "Warm, durable, easy to clean."
*Content:* 4-6 product cards in horizontal scroll

---

## Next Steps

- Prototype photo upload UX
- Design and test question flows with users
- Prepare for usability testing with Living Room scenario
- Document Part 2 requirements (category selection and personalized shopping home)
- Plan space-type expansion roadmap
