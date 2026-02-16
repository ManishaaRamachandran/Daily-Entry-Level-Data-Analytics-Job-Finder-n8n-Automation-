# Daily Entry-Level Data Analytics Job Finder (n8n Workflow)

This project contains an **n8n automation workflow** that runs every day at **1:00 PM IST** and searches for **entry-level data analytics jobs** using the **Adzuna Job Search API**.  
The workflow formats the results neatly and sends them to your email automatically.

---

## 🚀 Features
- Runs automatically every day at **1 PM (IST)**
- Fetches job listings from **Adzuna API**
- Filters and formats job details
- Sends a clean, aligned job report via **Gmail**
- Includes job title, company, location, salary, and apply link

---

## 🛠 Workflow Steps
1. **Schedule Trigger (Cron)**
2. **HTTP Request Node (Adzuna API)**
3. **Function Node (Format job list into HTML table)**
4. **Gmail Node (Send Email)**

---

## 📌 Requirements
- n8n installed (local or cloud)
- Adzuna API credentials:
  - `app_id`
  - `app_key`
- Gmail OAuth credentials connected in n8n

---

## 🔑 Adzuna API Setup
1. Create an account on Adzuna Developer Portal
2. Generate your API credentials:
   - **App ID**
   - **App Key**
3. Add them inside the HTTP Request node query parameters.

Example parameters:
- `app_id = YOUR_APP_ID`
- `app_key = YOUR_APP_KEY`
- `what = entry level data analyst`
- `where = India`
- `results_per_page = 10`

---

## 📧 Gmail Setup
To send mail using Gmail:
1. Create OAuth credentials in Google Cloud Console
2. Add redirect URL from n8n
3. Copy **Client ID** and **Client Secret**
4. Connect Gmail credentials in n8n

---

## 📂 Files Included
- `workflow.json` → Exported n8n workflow file

---

## ▶️ How to Use
1. Download the workflow JSON file.
2. Import it into n8n:
   - n8n → Workflows → Import from File
3. Add your Adzuna API keys.
4. Connect Gmail credentials.
5. Activate the workflow.

---

## 📌 Output Example
The email contains a formatted table with:
- Job Title
- Company
- Location
- Salary
- Apply Link

---

## 📅 Automation Schedule
Runs daily at:
**1:00 PM IST**

Cron Expression:
```cron
0 0 13 * * *
