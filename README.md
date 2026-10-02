# EventForce Management System --- Salesforce Implementation

> A Salesforce CRM solution for centralizing and automating event
> planning operations, including event scheduling, client management,
> venue reservations, vendor coordination, cancellation approvals,
> reminders, feedback, reporting, and security.

## Project & Institution Details

  -----------------------------------------------------------------------
  Item                                Details
  ----------------------------------- -----------------------------------
  **Project Title**                   EventForce Management System --
                                      Salesforce Implementation

  **Institution**                     Alpha College of Engineering,
                                      Thirumazhisai, Chennai

  **Team ID**                         `6ab4d4f2b5170a9b58b51c5d`

  **Platform**                        Salesforce CRM / Developer Edition
  -----------------------------------------------------------------------

### Team Members

  Role          Student
  ------------- -------------
  Team Lead     Pratiksha S
  Team Member   Sowmiya A
  Team Member   Shalini A
  Team Member   Aswin S
  Team Member   Lokesh J

## Project Overview

The EventForce Management System is a Salesforce-based CRM solution
designed to centralize and streamline event planning and management
operations.

The system manages Events, Clients, Venues, Vendors, Event--Vendor
assignments, Feedback, and event cancellations. It combines Salesforce
custom objects, relationships, validation rules, formula fields, Flows,
Approval Processes, Apex Triggers and Classes, Reports, Dashboards, and
role-based security.

## Objectives

-   Centralize event, client, venue, vendor, and feedback information.
-   Streamline event booking and venue reservation.
-   Prevent venue double bookings.
-   Automate event reminders.
-   Provide a controlled event cancellation approval process.
-   Improve stakeholder coordination.
-   Capture and manage client feedback.
-   Provide operational reports and dashboards.
-   Maintain controlled access through Salesforce security.
-   Support data migration through the Salesforce Data Import Wizard.

## Key Features

### Event Management

Manages Event Name, Event Type, Event Date, Event Status, Event Budget,
Client, and Venue.

### Client Management

Maintains client name, email, phone, address, country, and city.

### Venue Management

Maintains venue address, location, capacity, and availability status.
Apex logic supports venue availability validation and double-booking
prevention.

### Vendor Management

Maintains vendor details, service type, contact information, and status.
The `EventVendor` junction object supports the Event--Vendor
many-to-many relationship.

### Feedback Management

Stores client ratings and comments and links feedback to Events and
Clients.

### Automation

Uses Salesforce Flows for event reminders and process updates.

### Cancellation Approval

Uses an Approval Process for controlled event cancellation requests,
notifications, and status updates.

## System Architecture

``` text
Users / Event Team
        |
        v
Salesforce Lightning App
        |
        v
+-----------------------------+
|       EventForce CRM        |
+-----------------------------+
        |
        +-----------------------------+
        |                             |
        v                             v
 Custom Objects                 Automation
        |                             |
        |                    +--------+--------+
        |                    |        |        |
        v                    v        v        v
 Event                    Flows   Approval   Apex
 Client
 Vendor
 Venue
 Feedback
 EventVendor
        |
        v
 Reports & Dashboards
        |
        v
 Operational Monitoring
```

## Salesforce Data Model

  Object             Purpose
  ------------------ ---------------------------------------------------------
  `Event__c`         Event information, status, date, type, and budget
  `Client__c`        Client information and contact details
  `Vendor__c`        Vendor details, services, and status
  `Venue__c`         Venue information, capacity, location, and availability
  `Feedback__c`      Client ratings and comments
  `EventVendor__c`   Junction object connecting Events and Vendors

### Relationships

``` text
Event ───────────────> Client
  |
  └──────────────────> Venue

Event <──── EventVendor ────> Vendor

Feedback ────────────> Event
Feedback ────────────> Client
```

## Automation & Business Logic

### Salesforce Flows

-   Event reminders
-   Process updates
-   Feedback notifications
-   Approval-related updates

### Approval Process

``` text
Cancellation Request
        ↓
Approval Process
        ↓
Approved / Rejected
        ↓
Event Status Update
        ↓
Notifications
```

### Validation Rules

Validation Rules maintain data quality, including client email
validation.

### Formula Field

The Event Budget is calculated automatically from Event Type.

### Apex

Advanced logic includes venue availability updates, double-booking
prevention, batch processing of completed events, and scheduled
processing. The documented implementation includes `VenueStatusHelper`,
`PreventDoubleBooking`, `BatchCompleteEvents`, and
`ScheduleCompleteEvents`.

## Security & Access Control

The system uses:

-   Profiles
-   Roles
-   Permission Sets
-   Organization-Wide Defaults (OWD)
-   Sharing Rules
-   Object and field permissions

