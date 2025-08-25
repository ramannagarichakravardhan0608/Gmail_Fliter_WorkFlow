This project is an end-to-end workflow built in n8n that automates the process of capturing leads from a form, storing them in Google Sheets, filtering based on their occupation, and sending personalized Gmail notifications.

Features

 Automated Lead Capture → Collects form submissions with fields like First Name, Last Name, Email, and Occupation.

 Smart Data Storage → Appends or updates rows in Google Sheets, preventing duplicate entries using the Email field.

 Conditional Filtering → Filters out non-student occupations before processing further.

 Dynamic Email Notifications → Sends different Gmail alerts based on the occupation (Doctor / Engineer).

 Unified Notifications → Regardless of occupation, a final summary notification is sent.

  Workflow Steps

Form Submission

Triggered when a user fills out and submits the form.

Captures details: First Name, Last Name, Email, Occupation.

 Google Sheets (Append/Update)

Saves form data in Google Sheets.

Uses Email as the matching column to avoid duplicates.

 Filter

Removes records where the occupation is not equal to "student".

 Switch

Routes data based on Occupation:

Doctor → Sends an email with subject hello and message doctor lead.

Engineer → Sends an email with subject hello and message enginner lead.

 Merge

Merges outputs from different occupation-based Gmail messages.

 Final Notification

Sends a general Gmail notification with the message:

You have a new lead message.

 Technologies Used

n8n
 Workflow automation platform

Google Sheets API - For storing and updating lead data

Gmail API - For sending automated emails

Example Workflow

Case 1 – Engineer

User submits form → Data stored in Google Sheets

Workflow detects occupation = Engineer

Email sent: "enginner lead"

Final summary email: "You have a new lead message"

Case 2 – Doctor

User submits form → Data stored in Google Sheets

Workflow detects occupation = Doctor

Email sent: "doctor lead"

Final summary email: "You have a new lead message"

Case 3 – Student

User submits form → Data stored in Google Sheets

Filter bypasses occupation = student

Only final summary email: You have a new lead message


Workflow Structure

Form Submission → Google Sheets → Filter → Switch → Gmail (Doctor/Engineer) 
                   ↓
                Merge → Final Gmail Notification

 Benefits

 Eliminates manual data entry.

 Provides real-time lead notifications.

 Ensures data consistency across Google Sheets.

 Easily customizable for new occupations or notification rules.


Future Improvements

Add Slack or Microsoft Teams integration for instant team alerts.

Use a database (Postgres/MySQL) instead of Google Sheets for scalability.

Add lead scoring based on occupation or custom rules.

Workflow Preview (n8n Editor Screenshot Recommended)

<img width="1228" height="447" alt="Screenshot 2025-08-07 at 7 09 29 PM" src="https://github.com/user-attachments/assets/7c47ea1b-21c3-41ce-9a04-c95a12097eb6" />
  
