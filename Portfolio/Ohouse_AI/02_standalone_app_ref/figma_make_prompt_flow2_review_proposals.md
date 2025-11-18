# Figma Make Prompt: Flow 2 - Review & Understand AI Proposals

## Project Brief

Create an interactive Figma prototype showing how users review and explore 4 AI-generated design proposals. The flow includes:
1. Chat context + 2x2 grid of design thumbnails
2. Grid interaction (tap any design)
3. Full-page detail view with design information (products, budget, materials)
4. Navigation between design options

**Context:** Ohouse AI standalone vision - Flow 2 (Review & Understand AI Proposals). After AI completes 6 reasoning steps (Flow 1), user sees 4 design proposals and can explore each in detail.

**Design System Reference:** Use design system from `figma_make_prompt_flow1_agentic_reasoning.md`:
- iPhone 14 Pro viewport (390 x 844px)
- Chat-based interface colors & typography
- Same component styles (bubbles, buttons, spacing)

**Flow 2 Specific:**
- Safe area: 20px horizontal padding (effective width: 350px)
- 2x2 grid layout with 8px spacing between items
- Navigation: Left-to-right push transition into detail view

---

## Screen 1: Chat with Design Grid (Main View)

### Visual Hierarchy & Layout

**Header Section (Fixed, 44px):**
- Status bar (20px)
- Navigation: Left title "AI Room Designer", right close button (X icon, 20x20px)
- Background: White (#FFFFFF)
- Bottom divider: 1px #E8E8E8

**Chat Context Area (Scrollable):**
- Previous chat messages (Steps 1-6, faded/reference)
- Spacing: 12px margins between sections

**Design Proposals Section:**
- **Intro text message** (left-aligned, AI bubble style):
  ```
  Here are four designs based on your family hangout goals. Each
  one balances warmth, functionality, and your budget. Tap any to
  see details and products.
  ```
  (14px, #333333, line-height 1.6)
  - Bubble style: #F5F5F5 bg, #E0E0E0 border, 16px padding, 16px margin-bottom

- **2x2 Grid Layout:**
  - Grid container: 350px width (accounting for safe area)
  - 2 columns, 8px gap between items
  - Each grid item: (171px x 171px)
  - Item structure:
    - **Design image:** 171x171px, corner radius 12px
    - **Label below image:** 12px gray text, centered, 8px top margin
    - **Example labels:**
      - "Option 1: Cozy & Warm"
      - "Option 2: Open & Playful"
      - "Option 3: Guest-Friendly"
      - "Option 4: Bold & Fresh"

  - **Visual treatment:**
    - Each image has subtle hover state (overlay when interactable)
    - Slight shadow: 0px 2px 8px rgba(0,0,0,0.08)
    - Border on hover: 2px #2E7D32 (indicates interactivity)

**Bottom CTA (if not in grid):**
- Optional: "Swipe to compare designs" hint text (12px gray, centered, bottom 20px padding)

### Interaction
- User taps any grid item → Push animation (left to right) → Detail view appears
- Grid remains visible on swipe-back gesture

---

## Screen 2-5: Design Detail View (Full Page, 4 variations)

### Navigation & Header
- **Left navigation arrow:** Chevron left (20x20px, #2E7D32)
  - Tapping goes back to grid view
  - Smooth left-to-right dismissal animation

- **Option indicator:** Small pill/badge near title
  - "Option 1 of 4" (12px, #999999, right-aligned)

- **Header title:** "Design Proposal: [Option Name]"
  - Example: "Design Proposal: Cozy & Warm"
  - 18px bold, #1A1A1A
  - Margin-top: 20px, margin-bottom: 20px

### Main Content (Scrollable)

#### **Section 1: Hero Image**
- **Design render image:** 350px width x 300px height
- **Corner radius:** 12px
- **Shadow:** 0px 4px 12px rgba(0,0,0,0.12)
- **Margin-bottom:** 20px

#### **Section 2: Design Story**
- **Section header:** "Your Design" (14px bold, #333333)
- **Content text:** (13px regular, #666666, line-height 1.6)
  ```
  Example for Option 1 (Cozy & Warm):
  "This design prioritizes warmth and comfort for your family
  movie nights. A large rug anchors the center space while warm
  floor lamps create ambient lighting. The sofa gets layered
  cushions and throws for that inviting feel you wanted."
  ```
- **Margin-bottom:** 20px

#### **Section 3: Key Additions**
- **Section header:** "Key Additions" (14px bold, #333333)
- **Bulleted list:** (13px regular, #666666)
  - Each item on new line with bullet point (•)
  - Indent: 8px from left
  - Example items:
    - Large rug (200×290cm) in warm taupe
    - 2x floor lamps with warm dimming
    - Cushion covers in cream & gray
    - Throw blankets (wool blend)
    - Wall art (3-piece set above sofa)
- **Margin-bottom:** 20px

#### **Section 4: Product Details** (Scrollable table-like layout)
- **Section header:** "Products in This Design" (14px bold, #333333)
- **Product cards** (one per line):
  - Layout: Small product image (60x60px) + product info
  - Product name (13px bold, #333333)
  - Brand (12px, #999999)
  - Price (13px bold, #2E7D32)
  - "View on Ohouse" link (12px, #2E7D32, underlined)

  Example:
  ```
  [Product Image]  Nordic Taupe Rug (200×290)
                   Muuto Design
                   $890
                   View on Ohouse →
  ```
  - Spacing: 12px between products
- **Margin-bottom:** 20px

#### **Section 5: Budget Summary**
- **Background:** Light gray (#F9F9F9)
- **Padding:** 16px
- **Border-radius:** 8px
- **Content:**
  - **Row 1:** "Estimated Total:" | "$1,200" (bold, #2E7D32)
  - **Row 2:** "Range:" | "$950–$1,450" (regular, #666666)
  - **Row 3:** "Flexibility:" | "Swappable items (adjust +/- $200)" (12px, #999999)
- **Margin-bottom:** 20px

#### **Section 6: Material & Customization (Optional)**
- **Section header:** "Material Options" (14px bold, #333333)
- **Selectable options** (chips/pills):
  - Example: Rug material options
  - Chips: "Wool" | "Wool Blend" | "Synthetic" (12px, padding 8px 12px)
  - Selected chip: #2E7D32 bg, white text
  - Unselected chip: #F0F0F0 bg, #666666 text
  - Border-radius: 20px
  - Spacing: 8px between chips
- **Margin-bottom:** 20px

#### **Section 7: Actions**
- **CTA buttons** (both full-width, 48px height):

  1. **Primary button:** "Save & Compare" (#2E7D32 background, white text, 14px bold)
     - Rounded 8px
     - Margin-bottom: 8px
     - On tap: Saves this design, optionally returns to grid

  2. **Secondary button:** "Give Feedback" (white bg, #2E7D32 border 2px, #2E7D32 text)
     - Rounded 8px
     - On tap: Opens feedback modal (or navigates to feedback flow)

- **Margin-bottom:** 20px (bottom safe area)

---

## Screen Navigation & Transitions

### Grid → Detail View
- **Trigger:** User taps any grid item (4 variations, one for each design)
- **Animation:** Push from left (slide-in from right edge)
- **Duration:** 0.4s ease-out
- **Result:** Detail view appears full-screen, grid slides off to the left

### Detail View Navigation (Between Options)
- **Method 1:** Swipe gesture (left-swipe to next option, right-swipe to previous)
  - Auto-updates design image, text, products, budget
  - Smooth horizontal slide animation

- **Method 2:** Back button + tap different grid item
  - Returns to grid, user selects new design
  - Re-enters detail view with new design content

- **Method 3:** Dot indicator at bottom (optional)
  - Small dots (4 total) indicating current position in carousel
  - User can tap to jump to specific design
  - Position: Bottom center, above buttons

---

## Content Variations (4 Design Options)

Each detail view should show different:
1. **Hero image** (different design aesthetic for each option)
2. **Design story text** (unique narrative for each direction)
3. **Key additions list** (different products per option)
4. **Product details** (4-6 products per design)
5. **Budget range** (may vary by option)
6. **Material options** (context-appropriate materials)

### Option 1: Cozy & Warm
- Theme colors: Warm taupe, cream, soft gold
- Key products: Large rug, warm lamps, cushions, throws
- Budget: ~$1,200

### Option 2: Open & Playful
- Theme colors: Light neutral, pops of color, open space
- Key products: Medium rug, colorful storage, flexible seating
- Budget: ~$950

### Option 3: Guest-Friendly
- Theme colors: Neutral, accent chairs, balanced
- Key products: Rug, lamps, accent chairs, console table
- Budget: ~$1,450

### Option 4: Bold & Fresh
- Theme colors: Jewel tones, modern, personality
- Key products: Textured rug, statement lamps, bold art, colorful cushions
- Budget: ~$1,300

---

## Interaction States & Micro-interactions

### Grid Items
- **Default:** Clean image with label below
- **Hover/Focus:** 2px #2E7D32 border appears, slight scale (1.02x)
- **Pressed:** Scale (0.98x), opacity 0.9
- **Transition time:** 0.2s ease-out

### Buttons (Detail View)
- **Default:** Primary: solid #2E7D32, Secondary: white with border
- **Hover:** Primary: darker #1B5E20, Secondary: light gray #F5F5F5 bg
- **Pressed:** Scale 0.95x
- **Transition time:** 0.15s ease-in-out

### Material Option Chips
- **Default:** Unselected: white/gray, Selected: #2E7D32
- **Tap:** Toggles selection state
- **Transition time:** 0.2s ease-out

### Navigation
- **Back arrow:** Hover state: color to #1B5E20, scale 1.1x
- **Swipe gesture:** Smooth continuous pan, elastic snap-back if released mid-swipe


---

## Figma Make Implementation Steps

1. **Create Flow 2 specific components:**
   - Grid item (image + label, 171x171px each)
   - Product card (image + name + brand + price + link)
   - Budget summary box (#F9F9F9 background)
   - Material option chips (selected/unselected states)
   - Detail view sections (reusable, themed)

2. **Build Screen 1 (Grid View):**
   - Chat intro message bubble
   - 2x2 grid (350px width, 8px spacing)
   - Each grid item: 171x171px image + 12px label below
   - All items interactive/tappable

3. **Build Screens 2-5 (Detail Views for each Option):**
   - Use one template, create 4 content variants:
     - Option 1: Cozy & Warm
     - Option 2: Open & Playful
     - Option 3: Guest-Friendly
     - Option 4: Bold & Fresh
   - Each includes: hero image, story text, key additions, products, budget, materials

4. **Add Flow 2 interactions:**
   - Grid item tap → Push transition to detail view (0.4s)
   - Back arrow → Pop back to grid
   - Swipe left/right → Navigate between detail screens (0.3s)
   - Material chip tap → Toggle selection
   - Primary/secondary buttons → Trigger actions

5. **Final checks:**
   - Grid items properly spaced and sized
   - Detail view sections scroll naturally
   - All text readable at specified font sizes
   - Interactive states clear (hover, selected, pressed)
   - Navigation smooth and intuitive

---

## Success Criteria

When complete, the prototype should:
1. ✅ Show 2x2 grid of 4 design proposal thumbnails
2. ✅ Grid items tap → detail view push transition (0.4s)
3. ✅ Display 4 distinct detail views (one per design option)
4. ✅ Show design story, key additions, products, budget in each detail view
5. ✅ Allow swipe navigation between detail views (left/right)
6. ✅ Back arrow returns to grid
7. ✅ Product cards include: image + name + brand + price + "View on Ohouse" link
8. ✅ Budget summary clearly shows: total + range + flexibility note
9. ✅ Material options appear as selectable chips
10. ✅ Save & Feedback buttons functional/interactive
11. ✅ Natural mobile UX (iPhone 14 Pro, 350px effective width)
12. ✅ Smooth transitions and responsive interactions

