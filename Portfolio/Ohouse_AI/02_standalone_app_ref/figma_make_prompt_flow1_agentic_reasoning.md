# Figma Make Prompt: Flow 1 - Agentic Reasoning Chat Experience

## Project Brief

Create a chat-based UI prototype showing how AI interior designer's reasoning progresses through 7 sequential steps (0-6) as it parses user intent and then analyzes a user's living room photo.

**Context:** This is Flow 1 (Agentic Reasoning & Design Generation) from Ohouse AI standalone vision. The user uploads a room photo + provides intent (Role + Pain), and the AI first confirms understanding of their intent (Step 0), then explains its thinking through 6 transparent reasoning steps (Steps 1-6) before transitioning to Flow 2 (showing 4 design proposals).

**Design System Reference:** Use the same design system defined in `figma_make_prompt_flow2_review_proposals.md` (iPhone 14 Pro viewport 390x844px, chat-based interface, color palette, typography).

---

## Key Content: 7 AI Reasoning Steps (0-6)

Each step is a separate bubble that appears sequentially in chat. Copy is directly from `AI_reasoning_instruction.md` Output Examples.

### **Step 0: Parse & Confirm User Intent**

**Bubble Label:** `CONFIRMING YOUR INTENT`

**Content (Example 1 - Clear Intent):**
```
You want me to make your living room warmer and cozier for family movie nights.
I'm sensing you like a cozy, intimate mood without it feeling cramped.
Let me analyze your space and create some designs that bring that warmth.
```

**Content (Example 2 - Unclear Intent):**
```
I want to make sure I understand—when you say "make it nice," are you picturing
something cozy and comfortable, sleek and modern, or colorful and playful?
That'll help me create exactly what you're envisioning.
```

**Visual Notes:**
- Question mark icon (16x16px, gray) next to step label (optional)
- Fade-in animation (0.4s)
- This step appears FIRST before Steps 1-6
- If intent is unclear, show Example 2 with options and wait for user clarification
- Once clarified, either return to Step 0 to confirm OR proceed to Step 1
- If intent is already clear (from onboarding), show Example 1 briefly then proceed

---

### **Step 1: Read Your Room**

**Bubble Label:** `STEP 1: READING YOUR ROOM`

**Content:**
```
I can see your living room with a gray sofa, TV on the right,
and open center space. Right now it feels a bit bare,
which is actually perfect—we have lots of room to add warmth
and personality.
```

**Visual Notes:**
- Eye icon (16x16px, gray) next to step label (optional)
- Fade-in animation (0.4s)

---

### **Step 2: Frame Your Goals & Constraints**

**Bubble Label:** `STEP 2: FRAMING YOUR GOALS`

**Content:**
```
So this is your family hangout where you want to relax and watch
movies together. I'll add warmth and texture while keeping the TV
view clear and the space open for the kids. Does that sound right?
```

**Visual Notes:**
- Target icon (16x16px, gray) next to step label (optional)
- Fade-in animation (0.4s, 1s delay from Step 1)

---

### **Step 3: Explore Layout & Style Options**

**Bubble Label:** `STEP 3: EXPLORING DIRECTIONS`

**Content:**
```
I'm thinking about three directions for your family space:

1. Cozy TV-focused layout with a large rug and warm lighting
   for movie nights
2. Open and playful—center stays free so the kids have room to move
3. Guest-friendly—add accent chairs so it works when people visit

Each balances your priorities differently. Let me turn these into
visual designs so you can see them in action.
```

**Visual Notes:**
- Compass icon (16x16px, gray) next to step label (optional)
- Numbered list (1. 2. 3.) indented 8px
- Fade-in animation (0.4s, 2s delay from Step 1)

---

### **Step 4: Match Products to Your Room**

**Bubble Label:** `STEP 4: SOURCING REAL PRODUCTS`

**Content:**
```
I'm pulling real products that match this direction. I'm looking at
rugs sized for your room, lamps that sit by the sofa without blocking
the TV, and cushions to warm up that gray sofa. I'm staying mid-range—
let me know if you want to go budget-friendly or upgrade to something
premium.
```

