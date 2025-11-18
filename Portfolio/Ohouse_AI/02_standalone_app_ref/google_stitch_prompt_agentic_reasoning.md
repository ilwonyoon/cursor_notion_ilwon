# Google Stitch Prompt: Agentic Reasoning Chat Experience (Static Mocks)

## Project Overview

Generate 6 static UI mockups showing the AI interior designer's reasoning progress through sequential steps in a chat-based interface. Each mockup represents a key moment in the reasoning flow as the AI analyzes a user's living room and prepares design proposals.

**Context:** Ohouse AI standalone vision - Flow 1 (Agentic Reasoning & Design Generation). User has uploaded a room photo and provided intent (family hangout, cozy).

---

## Design System & Constants

### Canvas & Viewport
- **Device:** iPhone 14 Pro
- **Screen size:** 390 x 844px
- **Safe area:** 40px horizontal padding (effective width: 310px)
- **Color scheme:**
  - Background: #FFFFFF
  - AI bubble bg: #F5F5F5
  - AI bubble border: #E0E0E0
  - User bubble bg: #E8F4F8
  - Text primary: #333333
  - Text secondary: #999999
  - Accent (budget): #2E7D32

### Typography Standards
- **Header:** 18px bold, #1A1A1A
- **Step title:** 11px all-caps bold, #999999, letter-spacing +0.5px
- **Body text:** 14px regular, #333333, line-height 1.6
- **Secondary text:** 12px regular, #999999

### Component Specs
- **Message bubble padding:** 16px
- **Bubble border-radius:** 16px
- **Bubble shadow:** 0px 2px 8px rgba(0,0,0,0.08)
- **Bubble margin-bottom:** 12px
- **Status bar height:** 44px
- **Header height:** 56px

---

## Mockup 1: Initial State - User Input & Loading

### Visual Description

