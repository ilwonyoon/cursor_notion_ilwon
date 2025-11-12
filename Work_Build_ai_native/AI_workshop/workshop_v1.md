# Vibe Coding Workshop - A to Z for Dummies

## Part 0: Getting Started (20 min)

### 0.1 What is "Vibe Coding"?

**Traditional Programming**
```
Designer: "Hey dev, I need this feature"
Developer: "OK, see you in 3 weeks"
(Wait 3 weeks...)
Result: Not what I wanted
```

**Vibe Coding**
```
You: Tell Claude what you want
Claude: "Here's the code!"
You: "Change the color to blue"
Claude: "Done!"
Result: Exactly what you wanted
```

**Key: "Program by talking to AI"**

---

## Part 1: Environment Setup (1 hour)

### 1.1 Install Cursor

Cursor is a code editor with Claude built-in.

#### Step 1: Download
1. Visit https://www.cursor.sh
2. Click "Download"
3. Choose your OS (Mac or Windows)
4. Wait for download

#### Step 2: Install
**Mac:**
- Double-click `Cursor.dmg`
- Drag to Applications folder

**Windows:**
- Double-click installer
- Click Next until done

#### Step 3: Open Cursor
- Applications → Cursor (or from Downloads)

#### Step 4: Connect Claude
```
Settings → Features → Claude API
```
- Toggle "Enable Claude API"
- Go to https://console.anthropic.com/api/keys
- Create Key and paste into Cursor

---

### 1.2 Install Claude Code CLI

Claude Code CLI lets you use Claude from terminal.

#### Step 1: Open Terminal

**Mac:**
- Spotlight (Command + Space)
- Type "Terminal" and open

**Windows:**
- Windows Search (Windows + S)
- Type "PowerShell" and open

#### Step 2: Copy and paste this command:

**Mac/Linux:**
```bash
curl -fsSL https://claude.sh/install.sh | bash
```

**Windows PowerShell:**
```powershell
irm https://claude.sh/install.ps1 | iex
```

#### Step 3: Verify installation
```bash
claude --version
```

If you see a version number, you're done!

---

### 1.3 Install Git

Git is like a "time machine for code".

#### Step 1: Download

**Mac:**
```bash
xcode-select --install
```

**Windows:**
- Visit https://git-scm.com/download/win
- Download and install (click Next)

#### Step 2: Verify
```bash
git --version
```

---

### 1.4 GitHub Setup

GitHub stores your code online.

#### Step 1: Create account
- https://github.com/signup
- Sign up with email

#### Step 2: Configure Git
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

---

### 1.5 Install Node.js

Node.js lets JavaScript run on your computer.

#### Step 1: Download
- https://nodejs.org
- Download LTS version

#### Step 2: Install
- Double-click and click Next until done

#### Step 3: Verify
```bash
node --version
npm --version
```

---

### 1.6 Create Your First Project

#### Step 1: Create folder
```bash
mkdir -p ~/Desktop/vibe-coding
cd ~/Desktop/vibe-coding
```

#### Step 2: Create React project
```bash
npm create vite@latest my-first-project -- --template react
```

When asked about TypeScript: Choose "No"

#### Step 3: Navigate to project
```bash
cd my-first-project
```

#### Step 4: Install packages
```bash
npm install
```

#### Step 5: Start development server
```bash
npm run dev
```

You should see:
```
➜ Local: http://localhost:5173/
```

#### Step 6: Check in browser
- Open Chrome/Safari
- Go to http://localhost:5173
- You should see "Vite + React" page

---

### 1.7 Modify Your First Code

#### Step 1: Open in Cursor
1. Open Cursor
2. File → Open Folder
3. Select `my-first-project` folder

#### Step 2: Open App.jsx
- Left panel → src → App.jsx

#### Step 3: Ask Claude to help
- Press Cmd+K (or Ctrl+K on Windows)
- Type: "Replace the count button with 'Hello, [Your Name]'"

#### Step 4: Review and accept
- Claude shows the change
- Click "Accept"

#### Step 5: See the result
- Refresh browser (Cmd+R or Ctrl+R)
- Text should change!

---

### 1.8 Save to Git

#### Step 1: Go to project folder
```bash
cd ~/Desktop/vibe-coding/my-first-project
```

