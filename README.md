# n8n Customer Inquiry Automation

An end-to-end customer inquiry automation workflow built with **n8n and Airtable**.

The workflow receives customer inquiries from a website webhook, validates and classifies the submission, checks for duplicate contacts, creates or updates Airtable records, sends email notifications, and automatically creates a follow-up reminder for unresolved inquiries.

## 🚀 Features

- Website form submission via webhook
- Input validation
- Duplicate contact detection
- Create new Airtable inquiry records
- Update existing contacts
- High-priority inquiry classification
- Internal email notifications
- Customer confirmation emails
- Two-business-day follow-up check
- Automated follow-up reminders
- Conditional workflow routing
- Basic error handling

## 🔄 Workflow

```text
Website Form
     ↓
Webhook
     ↓
Validate & Classify
     ↓
Valid Inquiry?
   ↙       ↘
 No         Yes
 ↓           ↓
Error    Find Duplicate
             ↓
        Duplicate?
        ↙        ↘
      Yes         No
       ↓           ↓
    Update       Create
       ↘          ↙
        Prepare Follow-up
               ↓
         High Priority?
          ↙          ↘
        Yes           No
         ↓             ↓
Internal Notification
          ↘          ↙
       Customer Confirmation
               ↓
       Wait 2 Business Days
               ↓
       Check Inquiry Status
               ↓
        Needs Follow-up?
          ↙          ↘
        Yes           No
         ↓             ↓
 Follow-up Reminder   Stop
