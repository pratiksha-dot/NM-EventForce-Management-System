# Phase 3 – UI/UX Development & Customization

## 1. Phase Overview

Phase 3 focuses on creating a simple and user-friendly interface for the EventForce Management System.

The phase uses Salesforce Lightning features to organize the EventForce modules into a centralized application and provide reports and dashboards for monitoring event operations.

## 2. Lightning App

A custom Lightning App named:

**Event Planner**

was created for the EventForce Management System.

The application provides a centralized workspace for accessing the major EventForce modules.

### Main Modules

- Events
- Clients
- Vendors
- Venues
- Feedback

The Lightning App brings these modules together so users can navigate between the different areas of the event management system from a single Salesforce application.

## 3. Custom Object Navigation

The EventForce application uses Salesforce custom objects to organize the system's business data.

The primary modules are:

### Events
Used to manage event information, including event date, event type, status, budget, client, and venue.

### Clients
Used to manage client contact and address information.

### Vendors
Used to manage vendor details, service type, contact information, and status.

### Venues
Used to manage venue details, capacity, location, and availability.

### Feedback
Used to maintain feedback, ratings, comments, and related event/client information.

## 4. Reports

Reports were included to provide analytical information about event operations.

### Upcoming Events by Month

An upcoming-events report was developed to organize event information for monitoring.

The report includes information such as:

- Event Name
- Event Date
- Event Type
- Client
- Venue
- Event Budget

The report is intended to support tracking of upcoming event activity.

## 5. Dashboard

A dashboard named:

**EventForce Operations Dashboard**

was developed to provide a visual summary of event operations.

The dashboard uses the upcoming-events reporting data to present event information in a graphical format.

### Dashboard Configuration

The project documentation specifies an upcoming-events visualization with:

- Donut chart
- Upcoming Events Overview subtitle
- Maximum of 6 displayed values
- Light dashboard theme

The dashboard provides a quick visual view of upcoming event activity.

## 6. User Interface Goals

The UI/UX implementation focuses on:

- Simple navigation
- Centralized access to EventForce modules
- Organized Salesforce Lightning workspace
- Easy access to operational information
- Visual representation of event data
- Improved monitoring through reports and dashboards

## 7. Phase 3 Outcome

Phase 3 provides the user-facing structure of the EventForce Management System. The Lightning App organizes the core modules, while reports and dashboards provide structured and visual access to operational information.

## Source

Based on the EventForce Management System Salesforce implementation documentation and the retrieved Salesforce project metadata.
