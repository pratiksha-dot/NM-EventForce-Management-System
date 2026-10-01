# EventForce Management System

## Salesforce Implementation Project

EventForce Management System is a Salesforce-based event management solution developed to organize and manage events, clients, vendors, venues, and feedback through a centralized CRM platform.

The project demonstrates Salesforce data modeling, automation, Apex development, Lightning App customization, security configuration, testing, reporting, and Git-based version control.

---

## Project Objectives

The main objectives of the EventForce Management System are:

- Manage event information in a centralized Salesforce application.
- Maintain client, vendor, venue, and feedback records.
- Establish relationships between the major business entities.
- Automate important event-management activities.
- Prevent invalid data and duplicate venue bookings.
- Manage event cancellation requests through an approval process.
- Provide reminders for upcoming confirmed events.
- Automatically update past event statuses.
- Control user access through Salesforce security features.
- Provide reports and dashboards for operational monitoring.

---

## Salesforce Data Model

The project uses the following custom objects:

| Object | Purpose |
|---|---|
| Event__c | Stores event information and event status |
| Client__c | Stores client contact and address information |
| Vendor__c | Stores vendor and service information |
| Venue__c | Stores venue information and availability |
| Feedback__c | Stores client/event feedback and ratings |
| EventVendor__c / Event_Vendor__c | Provides the event-vendor relationship structure |

### Important Relationships

- Event → Client
- Event → Venue
- Feedback → Event
- Feedback → Client
- Event → Vendor through the Event Vendor relationship structure

---

## Automation and Backend Development

### Validation Rule

**Email_Valid_Address**

Validates Client email addresses before the record is saved.

### Flow

**Client_Reminder_3_Days_Before**

A record-triggered Flow with a scheduled path that sends a reminder three days before the Event Date for qualifying confirmed events.

### Approval Process

**Event Cancellation Request Notification**

Provides an approval workflow for event cancellation requests and uses an email notification for the relevant Event Coordinator.

### Apex Classes

- `VenueStatusHelper`
- `BatchCompleteEvents`
- `ScheduleCompleteEvents`

### Apex Triggers

- `EventTrigger13`
- `PreventDoubleBooking`

The Apex implementation supports venue availability updates, prevention of duplicate venue bookings, and automatic completion of past events.

---

## Lightning App

The project includes a custom Lightning App:

**Event Planner**

The application provides centralized access to the main EventForce modules:

- Events
- Clients
- Vendors
- Venues
- Feedback

---

## Reports and Dashboard

The project includes reporting and dashboard functionality for operational monitoring.

### Upcoming Events by Month

The report is designed to organize upcoming event information including event name, date, type, client, venue, and budget.

### EventForce Operations Dashboard

The dashboard provides a visual summary of upcoming event activity using the project reporting data.

---

## Security

The EventForce implementation includes Salesforce security configuration using:

### Profiles

- Event Admin
- Event Coordinator
- Vendor Manager
- Client

### Roles

- Event Admin
- Event Coordinator
- Vendor Manager
- Client

### Permission Set

- Feedback Manager

### Record Access

The Event object uses restricted record access together with sharing configuration for controlled access.

---

## Project Phases

The repository is organized according to the five project phases.

### Phase 1 – Requirement Analysis

Defines the project scope, objectives, business entities, data architecture, relationships, and functional requirements.

### Phase 2 – Backend Development

Implements validation rules, Flow automation, approval processing, Apex classes, and Apex triggers.

### Phase 3 – UI/UX Development & Customization

Implements the Lightning App, module navigation, reports, and dashboard functionality.

### Phase 4 – Data Migration, Testing & Security

Covers data migration, user access, profiles, roles, permission sets, sharing, and functional testing.

### Phase 5 – Deployment, Documentation & Maintenance

Covers deployment preparation, version control, documentation, troubleshooting, and ongoing maintenance.

---

## Repository Structure

```text
EventForce/
│
├── phase-1-requirement-analysis/
├── phase-2-backend-development/
├── phase-3-ui-ux-customization/
├── phase-4-data-migration-testing-security/
├── phase-5-deployment-documentation-maintenance/
│
├── force-app/
│   └── main/
│       └── default/
│           ├── applications/
│           ├── approvalProcesses/
│           ├── classes/
│           ├── flows/
│           ├── objects/
│           ├── permissionsets/
│           ├── profiles/
│           ├── roles/
│           └── triggers/
│
├── config/
├── scripts/
Technologies Used
Salesforce Lightning Platform
Salesforce Custom Objects
Salesforce Flows
Salesforce Approval Processes
Apex
Salesforce Profiles and Roles
Permission Sets
Reports and Dashboards
Salesforce DX
Git
GitHub
Development Environment

The EventForce Management System was developed and tested in a Salesforce Developer Edition environment.

The project source metadata is maintained using a Salesforce DX project structure and Git version control.

Actual production deployment was outside the scope of the academic implementation.

Version Control

The project is maintained using Git and GitHub.

The repository contains the retrieved Salesforce metadata together with documentation for all five implementation phases.

Project Outcome

The EventForce Management System demonstrates how Salesforce can be used to build an integrated event-management solution combining structured data, automation, business logic, security, reporting, and user-interface customization.

The repository provides both the Salesforce source metadata and phase-wise project documentation for review and maintenance.

Repository

GitHub:

https://github.com/pratiksha-dot/Nm-project-Event-management-system
├── sfdx-project.json
├── package.json
└── README.md
