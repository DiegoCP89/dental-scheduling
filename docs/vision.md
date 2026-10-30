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
- Prospective Patient: first contact; registers through a web form.
- Dentist: sets availability and approves proof of payment for
  urgent appointments.
- Practice Owner: registers the practice and configures its rules.
- System Administrator: operates and maintains the system.
- External systems: WhatsApp, LLM provider.

## Key capabilities (MVP)

- Book, reschedule, cancel, and confirm an appointment.
- Self-registration form on first contact.
- Urgent appointments with upfront payment proof upload.
- Conflict-free scheduling based on dentist availability.

## Out of scope (for now)

- Online payment processing (only proof upload).
- Support for non-dental businesses.
- Native mobile app.

## Constraints and assumptions

- The urgent fee is configurable per practice and optional.
- The data model is multi-tenant (business_id) from the start.
- Personal data is handled under Brazilian law (LGPD).

## Open questions

- How is the dentist notified and how does the dentist approve
  a payment proof?
- Which WhatsApp connection will be used (see ADR-002)?
