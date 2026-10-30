# Vision Document

## Problem

Small dental practices schedule appointments by phone and manual
messaging. Requests outside business hours are missed, double
bookings happen, and no-shows are common.

## Goal

Provide a WhatsApp assistant, available 24/7, that lets people book,
reschedule, cancel, and confirm appointments while respecting the
dentist's working days and hours.

## Users (actors)

- Patient: manages their own appointments.
- Prospective Patient: first contact; books with name and phone, then completes registration through a secure link.

- Dentist: sets availability and approves proof of payment for
  urgent appointments.
- Practice Owner: registers the practice and configures its rules.
- System Administrator: operates and maintains the system.
- External systems: WhatsApp, LLM provider.

## Key capabilities (MVP)

- Book, reschedule, cancel, and confirm an appointment.
- Booking first, then registration completed through a secure link.
- Urgent appointments with upfront payment proof upload.
- Conflict-free scheduling based on dentist availability.

## Out of scope (for now)

- Online payment processing (only proof upload).
- Support for non-dental businesses.
- Native mobile app.

## Constraints and assumptions

- The urgent fee is configurable per practice and optional.
- The data model is multi-tenant (business_id) from the start.
- The product may have real commercial use, not only portfolio use.
- The system is designed to comply with LGPD (Brazil's General Data
  Protection Law).
- Patient data is sensitive: privacy and security are requirements
  from the start.
- Registration is progressive: a booking requires only name and phone;
  the remaining data is collected afterwards through a secure link.

## Open questions

- How is the dentist notified and how does the dentist approve
  a payment proof?
- Which WhatsApp connection will be used (see ADR-002)?
- Which extra verification, if any, is needed to cancel or reschedule?
