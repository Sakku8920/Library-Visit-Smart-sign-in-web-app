Installation Guide — Library Visit Web App

This guide explains how to set up, deploy, and run the Library Visit Web App using Google Sheets and Google Apps Script. The web app tracks member visits, records “Visit In” and “Visit Out” times, and stores logs automatically in a Google Sheet.

Requirements

Before you begin, make sure you have:

A Google Account

Access to Google Sheets

Basic familiarity with Google Apps Script

(Optional) A GitHub account for version control and sharing

Step 1 — Create the Google Sheet

Go to Google Sheets
 and create a new spreadsheet.

Rename it: Library_Visit_Records

Create the following three sheets (tabs) with these headers in the first row:
Sheet 1 — Members
MemberID | Name | Additional | PhotoURL | Course
Sheet 2 — Visits
Timestamp | MemberID | Action | Note | RecordedBy | Timezone
Sheet 3 — Settings
Key | Value

(Optional) Add admin emails in the Settings sheet:
admins | yourname@gmail.com, anotheradmin@gmail.com

Step 2 — Open the Apps Script Editor

In your spreadsheet, go to Extensions → Apps Script.

This opens the Apps Script editor connected to your sheet.

Delete any default code.

Step 3 — Add the Code Files

Create two files:
File 1: Code.gs
Click “+” → Script, name it Code.gs, and paste the backend code.
File 2: index.html
Click “+” → HTML, name it index.html, and paste the frontend HTML code. Save all files.

Step 4 — Run Initialization

From the function dropdown, select addSampleMember.

Click Run to create example members and initialize sheets.

Approve permissions when prompted (Review permissions → Allow).

Step 5 — Deploy as a Web App

Click Deploy → New Deployment.

Under Select type, choose Web app.

Fill in:
Description: Library Visit Tracker
Execute as: Me
Who has access: Anyone (or Anyone with Google Account)

Click Deploy, authorize, and click Allow.

Copy the Web App URL — this is your live app link.

Step 6 — Test the App

Open the deployed Web App URL in a browser.

Search by name or Member ID.

If there are multiple matches, confirm with Member ID and Course.

Click Visit In or Visit Out — animated dialogs will appear, and visit history updates automatically in the Visits sheet.

Step 7 — Theme Toggle (Day/Night)

Use the theme toggle to switch between light and dark modes. The app remembers your last choice automatically.

Step 8 — Admin Features

If your email is listed under admins in the Settings sheet, you will see extra options:

Export Today’s Visits: Generates a downloadable CSV file in Google Drive.

Generate Duration Report: Creates a sheet summarizing total time spent in the library.

Troubleshooting
Issue	Solution
“Member not found”	Check if MemberID or Name exists in the Members sheet.
“Server error”	Reload the app and verify Apps Script permissions.
UI not updating	Redeploy the web app after editing the HTML.
No timestamp recorded	Check sheet permissions and script runtime access.
Optional — GitHub & clasp (Version Control)

Install clasp: npm install -g @google/clasp

Login: clasp login

Create project: clasp create --title "Library Visit App" --type sheets

Push code: clasp push

Deploy: clasp deploy --description "Public web app"

Folder Structure
/Library-Visit-App
├── Code.gs
├── index.html
├── README.md
├── LICENSE
└── assets/

Author

Created by Saket Sharma
Library Assistant | Web Developer | Tech Curator
