# PRD: Ohouse AI – Space Personalization Onboarding & Intent Capture (Prototype, Part 1)

## 1. Product Overview

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

## 2. Problem & Opportunity

### 2.1 User Problems

**Users see many beautiful spaces online but struggle to:**
- Translate those ideas to their own space
- Know which problem to tackle first (ambiance, storage, layout, functionality, etc.)

**When personalization is missing or vague, the experience feels generic:**
- Recommendations are not clearly tied to how they live or what bothers them most

**Traditional forms or surveys feel heavy:**
- Users don't want to fill long forms before seeing value
- They are especially sensitive to friction right after upload

### 2.2 Opportunity

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

## 3. Goals & Non-goals

### 3.1 Goals (Part 1)

1. **Low-friction onboarding** – Let users upload a space photo and answer 2 questions without feeling like they are filling a form

2. **Capture high-signal intent** – Collect two key pieces of information during analysis:
   - **SpaceRole:** how they want to use the space
   - **SpacePain:** what feels most lacking right now

3. **Prepare for downstream personalization** – Ensure the captured data can be used by downstream systems (Part 2) to:
   - Select categories and sections
   - Generate copy that reflects the user's goals and pain

4. **Validate UX feasibility** – Confirm that users can comfortably answer 2 questions in ~15–20 seconds without confusion or drop-off

### 3.2 Non-goals (Part 1)

- Defining or implementing category selection UI
- Designing the personalized space shopping home
- Implementing inline survey modules (budget, household, etc.)
- Full ML-based prioritization or ranking logic
- Space-type selection or multi-space onboarding flows

*(These items will be covered in PRD Part 2 and future iterations)*

---

## 4. Target Users & Use Cases

### 4.1 Target Users

- **Age:** 20–40
- **Context:** Has or is setting up a space with basic furniture (e.g., sofa, TV stand, bed, desk)
- **Pain:** Feels that the space is empty, unfinished, or not comfortable/functional enough

### 4.2 Key Use Cases (for Part 1 – Living Room Prototype)

| Use Case | Scenario |
|----------|----------|
| **Empty but functional** | "I just moved in. I have a sofa and TV, but the room feels empty. I want it to feel cozy for family time and watching TV." |
| **Embarrassed to host** | "The living room works, but it looks unfinished. I feel shy inviting friends and want to improve it." |
| **Kids and safety/storage concerns** | "I have kids, toys, and clutter. I want a safer, more organized living room." |

*Part 1 focuses on how we ask and what we ask during the AI analysis phase to capture these space-specific needs. The system is designed to work with different space types (Bedroom, Home Office, Kitchen) in future iterations.*

---

## 5. User Flow (Part 1)

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

## 6. Detailed UX & Functional Requirements

### 6.0 Step 0 – Greeting Message

**Entry Condition:** User has just tapped into the Ohouse AI space experience

**Goal:** Set a friendly, approachable tone and signal what's about to happen

**Copy & Tone:**
- Keep it short and casual (1-2 sentences max)
- Signal the AI is here to help, not interrogate
- Set expectation: photo → AI analysis → personalization
- Space-agnostic but can be contextual (e.g., "living room" for living room prototype)

**Examples:**
- *"Hey! Let's make your space amazing. First, snap a photo."*
- *"Ready to transform this space? Show me what you're working with."*
- *"Let's find the perfect pieces for your space. First, let's see it."*

**Design Pattern:**
- Simple heading or hero message
- Optional: light icon or subtle animation
- Single CTA button: "Take a Photo" or "Choose from Gallery"
- Dismissible or auto-transitions after brief display

---

### 6.1 Step 1 – Space Photo Upload

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

### 6.2 Step 2 – Space Analysis & Question Capture

**State:** AI is analyzing the uploaded space photo (target: 15–20 seconds)

#### Overall UX Principles

- The loading state should feel active and purposeful, not like a blank wait
- Question blocks must be:
  - Easy to understand at a glance
  - Answerable in a few seconds
  - Clearly skippable if the user doesn't want to answer

#### 6.2.1 Loading UI

**Components:**
- Visual loader (e.g., animated icon or subtle progress indicator)
- Short helper copy:
  - *"We're understanding your living room…"*
  - *"Analyzing your space and layout…"*

**Key principle:** The loader and questions should appear on the same screen so the user understands that:
- The system is working
- Their answers will help improve the result

---

#### 6.2.2 Question 1 – Space Role

**Goal:** Understand how the user wants to use this space in their daily life

**Copy:**
- **Title:** "What kind of space do you want?"
- **Subtitle:** "You can choose up to 2"

**Interaction:** Chip-style multi-select, maximum 2 selections

**Example Options (Living Room Prototype):**
- Family relaxation space
- A place to host guests
- Kids' play zone
- TV & movie space
- Home café & conversation
- Work & study corner

