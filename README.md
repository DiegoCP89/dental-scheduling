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
- Start with just a name in the chat and complete the registration later through a secure link

The assistant respects each dentist's working days and hours and is
designed to prevent conflicting bookings.

## Future Scope

Designed so it can later be adapted to other appointment-based
businesses, such as law firms and medical offices.

## Project Status

**Current phase:** Requirements and analysis (no code yet)

- [x] Project scope and repository setup
- [x] Vision document
- [ ] Use cases (UC-01 done)
- [ ] Business rules
- [ ] Data model (ER diagram)
- [ ] Patient registration API
- [ ] Appointment scheduling logic
- [ ] WhatsApp integration
- [ ] Urgent appointments and payment proof upload
- [ ] Conversational layer (LLM)
- [ ] Deployment

## Planned Stack

| Layer            | Tool                            |
| ---------------- | ------------------------------- |
| API              | FastAPI (Python)                |
| Database         | PostgreSQL, SQLAlchemy, Alembic |
| WhatsApp gateway | Evolution API                   |
| Conversation     | LLM with function calling       |
| Notifications    | Email (dentist alerts)          |
| CI/CD            | GitHub Actions                  |

## Documentation

- [Architecture Decision Records](docs/adr/)
- [Glossary](docs/glossary.md)

## Getting Started

Coming soon.

## Contributing

This is a learning project built in public. Commits follow
[Conventional Commits](https://www.conventionalcommits.org/);
work is organized with GitHub Issues and Projects.

This repository contains documentation only, so code contributions do not apply.

## License

The documentation in this repository is licensed under the [MIT License](LICENSE).
The application code will live in a separate private repository.

## Author

Diego Cruz Pereira, ADS student at Fatec Franca, Brazil.
[LinkedIn](https://www.linkedin.com/in/diegocp89) · [GitHub](https://github.com/DiegoCP89)
