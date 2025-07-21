# 🚀 Reddit-Powered Startup Idea Creator with n8n + AI

[![n8n](https://img.shields.io/badge/built%20with-n8n-orange?style=for-the-badge\&logo=n8n)](https://n8n.io)
[![AI Powered](https://img.shields.io/badge/AI%20powered-Gemini%20Flash-blueviolet?style=for-the-badge\&logo=google)](https://deepmind.google/technologies/gemini/)

Automate startup idea discovery from Reddit by identifying real user pain points using AI — and log your findings, solution, design directly into Google Sheets.

---

## 🧠 What This Project Does

📅 Scrapes Reddit for posts expressing frustration with products
🔍 Filters high-engagement posts
🧠 Uses AI to identify real user problems
🌟 Generates business ideas or solutions for the problems
📃 Logs all insights to Google Sheets

---

## 💡 Why This Matters

Most teams spend **80–90%** of their time on repetitive tasks. Automating workflows like these helps you:

* Surface validated startup ideas
* Eliminate manual research work
* Move fast from problem → solution
* Build MVPs people actually want

---

## 🔧 Tools & Services Used

| Tool                  | Purpose                         |
| --------------------- | ------------------------------- |
| [n8n](https://n8n.io) | Workflow Automation Engine      |
| Reddit API            | Scraping Real User Complaints   |
| Gemini Flash 2.0      | Fast AI analysis (prompt-based) |
| Google Sheets         | Structured Output Storage       |

---

## 🛠️ How To Set Up

### 1. Clone this Repository (Optional)

```bash
git clone https://github.com/your-username/reddit-startup-ideas.git
cd reddit-startup-ideas
```

---

### 2. Setup n8n

* Create a free account at [n8n.io](https://n8n.io)
* Start a new workflow
* Choose **Manual Trigger**

---

### 3. Configure Reddit Scraping

* Add a **Reddit Node**

* Provide your credentials:
  Get your [client ID and secret here](https://www.reddit.com/prefs/apps)

* Example query:
  `"why I stopped using Slack"`
  `"why I hate Instagram"`

* Limit to 10 posts (adjust as needed)

---

### 4. Filter for Quality Posts

* Use an **If Node**:

  * `upvotes >= 2`
  * `self_text is not empty`

---

### 5. Select Useful Fields

Use a **Set Node** to keep only:

* Title
* Post Text
* Created Date
* Upvotes
* URL

---

### 6. AI Analysis with Gemini Flash

* Add an **AI Node**
* Use Gemini Flash 2.0
* Prompt:

```text
Does this post contain a real product problem? Answer only yes or no.
```

* (Optional Prompt for explanation):

```text
Explain the product pain point in this post.
```

---

### 7. Filter AI-Validated Posts

* Use another **If Node**: Keep only posts with `yes` from AI

---

### 8. Generate Business Ideas with AI

* Add another **Gemini AI Node**
* Prompt:

```text
Given this user problem, suggest a concise and clear product idea.
```

---

### 9. Merge All Findings

* Use a **Merge Node** to combine:

  * Reddit data
  * AI explanation
  * AI-generated solution

---

### 10. Export to Google Sheets

* Create a Google Sheet with columns:
  `title`, `original_problem`, `created_date`, `upvotes`, `url`, `ai_decision`, `solution`

* Add a **Google Sheets Node** in n8n

* Authorize your account

* Map each field from JSON output to a column

---

## ✅ Final Output

![Sample Output Sheet](./assets/sample-sheet.png) <!-- Replace with your screenshot path -->

The final Google Sheet contains:

* Validated product complaints
* Clear business ideas
* Engagement metrics

---

## 🧪 Example Use Cases

* 🔍 Product Market Fit Validator
* 🧱 MVP Builder Based on Complaints
* 📊 Weekly "Problem Discovery" Report
* 🧠 Competitor Monitoring & Research

---

## 📂 Repository Structure

```
📆 reddit-startup-ideas
 ├📁 assets/
 │ └📷 sample-sheet.png
 ├📄 README.md
 ├📄 LICENSE
```

---

## 📣 Contributing

Feel free to fork and PR! Add support for other platforms (Twitter, LinkedIn), use different AI models (Claude, GPT-4), or build visual dashboards.

---

## ✍️ Author

**\[Your Name / Handle]**
[GitHub](https://github.com/your-username) • [Twitter](https://twitter.com/your-handle) • [Website](https://your-site.com)

---

## 📬 Feedback

If this project helped you or sparked an idea, give it a ⭐ and let us know what you’ll automate next!
