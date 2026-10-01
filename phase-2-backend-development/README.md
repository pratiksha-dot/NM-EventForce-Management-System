# Phase 2 – Backend Development

## 1. Phase Overview

Phase 2 focuses on developing the backend functionality of the EventForce Management System. The phase transforms the basic Salesforce data structure into an automated system by implementing validation rules, flows, approval processes, Apex classes, and triggers.

## 2. Validation Rule

A validation rule was implemented for the Client object to validate the email address entered by the user.

### Validation Rule
**Object:** Client__c  
**Rule Name:** Email_Valid_Address

The rule uses a regular expression to verify that the email follows a valid email-address format.

**Error Message:**
> Please Enter Valid Email Address

This prevents invalid email addresses from being saved in Client records.

## 3. Three-Day Event Reminder Flow

A record-triggered Flow named:

**Client_Reminder_3_Days_Before**

was implemented for the Event object.

### Flow Conditions

The reminder is associated with events that meet the required conditions, including:

- Event Status is Confirmed.
- A valid client email address is available.
- The Event Date is used as the time source.

### Scheduled Path

A scheduled path named:

**3_Days_Before**

runs three days before the Event Date.

The Flow sends a reminder email to the relevant client before the confirmed event.

## 4. Event Cancellation Approval Process

An Approval Process was implemented for handling event cancellation requests.

### Approval Process
**Event Cancellation Request Notification**

The process uses an email alert:

**Alert - Event Cancellation Request**

and the associated email template:

**Event Cancellation Request Notification**

The Event Coordinator is involved in the cancellation approval process.

This provides a controlled process for handling cancellation requests instead of allowing cancellation-related actions to occur without approval.

## 5. Apex Class – VenueStatusHelper

The `VenueStatusHelper` class contains reusable business logic for updating venue availability.

When an Event is confirmed, the associated venue is changed to:

**Reserved**

When an Event is canceled, the associated venue is changed to:

**Available**

The class uses a list of Event records and performs the corresponding venue updates.

## 6. Apex Trigger – EventTrigger13

The `EventTrigger13` trigger executes after Event records are inserted or updated.

It calls:

`VenueStatusHelper.updateVenueStatus(Trigger.new);`

This connects the Event record changes with the venue availability logic implemented in the helper class.

## 7. Apex Trigger – PreventDoubleBooking

The `PreventDoubleBooking` trigger executes before Event records are inserted or updated.

The trigger checks events that use the same venue and compares their event dates.

If an existing event already uses the same venue on the same date, the new or updated Event record receives the error:

> This Venue is already booked on this date.

This prevents duplicate venue bookings for the same date.

## 8. Batch Apex – BatchCompleteEvents

The `BatchCompleteEvents` class implements the Salesforce `Database.Batchable` interface.

It identifies events whose Event Date is before today and whose status is not already Completed.

These events are then updated to:

**Completed**

The batch process therefore provides a mechanism for automatically updating the status of past events.

## 9. Scheduled Apex – ScheduleCompleteEvents

The `ScheduleCompleteEvents` class implements the `Schedulable` interface.

Its purpose is to execute the `BatchCompleteEvents` batch job on a scheduled basis.

The scheduled class starts:

`Database.executeBatch(new BatchCompleteEvents(), 200);`

This allows the system to process past events automatically without requiring manual updates.

## 10. Backend Components

The main backend components implemented in EventForce are:

| Component | Purpose |
|---|---|
| Email Validation Rule | Validates Client email addresses |
| Client Reminder Flow | Sends reminders three days before confirmed events |
| Cancellation Approval Process | Controls event cancellation requests |
| VenueStatusHelper | Updates venue availability |
| EventTrigger13 | Invokes venue status logic |
| PreventDoubleBooking | Prevents duplicate venue bookings |
| BatchCompleteEvents | Marks past events as Completed |
| ScheduleCompleteEvents | Runs the batch process on schedule |

## 11. Phase 2 Outcome

Phase 2 provides the automation and business logic required for the EventForce Management System. Declarative Salesforce automation handles validation, reminders, and approvals, while Apex provides additional logic for venue availability, double-booking prevention, and automatic completion of past events.

## Source

Based on the EventForce Management System Salesforce implementation documentation and the retrieved Salesforce project metadata.
