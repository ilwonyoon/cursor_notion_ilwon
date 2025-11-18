# UX Writing DB – Ohouse AI Prototypes

## Overview

**Unified UX Copy Database for all Ohouse AI prototypes:**

### Scope
- **01. Near-term Vision:** Space Personalization Onboarding & Intent Capture (Prototype, Part 1)
- **02. Standalone App Reference:** AI Reasoning Experience
- **03. Property Tech Expansion:** Future prototype scope

### Tone Reference
- Friendly, Empowering, Honest (Ohouse UX Writing Principles)
- For AI Reasoning-specific tone: See `AI_reasoning_instruction.md` for Tone of Voice framework and LLM instructions

---

---

# Part 1: Near-term Vision – Onboarding Flow

**Prototype Scope:** Living Room (extensible to other space types)

---

## Step 1: Greeting

**Page ID:** `onboarding_greeting`
**Description:** Initial entry screen when user starts Ohouse AI space experience

| Copy Key | Component Type | Text Value | Tone Notes |
|----------|----------------|------------|-----------|
| `greeting_primary_message` | body | Hey! Let's find pieces that actually feel like you. Show us a photo of your room, and AI will discover items that match your taste, then help you see how they'd look in your space. Ready? Let's snap a photo or upload from your gallery. | Conversational, casual. Sets expectations without overpromising. Friendly + Empowering. |

---

## Step 2: Photo Upload

**Page ID:** `onboarding_photo_upload`
**Description:** Photo capture/upload screen with validation

| Copy Key | Component Type | Text Value | Tone Notes |
|----------|----------------|------------|-----------|
| `photo_validation_error` | toast | This doesn't look like an indoor space. Please upload a photo of your room. | Gentle, non-judgmental error message. Honest about limitation without blame. |

---

## Step 3: Loading & Questions

**Page ID:** `onboarding_loading_questions`
**Description:** AI analysis in progress with concurrent intent capture questions
**Tone:** Conversational + Transparent

### 3.1 Loading Context

| Copy Key | Component Type | Text Value | Tone Notes |
|----------|----------------|------------|-----------|
| `loading_context_message` | body | While we understand your room, let me ask a couple of questions to get to know you better. | Explains why questions appear during loading. Conversational tone ("let me ask"). |
| `loading_helper_1` | caption | We're understanding your living room… | Mid-loading helper text. Present continuous ("understanding") shows active work. |
| `loading_helper_2` | caption | Analyzing your room and layout… | Alternative helper text for variety. |

### 3.2 Question 1: Space Role

| Copy Key | Component Type | Text Value | Tone Notes |
|----------|----------------|------------|-----------|
| `q1_title` | heading | What would you do here? | Activity-based framing helps users visualize real usage. |
| `q1_subtitle` | caption | Choose up to 2 that fit you best | Empowering language ("fit you best") validates their actual lifestyle. |
| `q1_option_unwind_family` | chip | Unwind with family | Verb + context format for consistency and easy scanning. |
| `q1_option_have_friends` | chip | Have friends over | Verb + context format. |
| `q1_option_kids_playtime` | chip | Kids' playtime | Verb + context format. |
| `q1_option_movie_nights` | chip | Movie nights | Verb + context format. |
| `q1_option_coffee_chat` | chip | Coffee & chat | Verb + context format. |
| `q1_option_study_work` | chip | Study & work | Verb + context format. |
| `q1_max_selection_toast` | toast | You can choose up to 2 | Gentle limit reminder when user attempts 3rd selection. |

### 3.3 Question 2: Main Pain Point

| Copy Key | Component Type | Text Value | Tone Notes |
|----------|----------------|------------|-----------|
| `q2_title` | heading | What's most lacking right now? | Direct question that validates frustration without judgment. |
| `q2_subtitle` | caption | Pick the one that feels true | Matches Q1 subtitle style. Simpler, more conversational language. |
| `q2_option_too_empty` | chip | Feels too empty | Feeling-based language. User's emotional perspective. |
| `q2_option_not_cozy` | chip | Doesn't feel cozy | Feeling-based language. Matches user's pain. |
| `q2_option_storage` | chip | Storage & organization | Objective constraint-based language. |
| `q2_option_lighting` | chip | Lighting & windows | More specific than generic "light" - user language. |
| `q2_option_not_kid_friendly` | chip | Not kid-friendly | Specific constraint that shapes design. |
| `q2_option_guests` | chip | Hesitant to have guests | Emotional pain point. Validates social concern. |

---

## Step 4: Analysis Complete

