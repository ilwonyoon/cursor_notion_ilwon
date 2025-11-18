# Figma Make Prompt: Agentic Reasoning Chat Experience

## Project Brief

Create a chat-based UI prototype showing how AI interior designer's reasoning progresses through 6 sequential steps as it analyzes a user's living room photo and generates design proposals.

**Context:** This is the "Agentic Reasoning & Design Generation" flow (Flow 1) from the Ohouse AI standalone vision. The user uploads a room photo, and the AI thinks out loud through 6 reasoning steps before presenting 3-4 design proposals.

---

## Design Requirements

### 1. Overall Layout & Structure

**Canvas Setup:**
- iPhone 14 Pro viewport (390 x 844px)
- Chat-based interface (similar to ChatGPT, Claude)
- Background: Clean white (#FFFFFF)
- User message bubbles: Right-aligned, light blue (#E8F4F8)
- AI message bubbles: Left-aligned, white with subtle border (#F5F5F5 background, #E0E0E0 border)

**Header:**
- Title: "AI Room Designer"
- Room context (optional): Displays "Living Room" + room photo thumbnail (80x80px, rounded corner)
- Status indicator: "Analyzing..." (animated pulsing dot) → "Ready to show options" (checkmark)

**Structure:**
- Top: Chat history area (scrollable)
- Middle: Sequential reasoning messages from AI
- Bottom: Action buttons (when reasoning complete)

---

### 2. User Input (Start)

**Screen State 1: User Uploads Photo & Answers Questions**

Show:
- User message bubble: (Room photo thumbnail 200x150px with rounded corners)
- User message: "Living room, empty but functional. Want family time + cozy."

*Note: This is the condensed version combining photo upload + intent answers (Role + Pain). For this prototype, assume the user has already provided this context.*

---

### 3. AI Reasoning: 6 Sequential Steps

Each step appears as an AI message bubble with:
- **Step title** (small, gray, all-caps: `STEP X: [TITLE]`)
- **Reasoning text** (body copy, readable, conversational)
- **Visual indicator** (animated progress or step counter)
- **Timing:** Each step reveals with a subtle fade-in animation

---

#### **Step 1: Read Your Room**

**Bubble content:**
```
STEP 1: READING YOUR ROOM

I can see your living room with a gray sofa, TV on the right,
and open center space. Right now it feels a bit bare,
which is actually perfect—we have lots of room to add warmth
and personality.
```

**Visual Details:**
- Bubble appears with fade-in (0.4s)
- Icon (optional): Eye icon or room icon (16x16px, gray)
- Text: Light gray (#666666), 14px, line-height 1.5
- No buttons/interactions yet

---

#### **Step 2: Frame Your Goals & Constraints**

**Bubble content:**
```
STEP 2: FRAMING YOUR GOALS

So this is your family hangout where you want to relax and watch
movies together. I'll add warmth and texture while keeping the TV
view clear and the space open for the kids. Does that sound right?
```

**Visual Details:**
- Bubble appears with fade-in (0.4s)
- Icon (optional): Target or blueprint icon
- Text: Same styling as Step 1
- **Interaction note:** This is where confirmation happens in real flow, but for prototype, no button—just text appears

---

#### **Step 3: Explore Layout & Style Options**

**Bubble content:**
```
STEP 3: EXPLORING DIRECTIONS

I'm thinking about three directions for your family space:

1. Cozy TV-focused layout with a large rug and warm lighting
   for movie nights
2. Open and playful—center stays free so the kids have room to move
3. Guest-friendly—add accent chairs so it works when people visit

Each balances your priorities differently. Let me turn these into
visual designs so you can see them in action.
```

**Visual Details:**
- Bubble appears with fade-in
- Icon: Compass or branching icon
- Text: Same styling
- Numbered list formatting (1. 2. 3.) indented slightly
- Each option on separate line for clarity

---

#### **Step 4: Match Products to Your Room**

**Bubble content:**
```
STEP 4: SOURCING REAL PRODUCTS

I'm pulling real products that match this direction. I'm looking at
rugs sized for your room, lamps that sit by the sofa without blocking
the TV, and cushions to warm up that gray sofa. I'm staying mid-range—
let me know if you want to go budget-friendly or upgrade to something
premium.
```

**Visual Details:**
- Bubble appears with fade-in
- Icon: Shopping bag or product icon
- Text: Same styling
- **Interaction note:** Budget selection happens here in real flow, but for prototype, no buttons yet

---

#### **Step 5: Refine with Your Feedback (Intro)**

**Bubble content:**
```
STEP 5: SHOWING DESIGN OPTIONS

Here are four ways to design your living room, each balancing what you want.

• Option 1: Movie-night focused with a big rug and warm lights
• Option 2: Open and playful, keeping the middle free for the kids
• Option 3: Includes storage along the TV wall
• Option 4: Bolder colors and a fresher mood

What resonates? Feel free to tap any area if you want to adjust that part.
```

**Visual Details:**
- Bubble appears with fade-in
- Icon: Palette or design icon
- Text: Same styling
- Bullet points (•) for each option
- **Visual separator:** Subtle divider line below this step

---

#### **Step 6: Final Plan Summary (Preview)**

**Bubble content:**
```
STEP 6: PREPARING YOUR FINAL PLAN

Here's your living room—we built on the cozy direction you liked
with a lighter rug and warmer lighting that brings out the family
warmth you wanted.

Key additions: Large rug (200×290cm), two floor lamps, wall art above
the sofa, toy storage along the TV wall.

Total: Around $1,200 (flexible—we can adjust by swapping items).

Below you'll see all the products. Ready to explore?
```

**Visual Details:**
- Bubble appears with fade-in
- Icon: Check mark or blueprint icon
- Text: Same styling
- Emphasize: "Key additions" in bold
- Budget amount highlighted (optional: different color, e.g., #2E7D32 green)

---

### 4. Interaction & Animation Requirements

**Sequential Appearance:**
- Each step appears one after another with a 0.8–1.2 second delay between steps
- Fade-in animation: 0.4s ease-in
- Scroll behavior: Auto-scroll to newest message (keep latest reasoning visible)

**Progress Indicator (Optional but Recommended):**
- Small step counter in top-right of header: "Step 1/6" → "Step 2/6" → ... → "Step 6/6"
- OR animated progress bar (thin line) at the bottom of chat area

**Loading State (While Analyzing):**
- Before Step 1 appears: Show loading message "Analyzing your room..." with animated three-dot loader
- Once Step 1 appears, loader disappears

**Chat Behavior:**
- Each new bubble pushes previous bubbles up (natural chat scroll)
- No "typing" indicator (we're showing final text, not letter-by-letter animation)
- Slight visual breathing room between steps (12px margin between bubbles)

---

### 5. Visual Hierarchy & Typography

**Header:**
- Title: 18px, bold (#1A1A1A)
- Room label: 12px, gray (#999999)

**Step Title:**
- 11px, all-caps, letter-spacing +0.5px, color #999999, font-weight 600

**Step Body Text:**
- 14px, regular weight (#333333), line-height 1.6
- Lists/options: 14px, indented 8px, bullet style

**Bubble Styling:**
- Padding: 16px
- Border-radius: 16px
- Shadow: Subtle (0px 2px 8px rgba(0,0,0,0.08))
- Max-width: 340px (leaving 25px margin on each side)

---

### 6. Color Palette

| Element | Color | Hex |
|---------|-------|-----|
| AI Bubble Background | Light Gray | #F5F5F5 |
| AI Bubble Border | Medium Gray | #E0E0E0 |
| User Bubble Background | Light Blue | #E8F4F8 |
| Text (Primary) | Dark Gray | #333333 |
| Text (Secondary) | Medium Gray | #999999 |
| Step Title Text | Gray | #999999 |
| Accent (Budget) | Green | #2E7D32 |
| Background | White | #FFFFFF |
| Border (Divider) | Light Gray | #F0F0F0 |

---

### 7. Prototype Flow (What to Show)

**Screen 1: Initial State**
- Header with "AI Room Designer" + loading indicator
- User message bubble (room photo + brief context)
- Loading message "Analyzing your room..."

**Screen 2-7: Steps Appear Sequentially**
- Each step reveals one at a time (Steps 1-6)
- Previous steps remain visible (chat scrolls naturally)
- After Step 6: Show "Ready to show design options" message

**Screen 8: Final State (Post-Reasoning)**
- All 6 steps visible in chat history
- At bottom: Action buttons (optional for this prototype):
  - Primary: "See 4 Design Options" (links to next flow)
  - Secondary: "Ask a question" (for conversation continuation)

---

### 8. Accessibility & Interaction Hints

**For Prototype:**
- No hover states needed (this is a read-through flow, not interactive)
- Each step is clearly numbered for easy reference
- Text contrast: All text meets WCAG AA standards (4.5:1 for body text)
- Font size: 14px minimum (readable on mobile)

**Responsive Note:**
- This prototype is designed for mobile (iPhone viewport)
- If adapted to desktop: Maintain max-width of 500px for chat bubbles for readability

---

## Figma Make Instructions

1. **Start with:** iPhone 14 Pro artboard
2. **Create components for:**
   - AI Message Bubble (reusable template)
   - Step Title (reusable, gray label)
   - User Message Bubble
   - Header with title + room context
   - Progress indicator

3. **Duplicate AI Bubble for each step:** Modify text content per step

4. **Add animations:**
   - Fade-in for each bubble (0.4s)
   - Sequential delay between steps (0.8–1.2s)
   - Auto-scroll chat (simulated by showing fixed "viewport" of 3-4 visible bubbles)

5. **Final deliverable:**
   - Interactive prototype showing sequential reveal of Steps 1-6
   - User can click through states (e.g., "Show next step" button) OR
   - Auto-play animation showing all steps revealing in sequence

---

## Design Principles Embedded in This Prototype

✅ **Transparent:** Each step shows thinking process (Observation → Logic → Action)
✅ **Conversational:** Present continuous tense ("I'm thinking...", "I'm looking..."), personal pronouns ("we")
✅ **Evidence-Based:** Each step tied to user input or constraint (photo analysis, stated goals, room specs)
✅ **No Black Box:** User sees all reasoning steps, not just final design
✅ **User Agency:** Step 2 & 4 have built-in confirmation/choice moments (even if not fully interactive in prototype)

---

## Optional Enhancements

**If time allows:**
- Add subtle icons for each step (eye, target, compass, cart, palette, checkmark)
- Show a small progress ring or step counter in top-right
- Add a "You can ask me questions" hint after Step 6 (contextual help)
- Simulate "room photo" as a small 80x80px thumbnail in the header that updates based on context

---

## Success Criteria

When complete, the prototype should:
1. ✅ Show all 6 reasoning steps in conversational chat format
2. ✅ Display steps sequentially with smooth fade-in animations
3. ✅ Keep previous steps visible (natural chat behavior)
4. ✅ Use the exact copy from AI_reasoning_instruction.md
5. ✅ Feel like a conversation with a designer, not a list or report
6. ✅ Be mobile-friendly (390px viewport)
7. ✅ Demonstrate the "Transparent + Conversational + Evidence-Based" tone pillars