Documented roles include Event Administrator, Event Coordinator, Vendor
Manager, and Client.

## Reports & Dashboards

The system provides operational reporting including:

-   Upcoming Events by Month
-   Event schedules
-   Vendor activities
-   Event budgets
-   Event performance
-   Client feedback
-   EventForce Operations Dashboard

## Project Development Phases

### Phase 1 --- Requirement Analysis & Planning

Defined the problem statement, stakeholders, requirements, customer
journey, data flow, technology stack, and solution architecture.

### Phase 2 --- Backend Development & Configurations

Implemented custom objects, fields, relationships, formula fields,
validation rules, Flows, Approval Process, Apex Classes, Apex Triggers,
Batch Apex, and Scheduled Apex.

### Phase 3 --- UI/UX Development & Customization

Configured the Event Planner Lightning App, navigation items, object
tabs, page layouts, reports, and EventForce Operations Dashboard.

### Phase 4 --- Data Migration, Testing & Security

Performed Data Import Wizard migration, pre-validation, user creation,
Profiles, Roles, Permission Sets, Sharing Rules, OWD configuration, and
functional/security testing.

### Phase 5 --- Deployment, Documentation & Maintenance

The project was developed and tested in a Salesforce Developer Edition
for academic purposes. Production deployment was not performed. The
documentation describes the deployment and maintenance approach for a
future real-world implementation.

## Screenshots

Store your screenshots in the repository as:

``` text
screenshots/
├── Phase2/
├── Phase3/
└── Phase4/
```

### Phase 2 --- Backend Development & Configuration

Custom objects, fields, relationships, formula fields, validation rules,
approval processes, Flows, and Apex.

[View Phase 2 Screenshots](screenshots/Phase2/)

### Phase 3 --- UI/UX Development & Customization

Lightning App, navigation, tabs, layouts, reports, and dashboard.

[View Phase 3 Screenshots](screenshots/Phase3/)

### Phase 4 --- Data Migration, Testing & Security

Data Import Wizard, imported records, Profiles, Roles, Permission Sets,
Sharing Rules, OWD, and testing evidence.

[View Phase 4 Screenshots](screenshots/Phase4/)

## Testing

Testing covered:

  Area                        Validation
  --------------------------- ------------------------------------------
  Data Accuracy               Records and field values
  Automation                  Flows, reminders, approvals, and updates
  Venue Validation            Availability and double-booking logic
  Security                    User access and permissions
  Reports                     Reports and dashboard information
  Operational Functionality   Core event-management workflows

## Advantages

-   Centralized event-management data
-   Reduced manual processing
-   Automated reminders and processes
-   Venue double-booking prevention
-   Controlled cancellation workflow
-   Better operational visibility
-   Role-based security
-   Improved data quality
-   Scalable Salesforce platform

## Limitations

-   Developed using Salesforce Developer Edition for academic purposes.
-   Production deployment was not performed.
-   Real-world deployment may require sandbox environments and
    deployment tooling.
-   Flows, Apex, Approval Processes, validation rules, and sharing
    settings require ongoing maintenance.
-   Production deployment would require appropriate Apex test classes
    and validation.

## Future Scope

-   Production Salesforce deployment
-   Advanced event automation
-   Enhanced vendor management
-   Advanced analytics
-   Additional reports and dashboards
-   External integrations
-   Mobile accessibility
-   Further optimization of event operations

## Project Structure

``` text
NMProject-EventForce-Management-System/
│
├── README.md
├── screenshots/
│   ├── Phase2/
│   ├── Phase3/
│   └── Phase4/
├── documentation/
│   └── EventForce-Management-System-Documentation.pdf
└── other project files/
```

## Technology Stack

  Layer            Technology
  ---------------- ------------------------------------------------------
  CRM Platform     Salesforce CRM / Developer Edition
  User Interface   Salesforce Lightning App
  Database         Salesforce Custom Objects
  Business Logic   Salesforce Flows, Formula Fields, Validation Rules
  Approval         Salesforce Approval Process
  Automation       Record-Triggered Flows, Apex Triggers
  Processing       Batch Apex, Scheduled Apex
  Security         Profiles, Roles, Permission Sets, Sharing Rules, OWD
  Reporting        Salesforce Reports & Dashboards
  Data Migration   Salesforce Data Import Wizard

## Academic Project

This project was developed as a Salesforce CRM implementation for
academic purposes and demonstrates Salesforce objects, automation, Apex
logic, security, data migration, reports, and dashboards for an
event-management use case.

**Alpha College of Engineering, Thirumazhisai, Chennai**

**Team ID:** `6ab4d4f2b5170a9b58b51c5d`
