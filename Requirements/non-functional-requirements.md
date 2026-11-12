# Non-Functional Requirements

Priority uses MoSCoW: Must / Should / Could

| ID | Category | Requirement | How it can be verified | Priority |
|---|---|---|---|---|
| NFR-01 | Performance | Each page shall load within 3 seconds under normal network conditions. | Time page loads using browser developer tools. | Must |
| NFR-02 | Performance | The system shall display facility availability within 2 seconds of the user selecting a date and time. | Time the availability check across several facilities. | Should |
| NFR-03 | Security | User passwords shall be stored in hashed form, never as plain text. | Inspect the stored user records in the database. | Must |
| NFR-04 | Security | Campus users shall only be able to view their own bookings and reports. | Sign in as one user and attempt to access another user's records. | Must |
| NFR-05 | Security | A user session shall expire after 30 minutes of inactivity. | Leave a session idle for 30 minutes, then attempt an action. | Should |
| NFR-06 | Usability | A first-time user shall be able to complete a facility booking within 3 minutes without instructions. | Time test users booking a facility for the first time. | Should |
| NFR-07 | Usability | The system shall display a clear error message whenever user input is invalid or an action fails. | Submit empty or invalid forms and check the messages shown. | Must |
| NFR-08 | Compatibility | The system shall function correctly on the latest versions of Chrome, Edge and Firefox. | Run the main test cases in each browser. | Must |
| NFR-09 | Compatibility | The interface shall be usable on mobile screens 360 px wide and above. | View pages using the browser's mobile device emulator. | Should |
| NFR-10 | Reliability | Bookings and reports shall be stored permanently, so no data is lost when the user refreshes or closes the browser. | Create a booking, close the browser, sign back in and confirm it remains. | Must |