#### Step 2: Check status
```bash
git status
```

#### Step 3: Add files
```bash
git add .
```

#### Step 4: Save
```bash
git commit -m "First project setup"
```

#### Step 5: Upload to GitHub
1. Go to https://github.com/new
2. Create repository
3. Copy commands shown and paste in terminal

Done! Your code is on GitHub.

---

## Part 2: Core Concepts (1 hour)

### 2.1 How Vibe Coding Works

**Claude's Workflow:**
1. You ask (Prompt)
2. Claude thinks
3. Claude answers (Response)

**Good question:**
```
"In App.jsx, change button color to blue"
```

**Bad question:**
```
"Change the color"
```

---

### 2.2 Frontend Basics: HTML/CSS/JavaScript

**HTML** = Structure (walls, doors, windows)
**CSS** = Styling (paint, lights, furniture)
**JavaScript** = Interactivity (electricity, function)

---

### 2.3 React Components

React lets you build with reusable blocks (like LEGO).

```jsx
function MyButton() {
  return <button>Click me</button>;
}
```

Use it anywhere: `<MyButton />`

---

### 2.4 State (Changing Data)

State is data that changes over time.

```jsx
const [count, setCount] = useState(0);

<button onClick={() => setCount(count + 1)}>
  Count: {count}
</button>
```

---

### 2.5 Tailwind CSS

Style without writing CSS. Just use class names.

```jsx
<button className="bg-blue-500 text-white px-4 py-2 rounded">
  Click me
</button>
```

- `bg-blue-500` = blue background
- `text-white` = white text
- `px-4 py-2` = padding
- `rounded` = rounded corners

---

### 2.6 API Integration

APIs let you connect to external services.

```javascript
const response = await fetch('https://api.example.com/data');
const data = await response.json();
```

---

### 2.7 Environment Variables

Store sensitive info (like API keys) in .env.local

```
REACT_APP_API_KEY=your_secret_key_here
```

Use in code:
```javascript
const key = process.env.REACT_APP_API_KEY;
```

**IMPORTANT:** Never commit .env.local to GitHub!

---

### 2.8 Essential Terminal Commands

| Command | What it does |
|---------|-------------|
| `cd folder` | Go to folder |
| `ls` (Mac) or `dir` (Windows) | List files |
| `npm install` | Install packages |
| `npm run dev` | Start dev server |
| `git add .` | Prepare files |
| `git commit -m "msg"` | Save version |
| `git push` | Upload to GitHub |

---

### 2.9 Reading Error Messages

Error format:
```
ERROR: Cannot find module 'react'
at /Users/name/project/src/App.jsx:1:28
```

- **What:** Cannot find module 'react'
- **Where:** App.jsx, line 1
- **Solution:** Ask Claude!

---

### 2.10 Debugging

Add logging:
```javascript
console.log("Current value:", myVariable);
```

View in browser DevTools (F12)

---

## Part 3: AI Tools & Integration (1.5 hours)

### 3.1 .cursorrules File

Create `.cursorrules` file to guide Claude.

**Template:**
```
You are a React + Tailwind expert.

Rules:
- Use only Tailwind CSS for styling
- Use Shadcn UI components when possible
- Always handle errors
- Make code responsive
```

---

### 3.2 Shadcn UI Components

High-quality components you can copy-paste.

#### Install:
```bash
npx shadcn-ui@latest init
npx shadcn-ui@latest add button
```

#### Use:
```jsx
import { Button } from "@/components/ui/button"

<Button>Click me</Button>
<Button variant="outline">Or me</Button>
```

---

### 3.3 Environment Variables

#### Create .env.local:
```
REACT_APP_ANTHROPIC_API_KEY=sk-ant-xxxxx
```

#### Use in code:
```javascript
const apiKey = process.env.REACT_APP_ANTHROPIC_API_KEY;
```

