🔎 LinkedIn Job Scraper with Automated Email Alerts
This project automates the job-hunting process using a data engineering pipeline built on Azure. It scrapes job listings from LinkedIn based on user-defined parameters, then sends the results via email using Logic Apps.

🚀 Overview
An end-to-end pipeline built with Azure Data Factory and Azure Databricks, integrated with Webhook and Logic Apps, to extract job listings and notify users via customized email alerts. It's fully parameterized and can be scheduled to run at specific intervals.

🧩 How It Works
1. User Inputs via ADF Pipeline
   The pipeline accepts the following parameters:

   > job_role (e.g., Data Engineer)

   > location (e.g., Remote, US)

   > work_type, experience, keywords, posted_hours_ago

2. Databricks Notebook Executes Scraper
   The notebook:

   > Builds the LinkedIn job search URL based on parameters

   > Sends HTTP requests and parses job listings using BeautifulSoup

   > Filters jobs by:

      >> Matching keywords in the job description

      >> Work type (e.g., remote-only)

      >> Experience level

   > Stores all matching jobs in a structured JSON format

3. Webhook Sends Scraped Data to Logic App
   > Once the notebook finishes execution, the output JSON is passed to a Webhook, which triggers a Logic App.

4. Logic App Sends Customized Email
   > The Logic App:

    >> Parses the JSON output

    >> Formats the job listings

    >> Sends an email to the user (or multiple recipients) with the results

5. Scheduled Execution
   > The ADF pipeline can be scheduled to run periodically (e.g., every 6 hours) to automate the job search.

✨ Features
✅ Custom job search with filters (role, type, location, experience, etc.)

📩 Beautifully formatted emails with matching job listings

🔁 Schedule to run automatically at custom intervals

👥 Email alerts can be sent to multiple recipients

🛠️ Tech Stack
Azure Data Factory – Pipeline orchestration

Azure Databricks – Job scraper logic (Python)

Azure Webhook – Triggers the email service

Azure Logic Apps – Email formatting & delivery

Python Libraries – BeautifulSoup, requests, json, time

▶️ How to Use
Go to ADF Pipeline and enter:

Job Role, Location, Experience, Work Type, Keywords, Posted Hours Ago

Set the recipient email(s) in the Logic App

Trigger the pipeline manually or on a schedule

Check your inbox for the job listing results

👤 Intended Audience
Data Engineers interested in pipeline automation

Recruiters/Job Seekers wanting regular, filtered job alerts