**Page ID:** `onboarding_analysis_complete`
**Description:** AI presents room analysis and improvement suggestions based on photo + user intent
**Tone:** Empowering + Honest + Evidence-Based

| Copy Key | Component Type | Text Value | Tone Notes |
|----------|----------------|------------|-----------|
| `analysis_intro` | heading | Here's what we found in your living room. | Collaborative tone ("we found"). Specific to room type. |
| `analysis_observation` | body | Your space has great natural light and a solid foundation—sofa and TV in the right spots. But the middle of the room feels empty, and the walls need some personality. | Honest observation: acknowledges strengths first (Empowering), then real gaps (Honest). Specific to actual room observation. |
| `analysis_recommendations_intro` | body | Based on wanting cozy family time, here's what could transform this: | Links all suggestions back to user's stated intent from Q1. Evidence-based reasoning. |
| `analysis_recommendation_1` | list_item | Soft rugs and throws to anchor the middle zone and make movie nights cozier | Action-linked suggestion. Directly addresses "empty middle zone" observation. Tied to user's movie nights goal. |
| `analysis_recommendation_2` | list_item | Warm lighting around your sofa to soften the room | Addresses "needs personality" observation. Warm lighting = coziness (user's intent). |
| `analysis_recommendation_3` | list_item | Wall art or frames to give the blank walls some character | Directly solves "walls need personality" observation. |
| `analysis_cta` | body | Let's build out these categories next. | Maintains collaborative "we" energy. Conversational transition to next step. |

---

## Step 5: Category Selection

**Page ID:** `onboarding_category_selection`
**Description:** User chooses product categories to prioritize for their room
**Tone:** Empowering + Friendly

| Copy Key | Component Type | Text Value | Tone Notes |
|----------|----------------|------------|-----------|
| `category_title` | heading | Which categories matter most for your living room? | Personalized ("your living room"). Empowering by asking user to prioritize. |
| `category_subtitle` | caption | Pick up to 5. We'll create a personalized shopping page just for this room. | Clear benefit ("personalized shopping page") + clear limit ("up to 5"). |
| `category_counter` | caption | 0 of 5 selected | Real-time feedback as user selects. Shows progress. |
| `category_cta` | button | Create my shopping page | Primary action. "My" emphasizes personalization. |
| `category_max_selection_toast` | toast | You can choose up to 5 categories | Gentle limit reminder when user attempts 6th selection. |

**Category Options (Example):**
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

---

## Step 6: Personalized Shopping Home

**Page ID:** `onboarding_shopping_home`
**Description:** Curated product recommendations page aligned with room analysis + user selections
**Tone:** Empowering + Conversational

| Copy Key | Component Type | Text Value | Tone Notes |
|----------|----------------|------------|-----------|
| `shopping_home_page_title` | heading | Your Living Room | Personalized page title. Simple, user-focused. |
| `shopping_home_subtitle` | caption | Making your living room cozier for family time. Filtered by your selections. | Personalized with user's stated intent (cozy family time from Q1). Shows filtering is active. |
| `starter_grid_title` | heading | Start with these | Friendly, directional. Suggests entry point without being prescriptive. |
| `carousel_title_example_rugs` | heading | Soft rugs to anchor your family zone | Context-specific title. "Anchor" addresses "empty middle zone" from analysis. "Family zone" references user's intent. |
| `carousel_subtitle_example_rugs` | caption | Warm, durable, easy to clean. | Benefit-focused. "Easy to clean" addresses family with kids pain point (implied). |
| `carousel_title_example_lighting` | heading | Warm lighting to soften the room | Directly tied to analysis recommendation. "Soften" = coziness (user's goal). |
| `carousel_subtitle_example_lighting` | caption | Flexible options for your space. | Acknowledges room constraints. Empowering ("options"). |

---

## Tone Guidelines Applied

### Ohouse UX Writing Principles

All copy in this onboarding flow follows Ohouse's three core brand voices:

**1. Empowering (이끌어주는)**
- Build user confidence in decision-making
- Validate their actual lifestyle choices ("fit you best")
- Encourage exploration without pressure
- Examples: Q1 subtitle ("fit you best"), analysis strengths ("great natural light")

**2. Friendly (친근한)**
- Conversational, warm tone
- Like talking to a knowledgeable friend
- Keep language natural and easy to understand
- Examples: "Hey!", "Let's find pieces", "We're understanding your room"

**3. Honest (솔직한)**
- Transparent about limitations
- Provide genuine, trustworthy information
- Acknowledge challenges without sugarcoating
- Examples: Analysis observation ("middle feels empty"), error message (gentle validation failure)

### Connection to AI Reasoning

For AI-generated reasoning copy (Step 4 analysis messages), see `AI_reasoning_instruction.md` for:
- 3 Tone Pillars: Transparent, Conversational, Evidence-Based
- LLM Instructions for each step
- Consistency requirements across all 6 reasoning steps

---

## Notes for Implementation

### Dynamic Content Handling

The following copy blocks will be dynamically generated based on user input and AI analysis:
- `analysis_observation`: Room-specific (based on photo analysis)
- `analysis_recommendations_1-3`: Linked to user's SpaceRole + photo analysis
- `shopping_home_subtitle`: Includes user's SpaceRole from Q1
- Carousel titles/subtitles: Context-specific based on selected categories + analysis

### Space Type Extensibility

Current options for living room. For future space types (Bedroom, Home Office, Kitchen):
- Q1 options vary by space type
- Q2 pain points vary by space type
- Category options vary by space type
- All other structure and tone principles remain consistent

### User Flow Integration

This DB covers **Onboarding Part 1** (Steps 1-5).
**Part 2** (Personalized Shopping Home details) will have additional copy for:
- Inline surveys (budget, household type)
- Smart recommendations (AI-suggested categories)
- Product filtering and sorting copy

---

---

# Part 2: Standalone App Reference – AI Reasoning Flow

**Prototype Scope:** Reasoning steps 1-6 for the AI interior designer assistant
**Tone Reference:** Transparent, Conversational, Evidence-Based (See `AI_reasoning_instruction.md`)

---

## Step 1: Read Your Room

**Page ID:** `reasoning_step_1_read_room`
**Description:** AI observes the room and expresses its understanding to the user
**Tone:** Transparent + Conversational

| Copy Key | Component Type | Text Value | Tone Notes |
|----------|----------------|------------|-----------|
| `step1_observation_and_possibility` | body | I can see your living room pretty clearly now. You've got a gray sofa, the TV on the right, and that nice open center space. Right now it feels a bit bare, but that's actually perfect—we have lots of room to add warmth and texture without the space feeling cramped. | Shows observation → logic → possibility. Conversational tone ("that's actually perfect"). Connects observation to design potential. |

---

## Step 2: Frame Your Goals & Constraints

**Page ID:** `reasoning_step_2_frame_goals`
**Description:** AI reflects back the user's goals and constraints to show understanding
**Tone:** Conversational + Evidence-Based

| Copy Key | Component Type | Text Value | Tone Notes |
|----------|----------------|------------|-----------|
| `step2_brief_summary` | body | You told me this living room is for family movie nights and relaxing together. Right now it feels too empty and not cozy enough. So I'm focusing on adding warmth and texture while keeping the TV view clear and the space open for the kids. | Reflects back their role, pain, and constraints. Present continuous ("I'm focusing on") shows active reasoning. States constraints as part of solution, not restrictions. |

---

## Step 3: Explore Layout & Style Options

**Page ID:** `reasoning_step_3_explore_directions`
**Description:** AI presents multiple design directions with explicit trade-offs
**Tone:** Transparent + Conversational

| Copy Key | Component Type | Text Value | Tone Notes |
|----------|----------------|------------|-----------|
| `step3_directions_intro` | heading | I'm thinking about three directions for your family space | Present continuous, exploratory tone. |
| `step3_option_1` | list_item | **Cozy, TV-focused room** – Large rug and warm lights prioritizing your movie nights. | Bold label for clarity. States what direction prioritizes (movie nights). |
| `step3_option_2` | list_item | **Open and playful** – Center stays clear for the kids to move around freely. | Tied to their stated need (kids). |
| `step3_option_3` | list_item | **Guest-friendly** – Adds accent chairs for when you have people over, slightly more formal. | Addresses their secondary goal (guests). |
| `step3_balance_statement` | body | Each of these balances your needs differently. Let me turn these into visual designs so you can see them in action. | Explicitly frames trade-offs. Collaborative ("Let me turn these..."). |

---

## Step 4: Match Products to Your Room

**Page ID:** `reasoning_step_4_source_products`
**Description:** AI explains which product categories it's sourcing and why
**Tone:** Transparent + Evidence-Based

| Copy Key | Component Type | Text Value | Tone Notes |
|----------|----------------|------------|-----------|
| `step4_sourcing_intro` | body | I'm sourcing real products that match this direction. I'm looking at rugs that fit your room's center space, lamps for next to your sofa that won't block your TV view, and cushions to warm up that gray sofa. | Explains WHY each product category: room specs, constraints (TV sightline). Shows thinking linked to room analysis. |
| `step4_budget_explanation` | body | I'm staying in the mid-range because you didn't mention budget concerns, so this approach gives you good value without overcommitting. | Explains budget choice based on onboarding input. "Good value" = transparent reasoning. |

---

## Step 5a: Refine with Your Feedback – Intro

**Page ID:** `reasoning_step_5a_design_options`
**Description:** AI presents 4 design options with clear descriptions
**Tone:** Conversational + Evidence-Based

| Copy Key | Component Type | Text Value | Tone Notes |
|----------|----------------|------------|-----------|
| `step5a_intro_opening` | heading | Here are four ways to design your living room based on what you told me. Each one balances your needs differently. | Acknowledges user input. Frames trade-offs early. |
| `step5a_option_1` | list_item | **Option 1:** Movie-night focused – big rug and warm lights for comfort | Tied to their stated role. "for comfort" shows benefit. |
| `step5a_option_2` | list_item | **Option 2:** Open and playful – middle stays clear for the kids | Addresses their stated need. |
| `step5a_option_3` | list_item | **Option 3:** Organized – includes storage along the TV wall | Addresses implied pain point (empty, needs organization). |
| `step5a_option_4` | list_item | **Option 4:** Bolder style – more color and personality | Addresses "not cozy enough" pain point (personality/color). |
| `step5a_interaction_hint` | body | You can tap any area in each image to see more details or point out what appeals to you and what doesn't. | Clear interaction instruction. Invitation without interrogation. |

---

## Step 5b: Refine with Your Feedback – Response

**Page ID:** `reasoning_step_5b_feedback_response`
**Description:** AI acknowledges feedback and adjusts its design
**Tone:** Conversational + Evidence-Based + Transparent

| Copy Key | Component Type | Text Value | Tone Notes |
|----------|----------------|------------|-----------|
| `step5b_adjustment_response` | body | I'm keeping the open layout and rug from Option 2 since that's working well, and I'm adjusting the lamps and wall art to be warmer and softer. This brings together the openness you liked with the coziness you're after. | Acknowledges what's working. Describes specific adjustments. Ties changes to their stated preference ("openness you liked") + goal ("coziness you're after"). |

---

## Step 6: Prepare the Final Plan

**Page ID:** `reasoning_step_6_final_plan`
**Description:** AI summarizes the final design and connects it back to user's journey
**Tone:** Conversational + Evidence-Based + Transparent

| Copy Key | Component Type | Text Value | Tone Notes |
|----------|----------------|------------|-----------|
| `step6_celebration` | heading | Here's your transformed living room. We're building on the open, cozy direction you liked, with a lighter rug and warmer lighting that brings out the family warmth you wanted. | Celebrates transformation. "You liked", "you wanted" emphasizes their agency. References their original pain point (family warmth). |
| `step6_additions_title` | heading | The main additions | Clear section label. |
| `step6_addition_rug` | list_item | Large rug (200×290cm) to anchor the center and soften the space | Size + purpose. Shows how it solves "bare center" problem. |
| `step6_addition_lamps` | list_item | Two floor lamps for warmth and flexible lighting | Purpose tied to their goal (warmth) + functionality. |
| `step6_addition_art` | list_item | Wall art above the sofa to add personality and fill blank walls | Addresses "blank walls need character" observation from Step 1. |
| `step6_addition_storage` | list_item | Toy storage unit along the TV wall to keep things organized | Addresses functional need (organization) implied by "kids". |
| `step6_budget_label` | heading | Total budget | Clear section label. |
| `step6_budget_amount` | body | Around $1,200 (flexible—we can swap items to adjust up or down). Below you'll see all the products I selected. Everything's replaceable, so you have full control over the final picks. | Transparent about flexibility. Emphasizes user control ("you have full control"). |

---

## Tone Guidelines Applied: Part 2 (AI Reasoning)

### 3 Core Tone Pillars (AI Reasoning Specific)

**1. Transparent (투명성)**
- Every decision shows its reasoning: "I'm looking for [category] that [fits constraint]"
- Observation → Logic → Action chain is visible
- Trade-offs are explicitly named: "Each of these balances your needs differently"

**2. Conversational (대화식)**
- Present continuous tense ("I'm thinking...", "I'm focusing on...") to show active thought
- Reflects user's words back ("You told me...", "openness you liked")
- Avoids questions during reasoning (permission steps ask, not reasoning)
- Feels like thinking partner, not information delivery system

**3. Evidence-Based (근거 기반)**
- All decisions traceable to user input or room constraints
- Links back to their stated goals: "for family movie nights", "for the kids"
- Acknowledges their pain points: "family warmth you wanted", "fill blank walls"
- Each change explained with reason: "to anchor the center", "to add personality"

---
