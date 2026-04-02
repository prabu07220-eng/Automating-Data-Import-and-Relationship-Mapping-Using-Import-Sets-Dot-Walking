# Automating-Data-Import-and-Relationship-Mapping-Using-Import-Sets-Dot-Walking

#Overview

This project demonstrates how to automate the process of importing structured data into ServiceNow and dynamically map hierarchical relationships using Import Sets and Dot Walking.
The solution focuses on maintaining accurate relationships—such as Employee → Department → Manager—and ensuring the correct dependent information is displayed automatically on ServiceNow forms (e.g., showing the Manager Email when an Incident is assigned to an employee).

 # Objectives
 
Automate the import of employee data (Name, Email, Department, Manager) from an external system.
Map imported data into ServiceNow system tables using Transform Maps.
Utilize dot walking to fetch hierarchical values such as:
Employee’s Department
Department Manager
Manager Email
Auto-populate related data (e.g., Manager Email) on forms like the Incident form.
Key Features

1️⃣ Automated Data Import
Imports data via CSV, JSON, API, or SFTP.
Runs manually or on a scheduled basis.
Ensures complete and incremental (delta) updates.

2️⃣ Relationship Mapping
Maps employees to:
Department
Reporting Manager
Automatically updates or creates missing records during the transform process.

3️⃣ Dot Walking for Related Data
Dot Walking is used to retrieve:
Department → Manager
Manager → Email
Employee → Department → Manager Email
This ensures dependent values flow automatically without separate queries.

4️⃣ Auto-Population on Incident Form
When an employee is selected in the Assigned To field:
The system identifies the employee’s department
Extracts the manager’s email via dot walking
Displays it in a field like Manager Email

 # System Components

🔹 Import Set Table
Stores raw input data from the external system.
🔹 Transform Map
Maps fields from Import Set to:
sys_user
cmn_department
Any custom fields
🔹 Data Lookup Logic
Uses dot walking to fetch:

assigned_to.department.manager.email
🔹 Incident Form Automation
Form scripts / business rules ensure the Manager Email field auto-fills.
🧪 Testing Steps
✔ Employee Import Validation
Upload or schedule data import.
Validate that User, Department, and Manager values are created/updated.
✔ Relationship Mapping Validation
Open user record.
Confirm correct Department and Manager associations.
✔ Incident Auto-Fill Test
Open a new Incident.
Select Assigned To = Employee.
Ensure Manager Email automatically appears.


# Login credentials
Username: admin
Password: admin123
