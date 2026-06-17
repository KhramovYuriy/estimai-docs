# EstimAI — Support Documentation

---

## Quick start (2 minutes)

### Step 1: Install
Install EstimAI from the Atlassian Marketplace. It will appear in your Jira sidebar as "EstimAI".

### Step 2: Get an API key
EstimAI uses your own AI provider key — you pay directly to OpenAI or Anthropic at their rates.

**OpenAI (recommended):**
1. Go to platform.openai.com/api-keys
2. Create a new key
3. Copy it (starts with `sk-...`)

**Anthropic (alternative):**
1. Go to console.anthropic.com
2. Create a new API key
3. Copy it (starts with `sk-ant-...`)

### Step 3: Configure
1. Open EstimAI → click ⚙ Settings
2. Select your AI provider
3. Paste your API key
4. Click "Save settings"

### Step 4: Estimate
1. Open any Epic or issue in Jira
2. Or navigate to EstimAI in the sidebar
3. Enter the issue key (e.g., `KAN-4`) or paste the full URL
4. Optionally add design screenshots, Figma link, or grooming notes
5. Click "Estimate story points"

---

## Features guide

### Loading issues
EstimAI supports all Jira project types:
- **Team-managed (next-gen):** Children load automatically via `parent` relationship
- **Classic Scrum:** Children load via Epic Link field
- **Company-managed:** Sub-tasks load from issue fields

Enter an issue key (`KAN-4`), paste a full Jira URL, or let EstimAI auto-load from the current issue context (when used as an Issue Panel).

### Design screenshots
Upload up to 5 screenshots of your design. AI analyzes UI complexity, number of components, and interaction patterns.

Supported: PNG, JPG, WebP. Images are resized to 1200px max before sending.

### Figma integration
1. Go to figma.com → Account → Personal access tokens → Create new token
2. In EstimAI Settings → add your Figma Personal Access Token
3. Paste any Figma frame URL into the "Prototype link" field
4. Click ↓ to auto-fetch the screenshot

**Note:** The URL must include a `node-id` parameter (right-click a frame in Figma → Copy link).

### Grooming transcript
Paste your meeting notes, Grain/Notion AI transcript, or manual notes. EstimAI extracts technical decisions, risks, and constraints to improve estimate quality.

### Sub-tasks and platform dropdown
Each sub-task has a platform label (Frontend, Backend, iOS, Android, Desktop, QA, DevOps). This is used to:
- Filter calibration data to similar past tasks
- Improve estimate context

When an Epic with Jira sub-tasks is loaded, they auto-populate with AI-detected platform labels.

### Calibration
EstimAI fetches completed tasks from your project (last 90 days by default). These appear in each result card as historical anchors — real tasks your team completed, with actual hours logged.

Calibration window can be adjusted in Settings.

### Planning Poker feedback
After estimating:
1. Run your team's Planning Poker session
2. Select the team's agreed SP for each task
3. Click "Save feedback"

EstimAI tracks AI accuracy over time. The more you use it, the better the calibration becomes.

---

## FAQ

**Q: Why do I need to provide my own API key?**
A: EstimAI is "bring your own key" — you connect directly to OpenAI or Anthropic. This means your data never passes through our servers, and you pay AI costs at provider rates (typically $0.01–0.05 per estimation).

**Q: Is my data safe?**
A: Yes. EstimAI runs on Atlassian Forge — all data stays within Atlassian's infrastructure. Your API keys are encrypted per-installation. We never store issue content or AI responses after the session. [Full Privacy Policy]

**Q: Which AI provider should I use?**
A: Both work well. GPT-4o mini (OpenAI) tends to be slightly faster and cheaper. Claude Haiku (Anthropic) produces more detailed analysis text. You can switch between them in Settings anytime.

**Q: Why is my sub-tasks count showing 0?**
A: EstimAI tries multiple strategies to find child issues. If it still shows 0:
- For team-managed projects: children must have `parent = EPIC_KEY` relationship
- For classic projects: children must have "Epic Link" set
- You can always add tasks manually in the "Sub-tasks" section

**Q: The Figma screenshot isn't loading — what's wrong?**
A: Common causes:
1. Token not saved — go to Settings and re-save your Figma token
2. Wrong URL format — right-click a specific Frame in Figma → Copy link (URL must include `node-id=`)
3. No access — ensure your Figma token has access to the file

**Q: Can I use EstimAI for Linear / Asana / Notion?**
A: Currently EstimAI is Jira-only. You can still use it manually: enter a task description in the "Epic description" field without loading from Jira.

**Q: How accurate are AI estimates?**
A: Accuracy improves over time as calibration data builds up. In our testing, after 20+ feedback sessions, AI matches team estimates within ±1 SP about 80% of the time for well-described tasks.

**Q: Does EstimAI work on Jira Data Center / Server?**
A: No. EstimAI is built on Atlassian Forge and supports **Jira Cloud only**.

---

## Pricing

EstimAI is currently **free** — 15 AI estimations per month, with all features included (vision, Confluence context, historical calibration, Figma). A paid unlimited plan is planned for a future release.

---

## Contact & support

**Email:** khramovyuriy@gmail.com  
**Response time:** Within 24 hours on business days

For bug reports, please include:
- Your Jira project type (team-managed / classic)
- Issue key you were trying to estimate
- Screenshot of the error message
