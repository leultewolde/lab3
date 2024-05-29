# lab3

## Functional Requirements
- The system shall allow the Office Manager to register new Dentists.
- The system shall assign a unique ID to each Dentist.
- The system shall store Dentist’s First Name, Last Name, Contact Phone Number, Email, and Specialization.
- The system shall allow the Office Manager to enroll new Patients.
- The system shall store Patient’s First Name, Last Name, Contact Phone Number, Email, Mailing Address, and Date of Birth.
- The system shall allow Patients to request appointments via phone or an online form.
- The system shall allow the Office Manager to book appointments for Patients.
- The system shall send a confirmation email to the Patient for booked appointments.
- The system shall record the appointment details.
- The system shall allow Dentists to sign in and view their scheduled appointments.
- The system shall display Patient details and appointment details to the Dentist.
- The system shall allow Patients to sign in and view their scheduled appointments.
- The system shall display Dentist details and appointment details to the Patient.
- The system shall allow Patients to request cancellation or changes to their appointments.
- The system shall provide details of each Surgery, including name, location address, and telephone number.
- The system shall ensure that a Dentist does not have more than 5 appointments in a week.
- The system shall prevent Patients with outstanding unpaid bills from requesting new appointments.

## Domain Model
- OfficeManager
    - Attributes: managerId, firstName, lastName, contactPhone, email
    - Relationships: Manages 0..* Dentists, Manages 0..* Patients, Books 0..* Appointments
- Dentist
    - Attributes: dentistId, firstName, lastName, contactPhone, email, specialization
    - Relationships: Has 0..* Appointments, WorksAt 1..* Surgeries
- Patient
    - Attributes: patientId, firstName, lastName, contactPhone, email, mailingAddress, dateOfBirth
    - Relationships: Has 0..* Appointments, Has 0..1 Billing
- Appointment
    - Attributes: appointmentId, date, time, status
    - Relationships: ScheduledFor 1 Patient, With 1 Dentist, At 1 Surgery
- Surgery
    - Attributes: surgeryId, name, locationAddress, telephoneNumber
    - Relationships: Has 0..* Dentists, Hosts 0..* Appointments
- Billing
    - Attributes: billingId, amountDue, dueDate, status
    - Relationships: For 1 Patient

### Class Diagram
![alt text](<UML class.png>)