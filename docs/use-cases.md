# Use Cases

## UC-01: Book first appointment

**Actor:** Prospective Patient

**Goal:** Book a first appointment through WhatsApp without prior registration.

### Preconditions

1. The Prospective Patient has a WhatsApp account.
2. The clinic and the dentist are registered in the system.
3. The dentist has working hours configured.
4. The clinic's WhatsApp number is connected to the system.

### Main flow

1. The Prospective Patient sends a message to the clinic on WhatsApp.
2. The system sends the privacy notice.
3. The Prospective Patient accepts the notice, and the system records the consent (date and time).
4. The system asks for the patient's name. The phone number comes from WhatsApp.
5. The system shows the available dentists and time slots.
6. The Prospective Patient chooses a dentist and a time slot.
7. The system shows a summary (dentist, date, time) and asks for confirmation.
8. The Prospective Patient confirms.
9. The system saves the appointment.
10. The system sends the confirmation to the Prospective Patient.
11. The system notifies the dentist about the new appointment.
12. The system sends a link through WhatsApp to complete the patient data and to change or cancel the appointment.

### Failure cases

- **3a:** The patient does not accept the notice. The system ends the conversation and does not collect the name.
- **5a:** No time slots are available. The system offers other dates and times until the patient chooses one or gives up (see 4-8a).
- **4-8a:** The patient stops responding. After a period of inactivity, the system warns that the conversation will expire. If there is still no reply, the system expires the conversation, marks the contact as "not completed", and notifies the dentist for follow-up.
- **9a:** The chosen time slot was taken by someone else. The system informs the patient and goes back to step 5 with updated time slots.
- **9b:** The system cannot save the appointment. It does not send the confirmation. It tells the patient that the booking was not possible and that the clinic will get in touch, and it notifies the clinic of the failed attempt.
- **11a, 12a:** Notifying the dentist or sending the link fails. The appointment stays valid. The system retries and logs the failure.
- **Any step:** The language assistant is unavailable. The system falls back to a fixed menu or hands the conversation over to a human (see ADR-005).

### Postconditions

- The appointment is saved.
- The consent is recorded.
- The dentist is notified.
- The patient has received the confirmation and the link.

### Open questions

- Inactivity timeout: a business rule, configurable per clinic. Three minutes may be too short for WhatsApp.
- Does the system hold the chosen time slot while the patient decides, or only check it at step 9?
- How long are "not completed" contacts kept?
- The privacy notice (step 2) must state that the clinic may contact the patient later.
- Validity of the link: single use or valid until the appointment.
- Success metric for the MVP: conversion rate from contact to appointment.

### Notes for the domain model

- Each conversation has a unique ID, scoped by clinic. Logs use this ID instead of the phone number.
