# Use Case Descriptions

Actors: User (parent of all actors), Campus User (parent of Student and Staff), Campus Administrator, Maintenance Personnel

Booking statuses: Pending, Confirmed, Rejected, Cancelled
Report statuses: Pending, Accepted, Rejected, Assigned, In Progress, Resolved

---

## UC-01 Sign in

| Field | Description |
|---|---|
| Actor(s) | User (all actors) |
| Description | A user signs in with their university ID and password to access the functions available to their role. |
| Preconditions | The user has a registered account. |
| Main flow | 1. User opens the sign-in page.<br>2. User enters their university ID and password.<br>3. System verifies the credentials.<br>4. System identifies the user's role.<br>5. System displays the home page with the functions for that role. |
| Alternative flows | 3a. Credentials are invalid: system displays an error message and the user may try again.<br>5a. User selects Sign out at any time: system ends the session and returns to the sign-in page. |
| Postconditions | The user is signed in and can only access functions permitted for their role. |
| Related requirements | FR-01, FR-02, FR-03, NFR-03, NFR-05 |

## UC-02 Manage profile

| Field | Description |
|---|---|
| Actor(s) | User (all actors) |
| Description | A user views their profile and edits their personal information. |
| Preconditions | The user is signed in. |
| Main flow | 1. User selects My Profile.<br>2. System displays the user's profile details.<br>3. User selects Edit.<br>4. User updates their personal information and selects Save.<br>5. System validates and saves the changes.<br>6. System displays a confirmation message. |
| Alternative flows | 3a. User only wishes to view the profile: the use case ends after step 2.<br>5a. Input is invalid or a required field is empty: system displays an error message and the user corrects it. |
| Postconditions | The user's updated information is saved. |
| Related requirements | FR-04, FR-05, NFR-07 |

## UC-03 Browse facilities

| Field | Description |
|---|---|
| Actor(s) | Campus User (Student, Staff) |
| Description | A campus user browses the list of campus facilities and views a facility's details. |
| Preconditions | The user is signed in. |
| Main flow | 1. User selects Facilities.<br>2. System displays the list of campus facilities.<br>3. User filters the list by facility type and/or location.<br>4. System displays the matching facilities.<br>5. User selects a facility.<br>6. System displays the facility's location, capacity and available equipment. |
| Alternative flows | 3a. User does not filter: the full list remains displayed.<br>4a. No facilities match the filter: system displays a "no facilities found" message. |
| Postconditions | The user has viewed the facility information. |
| Related requirements | FR-06, FR-07, FR-08 |

## UC-04 Check availability

| Field | Description |
|---|---|
| Actor(s) | Campus User (Student, Staff) |
| Description | A campus user checks whether a facility is available for a selected date and time. Also included by UC-05. |
| Preconditions | The user is signed in and has selected a facility. |
| Main flow | 1. User selects a date and time.<br>2. System checks existing bookings and the facility's availability status.<br>3. System displays the available and unavailable time slots. |
| Alternative flows | 2a. The facility is marked unavailable: system displays a message that the facility cannot currently be booked. |
| Postconditions | The user knows which time slots are available. |
| Related requirements | FR-09, FR-11, NFR-02 |

## UC-05 Submit booking request

| Field | Description |
|---|---|
| Actor(s) | Campus User (Student, Staff) |
| Description | A campus user requests to book an available time slot for a facility. |
| Preconditions | The user is signed in and has selected a facility. |
| Main flow | 1. User selects Book.<br>2. System performs Check availability (UC-04).<br>3. User selects an available time slot.<br>4. User confirms the booking request.<br>5. System saves the booking with status Pending.<br>6. System displays a confirmation that the request has been submitted. |
| Alternative flows | 3a. The selected slot was booked by another user in the meantime: system displays an error and returns to step 2. |
| Postconditions | A booking request with status Pending is stored and awaits administrator approval. |
| Related requirements | FR-10, FR-11, NFR-06, NFR-10 |

## UC-06 Manage my bookings

