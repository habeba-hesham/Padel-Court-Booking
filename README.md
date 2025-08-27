📰 Automated Padel Court Booking System
📌 Overview
This project is an automation workflow built with n8n that manages padel court reservations. It integrates with Google Forms to collect booking requests, Google Sheets for structured storage, and Google Calendar and Gmail to handle the booking process and notifications.

The system provides robust validation, ensuring that only valid bookings are created. It automatically rejects reservation requests for past dates or for courts that are already booked, and sends custom notifications to users explaining the outcome.

⚙️ Features
Date & Time Validation: Automatically checks if a requested court reservation is for a past date or time.

Availability Check: Scans Google Calendar to ensure the requested court time slot is not already booked.

Automated Booking: Creates new events in Google Calendar for all valid bookings.

Custom Notifications: Sends personalized email confirmations for successful bookings and rejection notices for invalid requests.

Data Logging: All booking requests, including their status (accepted, past date, or duplicate), are logged in Google Sheets.

🛠️ Tools & Technologies
n8n – Workflow automation platform.

Google Forms – Used to collect padel court reservation requests.

Google Sheets – Acts as the database for all booking requests.

Google Calendar API – For creating and checking court availability.

Gmail Integration – For sending email notifications.

🚀 How It Works
Trigger: The workflow starts when a new booking request is submitted via Google Forms, which automatically adds a new row to a Google Sheet.

Date & Time Check: An IF node evaluates if the submitted date and time are in the past. If the condition is false, the workflow is directed to send a rejection email.

Availability Check: The workflow searches Google Calendar for existing reservations at the same date and time.

Conditional Logic:

If the time slot is already booked, the workflow sends a rejection email to the user, explaining that the time is unavailable.

If the time slot is free, the workflow proceeds to create a new calendar event.

Event Creation & Notification: A new event is created in Google Calendar, and a confirmation email is sent to the user with the booking details.

📂 Project Structure
workflow.json – The exported n8n workflow file.

README.md – Project documentation.

workflow.png – A visual representation of the workflow.

📌 Setup & Usage
Set up your Google Forms, Google Sheets, and Google Calendar.

Install and run n8n (via npm, Docker, or cloud).

Import the workflow.json file into your n8n instance.

Configure your Google credentials for Google Sheets, Calendar, and Gmail.

Activate the workflow.







