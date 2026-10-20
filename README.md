# dental-scheduling

> WhatsApp assistant that lets dental patients book, reschedule,
> cancel, and confirm appointments, available 24/7.

![License: MIT](https://img.shields.io/badge/license-MIT-green)
![Status: Requirements](https://img.shields.io/badge/status-requirements%20phase-yellow)

## The Problem

Small dental clinics handle scheduling by phone and manual messaging,
which leads to missed requests outside business hours, double bookings,
and no-shows. Reception staff spend time on repetitive tasks instead of
patient care.

## The Solution

Patients talk to an assistant on WhatsApp, available around the clock:

- Book, reschedule, or cancel an appointment
- Confirm an existing appointment
- Request an urgent appointment (requires upfront payment proof)
- Self-register through a short web form on first contact

The assistant respects each dentist's working days and hours, so
conflicting bookings cannot happen.

## Future Scope

Designed so it can later be adapted to other appointment-based
businesses, such as law firms and medical offices.

## Project Status

**Current phase:** Requirements and analysis (no code yet)

- [x] Project scope and repository setup
- [ ] Vision document and use cases
- [ ] Business rules
- [ ] Data model (ER diagram)
- [ ] Patient registration API
- [ ] Appointment scheduling logic
- [ ] WhatsApp integration
- [ ] Urgent appointments and payment proof upload
- [ ] Conversational layer (LLM)
- [ ] Deployment

## Tech Stack

| Layer            | Tool                            |
| ---------------- | ------------------------------- |
| API              | FastAPI (Python)                |
| Database         | PostgreSQL, SQLAlchemy, Alembic |
| WhatsApp gateway | Evolution API                   |
| Automation       | n8n (notifications)             |
| CI/CD            | GitHub Actions                  |

All components are open source.

## Documentation

- [Architecture Decision Records](docs/adr/)
- [Glossary](docs/glossary.md)

## Getting Started

Coming soon.

## Contributing

This is a learning project built in public. Commits follow
[Conventional Commits](https://www.conventionalcommits.org/);
work is organized with GitHub Issues and Projects.

## License

[MIT](LICENSE)
