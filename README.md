# Agent 01 — Screener (Gemini 2.5 Flash)

Part of the **Agentic Trading AI** pipeline based on Mark Minervini's Super Performance method.

## Live deployment

After following the steps below your URL will be:
```
https://<your-github-username>.github.io/<your-repo-name>/agent_01_screener.html
```

---

## Deploy to GitHub Pages in 5 steps

### Step 1 — Create a GitHub account
Go to [github.com](https://github.com) and sign up (free).

### Step 2 — Create a new repository
1. Click the **+** button → **New repository**
2. Name it anything, e.g. `trading-agents`
3. Set visibility to **Public** (required for free GitHub Pages)
4. Click **Create repository**

### Step 3 — Upload the file
1. In your new repo, click **Add file → Upload files**
2. Drag `agent_01_screener.html` into the upload area
3. Click **Commit changes**

### Step 4 — Enable GitHub Pages
1. Go to **Settings** tab of your repo
2. Scroll to **Pages** in the left sidebar
3. Under **Source**, select **Deploy from a branch**
4. Branch: `main`, folder: `/ (root)`
5. Click **Save**

### Step 5 — Open your live URL
Wait ~60 seconds, then visit:
```
https://<your-username>.github.io/trading-agents/agent_01_screener.html
```

GitHub will also show the URL at the top of the Pages settings page.

---

## Get your Gemini API key (free)

1. Go to [aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey)
2. Sign in with your Google account
3. Click **Create API key**
4. Copy the key (starts with `AIza...`)
5. Paste it into the **Gemini API key** field in the app

**Free tier limits:** 10 requests/minute · 250 requests/day  
Your key is stored in your browser only — never sent anywhere except Google's API.

---

## Usage

1. Enter your Gemini API key in the left panel
2. Select exchange (US / HK / Both), benchmark index, and number of candidates
3. Click **▶ RUN SCREENER**
4. Three stages run sequentially:
   - **1.1 Market environment** — VIX, index vs MAs, phase classification (EASY/BLOOD)
   - **1.2 Sector rotation** — top 5 RS-leading sectors this week
   - **1.3 Candidate screen** — top N stocks matching Minervini Trend Template
5. Review results in the **Results** tab
6. Copy the **JSON payload** from the JSON tab to pass to Agent 02 (Extraction)

---

## Pipeline position

```
[Agent 01 Screener] → [Agent 02 Extraction] → [Agent 03 Sentiment]
      → [Agent 04 Playbook] → [Agent 05 Journal] → [Agent 06 Knowledge]
```

This agent outputs a structured JSON payload (`agent_01_output`) consumed by Agent 02.