**Data Model:**
- **Field:** `SpaceRole`
- **Type:** Array of enums
- **Max length:** 2
- **Possible values (extensible by space type):**
  - `FAMILY_RELAX`
  - `HOST_GUESTS`
  - `KIDS_PLAY`
  - `TV_MOVIE`
  - `CAFE_CHAT`
  - `WORK_STUDY`
  - *(Other roles for different space types in future iterations)*

**UX Notes:**
- Chips should be ordered so the most common roles appear first
- Options should be contextualized by space type (Living Room ≠ Bedroom ≠ Home Office)
- When the user selects 2, additional taps should either:
  - Deselect the earliest selected chip, OR
  - Show a small toast: *"You can choose up to 2"*

---

#### 6.2.3 Question 2 – Main Pain Point

**Goal:** Capture what feels most lacking or frustrating in the current space

**Copy:**
- **Title:** "What feels most lacking in this space right now?"
- **Subtitle:** "Choose the one that feels most true"

**Interaction:** Single-select chips

**Example Options (Living Room Prototype):**
- It feels too empty
- It doesn't feel cozy enough
- Storage & organization is hard
- Light / curtains are not right
- It doesn't feel kid-friendly
- I feel shy inviting guests

**Data Model:**
- **Field:** `SpacePain`
- **Type:** Enum
- **Possible values (extensible by space type):**
  - `TOO_EMPTY`
  - `NOT_COZY`
  - `STORAGE_HARD`
  - `LIGHT_ISSUE`
  - `NOT_KID_FRIENDLY`
  - `EMBARRASSED_TO_HOST`
  - *(Other pain points for different space types in future iterations)*

**UX Notes:**
- Options should be phrased in user language, not design jargon
- The emotional tone should be empathetic, not judgmental
- Pain points may vary by space type (Bedroom ≠ Home Office ≠ Living Room)

---

#### 6.2.4 Interaction Rules (Both Questions)

**Visibility & Timing:**
- Both questions are shown while analysis is running
- If analysis finishes before the user answers:
  - Keep the questions visible until they respond or skip
  - Show a subtle message: *"Your space is ready. You can answer these to improve recommendations or skip for now."*

**Skipping Behavior:**
- Allow the user to skip each question (e.g., "Skip for now")
- If both are skipped:
  - `SpaceRole` and `SpacePain` remain empty / null
  - Downstream logic (Part 2) will fall back to generic defaults

**Partial Answers:**
- **If only Q1 is answered:** Use `SpaceRole` for downstream logic, leave `SpacePain` null
- **If only Q2 is answered:** Use `SpacePain`, and treat Role as unknown

**Completion:**
- When analysis is done and the questions are answered or skipped:
  - Proceed to Part 2 entry point (category selection and personalized shopping home)

---

## 7. Data & Analytics (Part 1)

### 7.1 Events to Track

**Key questions:**
- Can users answer these questions easily during loading?
- Do the questions create friction?

**Minimum events:**
- `ai_space_onboarding_start` – user starts the Ohouse AI space onboarding flow
- `ai_space_photo_uploaded` – photo upload completed
- `ai_space_q1_role_answered` – with selected options
- `ai_space_q2_pain_answered` – with selected option
- `ai_space_q1_skipped` / `ai_space_q2_skipped`
- `ai_space_analysis_complete` – analysis finished
- `ai_space_onboarding_part1_complete` – user transitions to Part 2

### 7.2 Metrics to Observe (for Learning)

- % of users who answer Q1
- % of users who answer Q2
- % of users who skip both
- Time to first answer
- Drop-off rate during analysis

**Note:** These are not hard KPIs yet but should inform whether:
- The questions are understandable
- The load-time UX feels acceptable or needs adjustment

---

## 8. Edge Cases & Constraints (Part 1)

### 8.1 Edge Cases

| Edge Case | Handling |
|-----------|----------|
| **User cancels upload mid-way** | Return to previous screen without storing partial data |
| **Poor or invalid photo** | For the prototype, show a lightweight error and let the user retry |
| **Analysis takes longer than expected (e.g., > 25s)** | Keep loader running, ensure the user can still answer or skip questions, and show a soft message like *"This is taking a bit longer than usual."* |
| **User leaves before completing onboarding** | Save `SpaceRole` and `SpacePain` data captured so far; allow resumption |

---

## 9. Future Considerations (Beyond Part 1)

- **Multi-space support:** Extend onboarding flow to handle Bedroom, Home Office, Kitchen, etc.
- **Space-type contextualization:** Customize Q1 and Q2 options based on space type
- **Smart defaults:** Infer space type from photo if possible (e.g., detect bed → Bedroom)
- **Advanced analytics:** User segment analysis based on Role + Pain combinations
- **Progressive disclosure:** Surface follow-up questions in Part 2 based on Part 1 answers

---

## Next Steps

- Prototype photo upload UX
- Design and test question flows with users
- Prepare for usability testing with Living Room scenario
- Document Part 2 requirements (category selection and personalized shopping home)
- Plan space-type expansion roadmap