| Field | Description |
|---|---|
| Actor(s) | Campus User (Student, Staff) |
| Description | A campus user views their own bookings and their status, and edits or cancels a booking. |
| Preconditions | The user is signed in. |
| Main flow | 1. User selects My Bookings.<br>2. System displays the user's bookings with their status (Pending, Confirmed, Rejected, Cancelled).<br>3. User selects a booking and chooses Edit.<br>4. User changes the date or time slot.<br>5. System checks the new slot's availability and saves the change.<br>6. System sets the booking status to Pending for re-approval and displays a confirmation. |
| Alternative flows | 3a. User chooses Cancel: system asks for confirmation, sets the status to Cancelled and frees the time slot.<br>3b. The booking date has passed: system does not allow editing.<br>5a. The new slot is unavailable: system displays an error and the original booking remains unchanged. |
| Postconditions | The booking is updated or cancelled. |
| Related requirements | FR-12, FR-13, FR-14, NFR-04 |

## UC-07 Approve booking requests

| Field | Description |
|---|---|
| Actor(s) | Campus Administrator |
| Description | An administrator approves or rejects pending booking requests. |
| Preconditions | The administrator is signed in and at least one booking is Pending. |
| Main flow | 1. Administrator selects Booking Requests.<br>2. System displays all bookings with status Pending.<br>3. Administrator selects a request and reviews its details.<br>4. Administrator selects Approve.<br>5. System sets the status to Confirmed. |
| Alternative flows | 4a. Administrator selects Reject: system sets the status to Rejected and frees the time slot. |
| Postconditions | The booking status is updated and visible to the requesting user. |
| Related requirements | FR-15 |

## UC-08 View all bookings

| Field | Description |
|---|---|
| Actor(s) | Campus Administrator |
| Description | An administrator views every booking in the system. |
| Preconditions | The administrator is signed in. |
| Main flow | 1. Administrator selects All Bookings.<br>2. System displays all bookings with facility, user, date, time and status.<br>3. Administrator selects a booking to view its details. |
| Alternative flows | 2a. No bookings exist: system displays a "no bookings" message. |
| Extension points | Cancel any booking (UC-09) |
| Postconditions | None. |
| Related requirements | FR-16 |

## UC-09 Cancel any booking

| Field | Description |
|---|---|
| Actor(s) | Campus Administrator |
| Description | Extends UC-08. While viewing a booking, an administrator cancels it, for example when a facility is closed. |
| Preconditions | The administrator is viewing an Confirmed or Pending booking in UC-08. |
| Main flow | 1. Administrator selects Cancel Booking.<br>2. System asks for confirmation.<br>3. Administrator confirms.<br>4. System sets the booking status to Cancelled and frees the time slot. |
| Alternative flows | 3a. Administrator does not confirm: the booking remains unchanged. |
| Postconditions | The booking is cancelled and the user sees the Cancelled status in My Bookings. |
| Related requirements | FR-17 |

## UC-10 Manage facilities

| Field | Description |
|---|---|
| Actor(s) | Campus Administrator |
| Description | An administrator adds new facilities, edits facility details and marks facilities as available or unavailable. |
| Preconditions | The administrator is signed in. |
| Main flow | 1. Administrator selects Manage Facilities.<br>2. System displays the list of facilities.<br>3. Administrator selects Add Facility.<br>4. Administrator enters the name, type, location, capacity and equipment.<br>5. System validates and saves the new facility. |
| Alternative flows | 3a. Administrator selects an existing facility and chooses Edit: the administrator updates its details and the system saves them.<br>3b. Administrator marks a facility as unavailable (e.g. under repair) or available again: the system updates its status and blocks or allows new bookings.<br>5a. A required field is missing: system displays an error message. |
| Postconditions | The facility list is updated. |
| Related requirements | FR-18, FR-19, FR-20, NFR-07 |

## UC-11 Report damage

| Field | Description |
|---|---|
| Actor(s) | Campus User (Student, Staff) |
| Description | A campus user reports damaged facilities or equipment. |
| Preconditions | The user is signed in. |
| Main flow | 1. User selects Report Damage.<br>2. User selects the affected facility.<br>3. User describes the problem.<br>4. User submits the report.<br>5. System saves the report with status Pending.<br>6. System displays a confirmation. |
| Alternative flows | 4a. The description is empty: system displays an error message. |
| Extension points | Attach photo (UC-12), after step 3 |
| Postconditions | A report with status Pending is stored for administrator review. |
| Related requirements | FR-21, NFR-10 |

## UC-12 Attach photo