#### For Vercel:
1. Go to Vercel dashboard
2. Settings → Environment Variables
3. Add your key (won't be public!)

---

### 3.4 Vercel Deployment

Deploy your website to the internet.

#### Step 1: Connect GitHub
- https://vercel.com
- "Import Project"
- Select your GitHub repo

#### Step 2: Add environment variables
- Settings → Environment Variables
- Add REACT_APP_ANTHROPIC_API_KEY

#### Step 3: Deploy
- Click "Deploy"
- Wait 1-2 minutes
- Your site is live!

#### Auto-deployment:
- Push to GitHub
- Vercel automatically deploys

---

## Part 4: Practice Projects (4 hours)

### Project A: AI Color Palette Generator

User enters keyword → Claude suggests 5 colors → Display with copy button

#### Steps:
1. Create project: `npm create vite@latest color-palette -- --template react`
2. Install Shadcn: `npx shadcn-ui@latest init`
3. Create .env.local with API key
4. In Cursor, ask Claude: "Build a color palette generator that..."
5. Test locally
6. Deploy to Vercel

---

### Project B: Typography Tester

Sliders for font size, line height, letter spacing. Real-time preview.

#### Steps:
1. Create project: `npm create vite@latest typography -- --template react`
2. Add Shadcn Slider: `npx shadcn-ui@latest add slider`
3. Ask Claude to build the interface
4. Test and refine
5. Deploy

---

### Project C: AI Design Feedback Bot (Advanced)

Upload image → Claude Vision analyzes → Chat interface for questions

#### Steps:
1. Create project with Vite React
2. Setup Claude Vision API
3. Add image upload
4. Create chat interface
5. Test and deploy

---

## Part 5: Troubleshooting & Next Steps (30 min)

### Common Errors

#### Error: "Cannot find module"
```
npm install
```

#### Error: "API key not found"
- Check .env.local exists
- Restart dev server

#### Error: "Port 5173 already in use"
- Use new terminal or Ctrl+C to stop

#### Error: "Environment variables not working on Vercel"
- Add to Vercel Settings → Environment Variables
- Redeploy

---

### Asking Claude Better Questions

**Good:**
```
"In App.jsx, change button color to blue.
Current: <button>Click</button>
Wanted: Blue background, white text"
```

**Bad:**
```
"Button doesn't work"
```

### Tips:
- Be specific (file name, what to change)
- Show current code
- Explain desired result
- Ask one thing at a time

---

### Learning Resources

- React: https://react.dev
- Tailwind: https://tailwindcss.com
- Shadcn: https://ui.shadcn.com
- Claude API: https://docs.anthropic.com
- Vercel: https://vercel.com/docs

---

### Next Steps After Workshop

**Week 1:** Rebuild today's project from memory
**Week 2:** Add new features to your projects
**Week 3:** Start a new project you need
**Week 4+:** Build real tools for your team

---

### Team Ideas

- Color palette manager
- Typography guide generator
- Design system automation
- Image analysis tool
- Feedback collection bot
- Prototype testing tool

---

## Appendix

### Terminal Cheat Sheet

```bash
# Folders
cd my-folder          # Go to folder
mkdir new-folder      # Create folder
ls (Mac) / dir (Win)  # List files
pwd                   # Show location

# Git
git add .             # Prepare files
git commit -m "msg"   # Save version
git push              # Upload
git status            # Check status

# NPM
npm install           # Install packages
npm run dev           # Start dev server
npm run build         # Build for production

# Utils
clear (Mac) / cls (Win)   # Clean screen
exit                      # Exit terminal
```

---

### Tailwind CSS Classes

```
Colors: bg-red-500, text-blue-300
Spacing: p-4 (padding), m-4 (margin)
Sizing: w-full, h-64
Alignment: flex, justify-center, items-center
Responsive: md:text-lg lg:text-2xl
Dark mode: dark:bg-gray-800
```

---

### Glossary

| Term | Meaning |
|------|---------|
| Component | Reusable UI block |
| Props | Data passed to component |
| State | Changing data |
| Hook | React function (useState, etc) |
| API | External service connection |
| Endpoint | API address |
| Deploy | Put website online |
| Repository | Code storage |
| Commit | Save version |
| Branch | Independent code version |
| Environment Variable | Secret info storage |

---

## Congratulations!

You now can:
✅ Use Claude for programming
✅ Build web tools
✅ Deploy to internet
✅ Handle errors confidently
✅ Keep learning

**Most important: Keep building!**

Start with small projects. Error messages are your teacher. Claude is your teammate.

**You got this!** 🚀
