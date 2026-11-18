# Functional Requirements

Actors: Student, Staff (both "Campus User"), Campus Administrator, Maintenance Personnel
Priority uses MoSCoW: Must / Should / Could / Won't

## Account
| ID | Requirement | Actor | Priority |
|---|---|---|---|
| FR-01 | The system shall allow users to sign in using their university ID and password. | All | Must |
| FR-02 | The system shall allow users to sign out. | All | Must |
| FR-03 | The system shall restrict access to functions based on the user's role. | All | Must |
| FR-04 | The system shall allow users to view their profile. | All | Should |
| FR-05 | The system shall allow users to edit their personal information. | All | Could |

## Facility Booking
| ID | Requirement | Actor | Priority |
|---|---|---|---|
| FR-06 | The system shall allow campus users to browse a list of campus facilities. | Campus User | Must |
| FR-07 | The system shall allow campus users to filter facilities by type and location. | Campus User | Should |
| FR-08 | The system shall display facility details, including location, capacity and available equipment. | Campus User | Should |
| FR-09 | The system shall allow campus users to check a facility's availability for a selected date and time. | Campus User | Must |
| FR-10 | The system shall allow campus users to submit a booking request for an available time slot. | Campus User | Must |
| FR-11 | The system shall prevent bookings for time slots that are already booked or for facilities marked unavailable. | Campus User | Must |
| FR-12 | The system shall allow campus users to view their own bookings and each booking's status (Pending, Confirmed, Rejected, Cancelled). | Campus User | Must |
| FR-13 | The system shall allow campus users to edit their own booking before the booking date. | Campus User | Should |
| FR-14 | The system shall allow campus users to cancel their own booking. | Campus User | Must |
| FR-15 | The system shall allow administrators to approve or reject booking requests. | Administrator | Must |
| FR-16 | The system shall allow administrators to view all bookings. | Administrator | Must |
| FR-17 | The system shall allow administrators to cancel any booking. | Administrator | Should |
| FR-18 | The system shall allow administrators to add a new facility. | Administrator | Must |
| FR-19 | The system shall allow administrators to edit facility details. | Administrator | Must |
| FR-20 | The system shall allow administrators to mark a facility as unavailable or available. | Administrator | Should |

## Maintenance Reporting & Tracking
| ID | Requirement | Actor | Priority |
|---|---|---|---|
| FR-21 | The system shall allow campus users to submit a damage report by selecting a facility and describing the problem. | Campus User | Must |
| FR-22 | The system shall allow campus users to attach a photo to a damage report. | Campus User | Could |
| FR-23 | The system shall allow campus users to view the status of reports they submitted. | Campus User | Must |
| FR-24 | The system shall allow administrators to review submitted reports and accept or reject them. | Administrator | Must |
| FR-25 | The system shall allow administrators to assign an accepted report to maintenance personnel as a task. | Administrator | Must |
| FR-26 | The system shall allow administrators to track the progress of all maintenance tasks. | Administrator | Must |
| FR-27 | The system shall allow maintenance personnel to view tasks assigned to them, including the report details. | Maintenance Personnel | Must |
| FR-28 | The system shall allow maintenance personnel to update a task's status (In Progress, Resolved). | Maintenance Personnel | Must |
