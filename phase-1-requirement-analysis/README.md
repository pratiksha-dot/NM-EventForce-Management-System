# Phase 1 – Requirement Analysis

## 1. Project Overview

The EventForce Management System is a Salesforce-based event management solution designed to organize and manage event-related information through a centralized CRM platform.

The project uses Salesforce to manage events, clients, vendors, venues, and feedback while providing a structured foundation for automation, security, reporting, and dashboard-based monitoring.

## 2. Project Objectives

The main objectives of the EventForce Management System are:

- Centralize event management information in Salesforce.
- Manage client information and their associated events.
- Maintain vendor and venue information.
- Manage feedback associated with events and clients.
- Establish relationships between the different modules.
- Provide a foundation for automation and business rules.
- Support secure access through Salesforce users, profiles, roles, and permission sets.
- Provide reports and dashboards for monitoring event operations.

## 3. Salesforce Data Architecture

The project uses the following custom objects:

### Event__c
Stores event information such as:
- Event Name
- Event Date
- Event Type
- Event Status
- Event Budget
- Client
- Venue

### Client__c
Stores client information such as:
- Client Name
- Email
- Phone
- Address
- Country
- City

### Vendor__c
Stores vendor information such as:
- Vendor Name
- Email
- Phone
- Service Type
- Status

### Venue__c
Stores venue information such as:
- Venue Name
- Address
- Location
- Capacity
- Availability Status

### Feedback__c
Stores feedback information including:
- Feedback ID
- Rating
- Comments
- Related Event
- Related Client

### EventVendor__c / Event_Vendor__c
The project contains the Event Vendor relationship structure used to connect events and vendors.

## 4. Relationships

The system establishes relationships between the major business entities.

- Event is associated with a Client.
- Event is associated with a Venue.
- Feedback is associated with an Event.
- Feedback is associated with a Client.
- Events and Vendors are connected through the Event Vendor relationship structure.

The Feedback Event lookup also uses a lookup-filter concept so that events associated with the selected client can be restricted when entering feedback.

## 5. Functional Scope

The requirements identified for the project cover:

1. Event management
2. Client management
3. Vendor management
4. Venue management
5. Feedback management
6. Event-vendor association
7. Data validation
8. Workflow and automation
9. User access and security
10. Reports and dashboards

## 6. Expected Salesforce Solution

The requirements form the foundation for the later implementation phases:

- Custom Salesforce objects and fields
- Relationships and lookup filters
- Validation Rules
- Record-triggered and scheduled automation
- Approval Process
- Apex Classes and Triggers
- Lightning App
- Profiles, Roles, Permission Sets and Sharing
- Reports and Dashboards

## 7. Phase 1 Outcome

Phase 1 establishes the business scope and Salesforce data structure required for the EventForce Management System. The identified objects, fields, relationships, users, automation requirements, security requirements, and reporting requirements provide the foundation for the subsequent development phases.

## Source

Based on the EventForce Management System Salesforce implementation documentation.
