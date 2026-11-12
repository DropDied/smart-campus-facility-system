# Use Case List

Actors: Student, Staff (generalised into Campus User), Campus Administrator, Maintenance Personnel

| UC ID | Use Case | Primary Actor(s) | FRs Covered | Relationship |
|---|---|---|---|---|
| UC-01 | Sign in | All actors | FR-01, FR-02, FR-03 | – |
| UC-02 | Manage profile | All actors | FR-04, FR-05 | – |
| UC-03 | Browse facilities | Campus User | FR-06, FR-07, FR-08 | – |
| UC-04 | Check availability | Campus User | FR-09 | Included by UC-05 |
| UC-05 | Submit booking request | Campus User | FR-10, FR-11 | «include» UC-04 |
| UC-06 | Manage my bookings | Campus User | FR-12, FR-13, FR-14 | – |
| UC-07 | Approve booking requests | Administrator | FR-15 | – |
| UC-08 | View all bookings | Administrator | FR-16 | Extended by UC-09 |
| UC-09 | Cancel any booking | Administrator | FR-17 | «extend» UC-08 |
| UC-10 | Manage facilities | Administrator | FR-18, FR-19, FR-20 | – |
| UC-11 | Report damage | Campus User | FR-21 | Extended by UC-12 |
| UC-12 | Attach photo | Campus User | FR-22 | «extend» UC-11 |
| UC-13 | View my report status | Campus User | FR-23 | – |
| UC-14 | Review damage reports | Administrator | FR-24 | – |
| UC-15 | Assign maintenance task | Administrator | FR-25 | – |
| UC-16 | Track maintenance progress | Administrator | FR-26 | – |
| UC-17 | View assigned tasks | Maintenance Personnel | FR-27 | – |
| UC-18 | Update task status | Maintenance Personnel | FR-28 | – |
