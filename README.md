# EventForce Management System – Salesforce Implementation

## Project Overview

EventForce Management System is a Salesforce-based event management solution developed using Salesforce CRM, Salesforce Developer Edition, and Lightning Experience.

The system is designed to manage events, clients, vendors, venues, feedback, approvals, automation, security, reports, and operational activities through a centralized Salesforce application.

## Institution Details

**Institution:** Alpha College of Engineering, Thirumazhisai, Chennai  
**Project:** EventForce Management System – Salesforce Implementation  
**Platform:** Salesforce CRM / Salesforce Developer Edition  
**Application:** Event Planner  
**Dashboard:** EventForce Operations Dashboard  
**Report:** Upcoming Events by Month  
**Naan Mudhalvan Team ID:** 6ab4d5950fc666a751b54176

## Team Details

| Role in Project | Student Name | Register Number | College Email ID |
|---|---|---|---|
| Team Lead | Pratiksha.S | 210123205019 | pratiksha6380@gmail.com |
| Team Member | Sowmiya.A | 210123205501 | sowmiyapriyal77@gmail.com |
| Team Member | Shalini.A | 210123205027 | shalinianandhan54@gmail.com |
| Team Member | Lokesh.J | 210123205012 | lokeshjayaraman7299@gmail.com |
| Team Member | Aswin.S | 210123205002 | aswinx2k23@gmail.com |

## Project Objectives

The main objectives of the project are:

- To manage event information in a centralized Salesforce system.
- To maintain client, vendor, venue, and feedback information.
- To establish relationships between events and related records.
- To automate event-related processes and reminders.
- To manage event cancellation through an approval process.
- To prevent venue double-booking using Apex logic.
- To provide reports and dashboards for event monitoring.
- To implement appropriate security and access control.
- To support data migration and validation within Salesforce.

## Salesforce Data Model

The project uses the following custom objects:

| Custom Object | Purpose |
|---|---|
| Event__c | Stores event details such as name, date, type, status, and budget. |
| Client__c | Stores client information and contact details. |
| Vendor__c | Stores vendor information, service type, and status. |
| Venue__c | Stores venue details, location, capacity, and availability. |
| Feedback__c | Stores feedback, ratings, and comments related to events and clients. |
| EventVendor__c | Junction object used to associate events with multiple vendors. |

### Object Relationships

- Event to Client: Lookup Relationship
- Event to Venue: Lookup Relationship
- Feedback to Event: Lookup Relationship
- Feedback to Client: Lookup Relationship
- EventVendor to Event: Master-Detail Relationship
- EventVendor to Vendor: Master-Detail Relationship

## Automation and Business Logic

The system includes Salesforce automation and Apex-based processing.

### Salesforce Automation

- Record-triggered Flows
- Event reminder automation
- Validation Rules
- Formula Fields
- Approval Process for event cancellation

### Apex Components

The project includes Apex components for venue and event processing:

- `VenueStatusHelper`
- `PreventDoubleBooking`
- `BatchCompleteEvents`
- `ScheduleCompleteEvents`

Batch Apex and Scheduled Apex are used to process past events and update their completion status.

## Security and Access Control

The project applies Salesforce security mechanisms to control access to records and functionality.

The implementation includes:

- Profiles
- Roles
- Permission Sets
- Organization-Wide Defaults
- Sharing Rules

The Event object is configured with Private Organization-Wide Default access as documented in the project implementation.

The project defines access requirements for roles such as:

- Event Administrator
- Event Coordinator
- Vendor Manager
- Client

## Reports and Dashboard

The Salesforce implementation includes:

**Report:** Upcoming Events by Month

**Dashboard:** EventForce Operations Dashboard

These components provide an overview of event-related information and support operational monitoring.

## Data Migration

Data migration is performed using the Salesforce Data Import Wizard.

The migration process includes:

1. Preparing the source data.
2. Validating the data before import.
3. Importing records into Salesforce.
4. Checking the imported records.
5. Verifying relationships and data accuracy.

## Testing

Testing is performed to verify:

- Data accuracy
- Object relationships
- Automation
- Approval processes
- Venue availability
- Double-booking prevention
- User permissions
- Reports and dashboard functionality
- Overall operational functionality

## Project Development Phases

The project is organized into the following phases:

1. Requirement Analysis and Planning
2. Backend Development and Configuration
3. UI/UX Development and Customization
4. Data Migration, Testing and Security
5. Deployment, Documentation and Maintenance

## Deployment

The project was developed and tested using Salesforce Developer Edition for academic purposes.

Production deployment was not performed as part of the academic implementation. A production deployment would require the appropriate Salesforce deployment process and complete Apex test coverage.

## Live Salesforce Org

[Open Salesforce Org](https://orgfarm-28f875b58c-dev-ed.develop.lightning.force.com/)

## Official Project Report

**Official PDF Report (.pdf):** EVENTFORCE MANAGEMENT SYSTEM DOCUMENT(IMPORTANT).pdf  
**Salesforce Implementation Screenshots:** Phase 2- part 1(screenshots),Phase 2 -part 2 (Screenshots),Phase 3-(screenshots),Phase 4-(screenshots)

## Project Limitations

- The implementation was developed in Salesforce Developer Edition for academic purposes.
- Production deployment was not performed.
- Advanced external integrations are outside the current implementation scope.
- The system can be further enhanced for larger-scale operational use.

## Future Scope

Possible future enhancements include:

- Production deployment
- Advanced event automation
- Enhanced vendor management
- Advanced analytics
- External system integrations
- Mobile accessibility
- Scalability improvements
- Additional automation and optimization

## Conclusion

The EventForce Management System demonstrates the implementation of an event management solution using Salesforce CRM. The system combines custom objects, relationships, automation, Apex, security controls, data migration, reports, and dashboards to support event management activities in a centralized platform.

## Repository Note

This README contains the project reference names for the Salesforce implementation screenshots. The screenshot files are not uploaded to this README repository.