**Header Section (Top 56px):**
- Title: "AI Room Designer" (left-aligned, 18px bold)
- Room indicator: "Living Room" with small room icon (12px gray text, right-aligned)
- Animated loading indicator: Pulsing dot (8px diameter, #2E7D32) + "Analyzing..."

**Chat Area:**
- One user message bubble (right-aligned, light blue #E8F4F8)
  - Content: Room photo thumbnail (200x150px, rounded 12px) centered in bubble
  - Text below photo: "Living room, empty but functional. Want family time + cozy." (14px, center-aligned)
  - Bubble max-width: 280px

- Below user message: Loading state message (left-aligned, AI bubble style)
  - Content: "Analyzing your room..." (14px)
  - Three-dot animated loader visible (represented as three static dots in stitch)

**Visual State:** Snapshot of "waiting for Step 1" - user has input, system is processing

---

## Mockup 2: Step 1 Complete - Read Your Room

### Visual Description

**Header Section:**
- Same as Mockup 1, but status changed to "Step 1/6 Complete"
- Loading indicator gone, small checkmark appears next to "AI Room Designer"

**Chat Area (Scrolled naturally, showing user input + Step 1):**

**User message bubble** (same as before, slightly faded/less prominent):
- Room photo thumbnail + user text

**AI Step 1 bubble** (left-aligned, fresh white #F5F5F5):
- Step label: "STEP 1: READING YOUR ROOM" (11px all-caps gray)
- Divider line below label (1px #F0F0F0)
- Content text:
  ```
  I can see your living room with a gray sofa, TV on the right,
  and open center space. Right now it feels a bit bare,
  which is actually perfect—we have lots of room to add warmth
  and personality.
  ```
  (14px, #333333, line-height 1.6)
- Small icon (optional): Eye icon (16x16px) next to step label, gray

**Visual State:** First reasoning step visible, chat naturally progresses downward

---

## Mockup 3: Step 2 Complete - Frame Goals & Constraints

### Visual Description

**Header:** Status "Step 2/6 Complete"

**Chat Area (Scrolled down, showing Steps 1-2):**

**Step 1 bubble** (visible above, slightly grayed out #FAFAFA background):
- Same as Mockup 2 but with reduced opacity (70%) to show it's "previous" content

**AI Step 2 bubble** (left-aligned, #F5F5F5):
- Step label: "STEP 2: FRAMING YOUR GOALS" (11px all-caps gray)
- Divider line
- Content text:
  ```
  So this is your family hangout where you want to relax and watch
  movies together. I'll add warmth and texture while keeping the TV
  view clear and the space open for the kids. Does that sound right?
  ```
  (14px, #333333, line-height 1.6)
- Small icon: Target icon (16x16px), gray

**Visual State:** Two steps visible in chat, natural conversation flow

---

## Mockup 4: Step 3 Complete - Explore Directions

### Visual Description

**Header:** Status "Step 3/6 Complete"

**Chat Area (Scrolled down, showing Steps 2-3):**

**Step 2 bubble** (visible above, faded #FAFAFA):
- Previous step, grayed out

**AI Step 3 bubble** (left-aligned, #F5F5F5):
- Step label: "STEP 3: EXPLORING DIRECTIONS" (11px all-caps gray)
- Divider line
- Content text with numbered list:
  ```
  I'm thinking about three directions for your family space:

  1. Cozy TV-focused layout with a large rug and warm lighting
     for movie nights
  2. Open and playful—center stays free so the kids have room
     to move
  3. Guest-friendly—add accent chairs so it works when
     people visit

  Each balances your priorities differently. Let me turn these
  into visual designs so you can see them in action.
  ```
  (14px body text, 13px for list items, indented 8px)
- Small icon: Compass icon (16x16px), gray

**Visual State:** Three directions clearly laid out, preparing for next step

---

## Mockup 5: Step 4 Complete - Source Products

### Visual Description

**Header:** Status "Step 4/6 Complete"

**Chat Area (Scrolled down, showing Steps 3-4):**

**Step 3 bubble** (visible above, faded #FAFAFA):
- Previous step, grayed out

**AI Step 4 bubble** (left-aligned, #F5F5F5):
- Step label: "STEP 4: SOURCING REAL PRODUCTS" (11px all-caps gray)
- Divider line
- Content text:
  ```
  I'm pulling real products that match this direction. I'm looking
  at rugs sized for your room, lamps that sit by the sofa without
  blocking the TV, and cushions to warm up that gray sofa. I'm
  staying mid-range—let me know if you want to go budget-friendly
  or upgrade to something premium.
  ```
  (14px, #333333)
- Small icon: Shopping bag icon (16x16px), gray

**Visual State:** Product sourcing logic visible, preparing for design visualization

---

## Mockup 6: Step 5 Complete - Show Design Options

### Visual Description

**Header:** Status "Step 5/6 Complete"

**Chat Area (Scrolled down, showing Steps 4-5):**

**Step 4 bubble** (visible above, faded #FAFAFA):
- Previous step, grayed out

**AI Step 5 bubble** (left-aligned, #F5F5F5, larger):
- Step label: "STEP 5: SHOWING DESIGN OPTIONS" (11px all-caps gray)
- Divider line
- Content text with bullet list:
  ```
  Here are four ways to design your living room, each balancing
  what you want.

  • Option 1: Movie-night focused with a big rug and warm lights
  • Option 2: Open and playful, keeping the middle free for
    the kids
  • Option 3: Includes storage along the TV wall
  • Option 4: Bolder colors and a fresher mood

  What resonates? Feel free to tap any area if you want to adjust
  that part.
  ```
  (14px for intro, 13px for bullets, bullet indent 16px)
- Small icon: Palette icon (16x16px), gray
- Visual note: This bubble is noticeably larger due to content volume

**Visual State:** Four distinct design options presented, ready for user feedback (though not interactive in static mock)

---

## Mockup 7: Step 6 Complete - Final Plan Summary

### Visual Description

**Header:** Status "Step 6/6 Complete - Ready to Explore"

**Chat Area (Scrolled down, showing Steps 5-6):**

**Step 5 bubble** (visible above, faded #FAFAFA):
- Previous step, grayed out

**AI Step 6 bubble** (left-aligned, #F5F5F5, prominent):
- Step label: "STEP 6: PREPARING YOUR FINAL PLAN" (11px all-caps gray)
- Divider line
- Content text:
  ```
  Here's your living room—we built on the cozy direction you liked
  with a lighter rug and warmer lighting that brings out the family
  warmth you wanted.

  Key additions: Large rug (200×290cm), two floor lamps, wall art
  above the sofa, toy storage along the TV wall.

  Total: Around $1,200 (flexible—we can adjust by swapping items).

  Below you'll see all the products. Ready to explore?
  ```
  (14px body text)
- Highlight: "Total: Around $1,200" in green (#2E7D32) bold
- "Key additions:" in bold (#333333)
- Small icon: Checkmark icon (16x16px), gray

**Visual State:** Complete reasoning shown, ready for next interaction (design viewing)

---

## Mockup 8: Full Chat History View (All Steps Visible)

### Visual Description

**Header:** Status "Ready to show 4 design options"

**Chat Area (Full scroll showing all steps at once - 2-3 steps visible at typical scroll depth):**

Show a "viewport" perspective showing:
- **Top:** User message bubble (partially visible, scrolled up)
- **Visible in viewport:**
  - Step 1 bubble (faded, reference)
  - Step 2 bubble (faded, reference)
  - Step 3 bubble (faded, reference)
  - Step 4 bubble (faded, reference)
  - Step 5 bubble (current focus, bright)
  - Step 6 bubble (below, fresh white)

**Bottom section:** Call-to-action area (below Step 6):
- Spacing: 16px
- Primary button: "See 4 Design Options" (full-width, rounded 8px, #2E7D32 background, white text, 16px bold)
- Secondary option: "Ask a question" (text link, #2E7D32, 14px)

**Visual State:** Complete chat history visible, user can see full reasoning path, ready to proceed to next flow

---

## Visual Styling Details

### Bubble Appearance
- **AI bubbles:**
  - Background: #F5F5F5
  - Border: 1px solid #E0E0E0
  - Shadow: 0px 2px 8px rgba(0,0,0,0.08)
  - Padding: 16px

- **User bubbles:**
  - Background: #E8F4F8
  - No border
  - Shadow: 0px 2px 8px rgba(0,0,0,0.08)
  - Padding: 16px

### Step Title Styling
- Font: 11px all-caps bold
- Color: #999999
- Letter-spacing: +0.5px
- Margin-bottom: 8px
- Divider line below: 1px #F0F0F0, margin-bottom 8px

### Body Text
- Font: 14px regular
- Color: #333333
- Line-height: 1.6
- Margin-bottom: 12px between bubbles

### Icon Placement
- Position: Left side of step label (8px before text)
- Size: 16x16px
- Color: #999999
- Icons: Eye, Target, Compass, Shopping Bag, Palette, Checkmark

---

## Interaction Notes (For Reference, Not in Static Mocks)

**In actual implementation, these moments would be interactive:**
- Step 2: Confirmation question "Does that sound right?" → [Yes] [Not exactly → Adjust]
- Step 4: Budget selection → [Budget-friendly] [Balanced] [Premium]
- Step 5: Tap design areas to refine → User feedback loop
- Step 6 / Mockup 8: CTA buttons are clickable

**For static mocks, these are represented as text without interactive state.**

---

## Copy Source

All reasoning text comes directly from `AI_reasoning_instruction.md` Step sections:
- Step 1: From "Output Example" section
- Step 2: From "Output Example" section
- Step 3: From "Output Example" section
- Step 4: From "Output Example" section
- Step 5: From "Output Example" section
- Step 6: From "Output Example" section

---

## Tone Principles Embedded in These Mocks

✅ **Transparent:** Each step shows observation → logic → action chain
✅ **Conversational:** Present continuous tense, personal pronouns, natural flow
✅ **Evidence-Based:** Each decision tied to user input or constraint
✅ **No Black Box:** Full reasoning visible in sequential chat
✅ **User-Centered:** Constant acknowledgment of user goals and room context

---

## Google Stitch Generation Instructions

1. **Generate 8 separate mockups** (Mockup 1-8 as described above)
2. **For each mockup:**
   - Use exact hex colors specified
   - Match typography (font sizes, weights, colors)
   - Maintain consistent spacing and component sizes
   - Show chat scrolling progression naturally (earlier steps fade out)
   - Include icons (or placeholder circles if icons unavailable)

3. **Quality checks:**
   - Each step's copy is readable and properly formatted
   - Bubble styles consistent across all mocks
   - Spacing and alignment professional
   - Text wrapping appropriate for 310px effective width
   - Icons and visual hierarchy clear

4. **Deliverable:**
   - 8 high-resolution PNG mockups (2x resolution for clarity)
   - Mobile-ready presentation
   - Ready to use in portfolio or presentation deck

---

## Success Criteria

When complete, the mockups should:
1. ✅ Show 6 sequential reasoning steps in chat format
2. ✅ Demonstrate natural chat scrolling (previous steps fade/gray out)
3. ✅ Use exact copy from AI_reasoning_instruction.md
4. ✅ Follow design system specifications precisely
5. ✅ Feel like conversation with a designer, not a report
6. ✅ Be mobile-appropriate (iPhone 14 Pro viewport)
7. ✅ Clearly show progression from Step 1 → Step 6
8. ✅ Include optional CTA buttons at the end (Mockup 8)

