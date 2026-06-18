# Privacy Policy — EstimAI

**Last updated:** 17 June 2026

## 1. Overview

EstimAI ("we", "our", "the app") is an Atlassian Forge application that provides AI-powered Story Point estimation for Jira. This Privacy Policy describes what data we collect, how we use it, and your rights.

EstimAI is built on the **Atlassian Forge** platform and operates **no servers or databases of its own** — its code runs inside Atlassian's infrastructure. To generate an estimate, however, EstimAI **sends the data you choose** (issue text, and any screenshots/transcript you add) to the **third-party AI provider you configure** (OpenAI or Anthropic), and optionally to Figma to fetch a linked design. See Sections 2–4 for exactly what is sent and to whom.

---

## 2. What data we access

### Data accessed from Jira
- **Issue data:** Title, description, status, labels, and sub-tasks of issues you choose to estimate
- **Project data:** Project key and completed issue history used for calibration (last 90 days by default)
- **User context:** Your Jira installation's site URL

We access only the issues you explicitly load into EstimAI. We do not scan, index, or store your entire Jira project.

### Data you provide
- **Design screenshots:** Images you upload for AI analysis. These are sent to your configured AI provider (OpenAI or Anthropic) and are not stored by us.
- **Grooming transcripts:** Text you paste into the grooming notes field. Sent to your AI provider for analysis, not stored by us.
- **API keys:** Your OpenAI or Anthropic API keys, stored encrypted in Atlassian Forge Storage, accessible only within your Jira installation.
- **Figma token:** Your Figma Personal Access Token, stored in Atlassian Forge Storage.

### Data we store
EstimAI stores the following data **per Jira installation** using Atlassian Forge Storage (per-tenant, isolated):
- **Estimation feedback:** When you save a Planning Poker result, we store: issue key, AI estimate, team estimate, delta, and timestamp. This is used to improve calibration over time.
- **Settings:** Your configured AI provider, calibration window (days), and SP scale.
- **Field preference:** Your chosen Story Points field, saved per project against your Atlassian `accountId` (an opaque Atlassian identifier — not your name or email) so the picker remembers your selection.

We do **not** store issue content, screenshots, transcripts, or AI-generated estimates after the session ends.

---

## 3. How we use your data

| Purpose | Data used | Retention |
|---------|-----------|-----------|
| Generate AI estimates | Issue title, description, sub-tasks, calibration history | Not stored — session only |
| Improve calibration accuracy | Estimation feedback (issue key, AI vs team SP) | Stored per installation, up to 200 entries |
| Authenticate with Figma | Figma Personal Access Token | Stored encrypted in Forge Storage |
| Call AI APIs | Issue data + images you provide | Sent to your AI provider, not stored by us |

---

## 4. Third-party services

EstimAI sends data to your chosen AI provider when you run an estimation:

| Provider | Privacy Policy | What's sent |
|----------|----------------|-------------|
| OpenAI (GPT-4o mini) | https://openai.com/privacy | Issue text, optional screenshots |
| Anthropic (Claude Haiku) | https://www.anthropic.com/privacy | Issue text, optional screenshots |
| Figma (optional) | https://www.figma.com/privacy | Your Figma token to fetch screenshots |

**You control which provider is used.** You provide your own API keys — EstimAI does not proxy or store AI responses.

---

## 5. Data sharing

We do not sell, trade, or share your data with third parties beyond the AI providers listed above, which you explicitly configure. We do not use your data for advertising.

---

## 6. Data security

- All data is stored in **Atlassian Forge Storage**, which is encrypted at rest and in transit
- API keys are stored per-installation and are not accessible to other tenants
- EstimAI runs entirely within Atlassian's Forge runtime and has **no databases or servers of its own**. The only data that leaves Atlassian is what you send to your configured AI provider / Figma at estimation time (see Section 4), under your own API keys
- Forge platform security details: https://developer.atlassian.com/platform/forge/security

---

## 7. Data retention and deletion

- **Estimation feedback** is stored on a rolling basis — oldest entries are deleted when the 200-entry limit is reached
- **Settings and API keys** remain until you uninstall the app or clear them manually
- **Uninstalling EstimAI** removes all stored data from Forge Storage for your installation

---

## 8. Your rights

You have the right to:
- **Access** the data we store about your installation (contact us)
- **Delete** your data by uninstalling the app or contacting us
- **Correct** settings data via the Settings page in EstimAI

---

## 9. Children's privacy

EstimAI is a professional tool intended for use in workplace settings. We do not knowingly collect data from individuals under 16 years of age.

---

## 10. Changes to this policy

We will update this policy as needed. The "Last updated" date at the top reflects the most recent revision. Continued use of EstimAI after policy changes constitutes acceptance.

---

## 11. Contact

Questions about this Privacy Policy?

**EstimAI Support**
Email: khramovyuriy@gmail.com
Support: https://khramovyuriy.github.io/estimai-docs/support