| Field | Description |
|---|---|
| Actor(s) | Campus User (Student, Staff) |
| Description | Extends UC-11. The user optionally attaches a photo of the damage to the report. |
| Preconditions | The user is filling in a damage report in UC-11. |
| Main flow | 1. User selects Attach Photo.<br>2. User chooses an image file.<br>3. System uploads the image and displays a preview.<br>4. The user continues with UC-11. |
| Alternative flows | 3a. The file is not a supported image type: system displays an error message. |
| Postconditions | The photo is attached to the report. |
| Related requirements | FR-22 |

## UC-13 View my report status

| Field | Description |
|---|---|
| Actor(s) | Campus User (Student, Staff) |
| Description | A campus user tracks the progress of damage reports they submitted. |
| Preconditions | The user is signed in. |
| Main flow | 1. User selects My Reports.<br>2. System displays the reports submitted by this user, with their status (Pending, Accepted, Rejected, Assigned, In Progress, Resolved).<br>3. User selects a report to view its details. |
| Alternative flows | 2a. The user has not submitted any reports: system displays a "no reports" message. |
| Postconditions | None. |
| Related requirements | FR-23, NFR-04 |

## UC-14 Review damage reports

| Field | Description |
|---|---|
| Actor(s) | Campus Administrator |
| Description | An administrator reviews new damage reports and accepts or rejects them. |
| Preconditions | The administrator is signed in and at least one report is Pending. |
| Main flow | 1. Administrator selects Damage Reports.<br>2. System displays reports with status Pending.<br>3. Administrator selects a report and reviews its details.<br>4. Administrator selects Accept.<br>5. System sets the report status to Accepted. |
| Alternative flows | 4a. The report is invalid or a duplicate: administrator selects Reject and the system sets the status to Rejected. |
| Postconditions | The report is Accepted and ready to assign, or Rejected. |
| Related requirements | FR-24 |

## UC-15 Assign maintenance task

| Field | Description |
|---|---|
| Actor(s) | Campus Administrator |
| Description | An administrator assigns an accepted report to maintenance personnel as a task. |
| Preconditions | The administrator is signed in and at least one report is Accepted. |
| Main flow | 1. Administrator selects an Accepted report.<br>2. Administrator selects Assign.<br>3. System displays the list of maintenance personnel.<br>4. Administrator selects a maintenance staff member.<br>5. System creates a maintenance task and sets the report status to Assigned. |
| Alternative flows | 3a. No maintenance personnel are registered: system displays an error message. |
| Postconditions | The task appears in the assigned staff member's task list. |
| Related requirements | FR-25 |

## UC-16 Track maintenance progress

| Field | Description |
|---|---|
| Actor(s) | Campus Administrator |
| Description | An administrator monitors the progress of all maintenance tasks. |
| Preconditions | The administrator is signed in. |
| Main flow | 1. Administrator selects Maintenance Tasks.<br>2. System displays all tasks with the facility, assigned staff and status.<br>3. Administrator filters tasks by status.<br>4. Administrator selects a task to view its details. |
| Alternative flows | 2a. No tasks exist: system displays a "no tasks" message. |
| Postconditions | None. |
| Related requirements | FR-26 |

## UC-17 View assigned tasks

| Field | Description |
|---|---|
| Actor(s) | Maintenance Personnel |
| Description | A maintenance staff member views the tasks assigned to them. |
| Preconditions | The maintenance staff member is signed in. |
| Main flow | 1. Staff member selects My Tasks.<br>2. System displays the tasks assigned to them, with facility, problem description, photo (if any) and status.<br>3. Staff member selects a task to view its full details. |
| Alternative flows | 2a. No tasks are assigned: system displays a "no tasks" message. |
| Postconditions | None. |
| Related requirements | FR-27 |

## UC-18 Update task status

| Field | Description |
|---|---|
| Actor(s) | Maintenance Personnel |
| Description | A maintenance staff member updates the progress of an assigned task. |
| Preconditions | The staff member is viewing one of their assigned tasks. |
| Main flow | 1. Staff member selects Update Status.<br>2. Staff member selects In Progress or Resolved.<br>3. System saves the new status.<br>4. System updates the related report's status so the reporting user and administrator can see it. |
| Alternative flows | 2a. The task is already Resolved: system does not allow further status changes. |
| Postconditions | The task and report statuses are updated. |
| Related requirements | FR-28 |
