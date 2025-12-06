
# 🚀 AI Facebook Ad Scraper & Analyzer – Automated Intelligence Workflow

> Fully automated competitor ad intelligence using Facebook Ad Library → Categorized → Analyzed → Logged → Ready for execution.

---

## 📌 Overview

This workflow is a complete automated intelligence system for analyzing Facebook Ads at scale. Designed for agencies, growth teams, media buyers, and founders who want structured insights—not screenshots and guesswork.

This automation scrapes ads, classifies them using logic-based routing, analyzes creatives with LLMs, extracts descriptions, rewrites ad copy, and stores everything in a structured sheet for long-term intelligence tracking.

This includes:
✓ Creatives (Video/Image/Text)
✓ Summary of the ad
✓ Rewritten copy for repurposing
✓ AI-generated creative prompts
✓ Advertiser metadata

Data is scraped using Appify (Facebook Ad Library API Wrapper) and processed with n8n.

---

## 🧠 What This Workflow Actually Does

1. Initiates a scraping pipeline
2. Extracts ad metadata
3. Categorizes ads dynamically:
   - Video ads
   - Image ads
   - Text‑only ads
4. Uses Gemini to visually analyze videos
5. Uses GPT‑4.5/GPT‑4o to summarize and rewrite ad copy
6. Pushes structured intelligence into Google Sheets
7. Stores video files automatically so that AI can analyze them accurately

---

## 🧩 Core Workflow Architecture



START TRIGGER
↓
Scrape Ads from Appify
↓
Filter based on advertiser popularity
↓
Switch Routing
↳ Video Branch
↪ Download Video
↪ Upload to Drive → Gemini Upload
↪ Gemini descriptive analysis
↪ GPT rewrite
↪ Store output in Google Sheets
↳ Image Branch
↪ AI Vision extraction
↪ GPT rewrite
↪ Store into Google Sheets
↳ Text Branch
↪ GPT rewrite only
↪ Store into Google Sheets
↓
End



---

## 🔍 Feature Breakdown

### 🔎 Scraping Layer
Using the Appify workflow scraper:
- Pulls live ads from Facebook Ad Library
- Includes advertiser page information
- Extracts media URLs
- Supports keyword‑based search queries

### 🎯 Filtering Logic (Early Noise Reduction)
Before processing ads, system eliminates low‑signal advertisers:
- Ads from pages with < 1000 likes are ignored

This helps:
- Remove dropshipping junk ads
- Reduce LLM cost
- Maintain quality dataset

### 🎛 Smart Routing Engine
System classifies ad formats:

| Media Indicators | Classified As |
|-----------------|----------------|
| Video URL exists | Video Ad |
| Image URL exists | Image Ad |
| Neither | Text‑only ad |

Routing ensures:
- Processing cost stays optimal
- Output formatting remains consistent

---

## 🧠 Intelligence Layer

### GPT‑4.5 or GPT‑4o
Used to:
- Rewrite ad copy
- Summarize campaigns
- Generate marketing angles
- Repurpose into new formats

Example Output Template:

``json
{
  "summary": "",
  "rewrittenAdCopy": ""
}


---

## 🎬 Video Analysis Layer (Gemini)

For each video:

1. Downloads creative automatically
2. Uploads video via Gemini resumable upload
3. AI generates:

* Frame‑level detail
* Creative style analysis
* Hooks used
* Emotional baseline
* CTA decoding

Example Response Captures:

* Scene changes
* Text overlays
* UI demonstration
* Product usage

---

## 🧾 Google Sheets Output Schema

The sheet stores structured ad intelligence:

| Column            | Description                   |
| ----------------- | ----------------------------- |
| ad_archive_id     | Unique ad identifier          |
| page_id           | Page ID running the ad        |
| date_added        | Timestamp of analysis         |
| type              | video/image/text              |
| summary           | AI‑generated ad breakdown     |
| rewritten_ad_copy | Fresh rewritten variant       |
| page_url          | Clickable FB page link        |
| video_prompt      | (Video only) Gemini breakdown |
| image_prompt      | (Image only) Vision breakdown |

---

## 💡 Use Cases

### For Agencies

* Track winning creatives from competitors
* Turn competitor scripts into variants

### For Founders

* Learn what messaging top brands use

### For Media Buyers

* Identify what angle performs per niche

### For Content Teams

* Turn competitors’ ads into content scripts

---

## ⚙️ Setup Requirements

You need access to:

🔹 Appify API Key (for Facebook Ad Library scraping)
🔹 OpenAI Key or Azure OpenAI Key
🔹 Google Sheets credentials
🔹 Google Drive credentials
🔹 Gemini API Key (only for videos)

---

## 🧪 Execution Steps

1. Open workflow in n8n
2. Insert all credentials
3. Run scraping node
4. Observe branching automatically
5. Export Google Sheet for analysis

Everything scales horizontally — meaning you can query:

* multiple keywords
* multiple regions
* multiple time periods

---

## 🧠 Advanced Ideas for Scaling

✔ Schedule daily scraping at midnight
✔ Auto‑email summary reports
✔ Cluster messaging patterns using embeddings
✔ Track advertiser spend activity
✔ Detect seasonal offers

---

## 🧵 Sample Intelligence Output Structure


Competitor Name: BrandX
Angle Used: AI for productivity
Primary CTA: "Book Demo"
Hook Pattern: Logic‑based urgency
Creative Type: Talking head video
Variant You Should Try: "Install now & unlock AI shortcuts"
``

---

## 🔥 Why This Workflow Works

Because it solves media buyers’ core pain:

> “We know competitors are winning—but we don’t know exactly why.”

This workflow turns:
❌ guessing → into clarity
❌ screenshots → into structured intelligence
❌ expensive manual research → into automation

---

## 📌 Final Output

You end up with:

📁 Centralized database of ads
📄 Rich AI summaries
✍️ Ready‑to‑use rewritten scripts
📊 Historical tracking per run
🎬 Complete decoded video messaging

All — without touching spreadsheets manually.

---

🛠 Build. Automate. Spy Better. Win Faster.

```
```