**Visual Notes:**
- Shopping bag icon (16x16px, gray) next to step label (optional)
- Fade-in animation (0.4s, 3s delay from Step 1)

---

### **Step 5: Show Design Options**

**Bubble Label:** `STEP 5: SHOWING DESIGN OPTIONS`

**Content:**
```
Here are four ways to design your living room, each balancing what you want.

• Option 1: Movie-night focused with a big rug and warm lights
• Option 2: Open and playful, keeping the middle free for the kids
• Option 3: Includes storage along the TV wall
• Option 4: Bolder colors and a fresher mood

What resonates? Feel free to tap any area if you want to adjust that part.
```

**Visual Notes:**
- Palette icon (16x16px, gray) next to step label (optional)
- Bullet points (•) for options, indented 16px
- Fade-in animation (0.4s, 4s delay from Step 1)

---

### **Step 6: Prepare Final Plan Summary**

**Bubble Label:** `STEP 6: PREPARING YOUR FINAL PLAN`

**Content:**
```
Here's your living room—we built on the cozy direction you liked
with a lighter rug and warmer lighting that brings out the family
warmth you wanted.

Key additions: Large rug (200×290cm), two floor lamps, wall art above
the sofa, toy storage along the TV wall.

Total: Around $1,200 (flexible—we can adjust by swapping items).

Below you'll see all the products. Ready to explore?
```

**Visual Notes:**
- Checkmark icon (16x16px, gray) next to step label (optional)
- "Key additions:" in bold
- "Total: Around $1,200" in bold green (#2E7D32)
- Fade-in animation (0.4s, 5s delay from Step 1)

---

## Flow Transition & Bottom CTA

**After Step 6 complete:**
- Show transition message: "Ready to show your 4 design options" (chat bubble)
- At bottom of chat: Primary CTA button
  - Text: "See 4 Design Options"
  - Style: #2E7D32 background, white text, full-width
  - On tap: Navigate to Flow 2 (Review Proposals)

---

## Figma Make Implementation

1. **Create reusable components:**
   - AI Chat Bubble (with step label + content)
   - Step Icon (small, gray, 16x16px)
   - Progress indicator (Step X/7 in header)

2. **Build 10 screens sequentially:**
   - Screen 1: Loading state ("Analyzing your room...")
   - Screen 2: Step 0 - Intent Confirmation (clear intent example)
   - Screen 3: Step 0 - Intent Clarification (unclear intent example with wait state)
   - Screen 4: Step 0 Clarified → Step 1 begins
   - Screens 5-9: Steps 1-6 appear one at a time
   - Screen 10: All steps visible + "See 4 Design Options" CTA

3. **Add animations:**
   - Each step fades in (0.4s ease-in)
   - Sequential delay: 0.8-1.2s between steps
   - Auto-scroll effect: Keep latest message visible
   - No typing animation (show final text)
   - Step 0 clarification can include a slight pause before auto-advancing

4. **Interactions:**
   - Screen 3 (unclear intent): Show user response field or button selection for clarification
   - Optional "Next Step" button to advance through screens OR
   - Auto-play all steps sequentially (with pause at Step 0 if clarification needed)

---

## Design Principles

These 7 steps (0-6) embed 3 core tone pillars:

✅ **Transparent:** Observation → Logic → Action shown in each step. Step 0 makes intent parsing visible.
✅ **Conversational:** Present continuous ("I'm thinking...", "I'm looking..."), personal pronouns ("we"). Step 0 clarifies without judgment.
✅ **Evidence-Based:** Each decision tied to user input (photo, stated goals, budget). Step 0 confirms intent before proceeding with analysis.

---

## Handoff to Flow 2

**End state of Flow 1:**
- User has seen all 6 reasoning steps in chat
- "Ready to show 4 design options" message visible
- CTA button: "See 4 Design Options"
- On tap → Flow 2 (2x2 grid of proposal thumbnails)
