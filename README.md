# Automate Daily Interview Schedule Delivery from Google Calendar to Gmail

### 📧 Morning Interview Briefing (n8n | Google Calendar | Gmail)

This workflow automatically fetches all interview events scheduled for the current day from a specific Google Calendar and sends a beautifully formatted HTML summary report to HR, hiring managers, or interviewers via Gmail. It ensures everyone is prepared for the day's recruitment tasks without manually checking calendars.

---

## ⚡ Quick Implementation Steps

- Import the workflow JSON into your [n8n account](https://n8n.partnerlinks.io/om1efg2qgvwi).
- Connect your **Google Calendar** and **Gmail** credentials.
- Open the **Set Config** node to define your Calendar ID and Recipient Email.
- Activate the workflow to start receiving daily summaries at your preferred time.

---

## 🎯 Who's It For

- **Recruiters & HR Managers:** Get a consolidated view of all interviews across different panels.
- **Hiring Teams:** Receive a daily briefing of their personal interview load.
- **Coordinators:** Automate the distribution of schedules to external stakeholders or vendors.

---

## 🛠 Requirements

| Tool                | Purpose                                          |
| :------------------ | :----------------------------------------------- |
| **[n8n account](https://n8n.partnerlinks.io/om1efg2qgvwi)**    | To run and schedule the daily automation         |
| **Google Calendar** | The source of truth for all scheduled interviews |
| **Gmail Account**   | To send the formatted schedule via email         |
| **Google OAuth2**   | Required credentials for Google service access   |

---

## 🧠 What It Does

- **Schedule Trigger:** Runs every morning (e.g., 8:00 AM) to prepare for the workday.
- **Data Fetching:** Pulls all events from a specific calendar starting from the current day.
- **Data Transformation:** Filters events to ensure only "Interviews" are processed and formats the time and candidate names.
- **HTML Styling:** Generates a clean, professional email table using inline CSS.
- **Automated Delivery:** Sends the final list to designated recipients automatically.

---

## 🧩 Workflow Components

- **Cron Node:** Set to trigger daily at a specific hour.
- **Google Calendar Node:** Fetches events for the current date.
- **Function/Set Node:** Logic to handle empty calendars and build the HTML report.
- **Gmail Node:** Sends the final report with a dynamic subject line (e.g., "Today's Interview Schedule - [Date]").

---

## 🔧 How To Set Up – Step-by-Step

1. **Import Workflow:** Upload the provided `.json` file into your n8n workspace.
2. **Set Credentials:**
   - **Google Calendar:** Connect your Google account via OAuth2.
   - **Gmail:** Connect your Gmail account via OAuth2.
3. **Update Configurations:**
   - Open the **Set Config** node.
   - `calendarId`: Enter your calendar email or ID.
   - `recipientEmail`: The email address where the report should be sent.
   - `reportTitle`: (Optional) Change the header of the email.
4. **Timezone Check:** Ensure your [n8n account](https://n8n.partnerlinks.io/om1efg2qgvwi) timezone matches your local time for accurate scheduling.
5. **Test & Enable:** Run the workflow manually once to verify the email looks correct, then toggle to **Active**.

---

## ✨ How To Customize

| Customization             | Method                                                                         |
| :------------------------ | :----------------------------------------------------------------------------- |
| **Change Timing**         | Adjust the Cron node schedule (e.g., to run weekly on Mondays).                |
| **Filter Keywords**       | Update the logic to only include events containing "Interview" or "Screening". |
| **Include Meeting Links** | Modify the HTML template to include the Google Meet or Zoom link.              |
| **Multiple Calendars**    | Add more Google Calendar nodes and merge them before the report.               |

---

## ➕ Add-ons (Advanced)

- **Candidate CVs:** Link to the candidate's CV (if stored in the event description) directly in the email.
- **Slack Cross-Post:** Send a summary to a private Slack channel in addition to Gmail.
- **SMS Alerts:** Use Twilio to send a text summary of the first interview of the day.

---

## 📈 Use Case Examples

- **Daily HR Brief:** A summary sent to the lead recruiter every morning at 8:30 AM.
- **Panel Preparation:** Send a list of candidates to technical interviewers for their specific slots.
- **Executive Summary:** A simplified view of all hiring activities sent to the CTO weekly.

---

## 🧯 Troubleshooting Guide

| Issue                 | Possible Cause            | Solution                                                                  |
| :-------------------- | :------------------------ | :------------------------------------------------------------------------ |
| **No email received** | No events found for today | Check if the Google Calendar has events scheduled for the current date.   |
| **Credential Error**  | OAuth2 token expired      | Re-authenticate the Google Calendar or Gmail node in credentials.         |
| **Empty Report**      | Wrong Calendar ID         | Ensure the `calendarId` in the Config node is the correct email address.  |
| **Wrong Time**        | Server Timezone mismatch  | Update the `N8N_GENERIC_TIMEZONE` environment variable in your n8n setup. |

---

## 📞 Need Assistance?

Need help integrating this into your recruitment workflow or adding more advanced filters?

👉 **Contact WeblineIndia** – Expert automation partners for HR and Enterprise workflows.
