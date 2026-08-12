<!-- foundation:identity -->
# Wildfern Salon

Appointment booking for a hair salon: customers pick a service and staff member, see real availability from staff schedules, book with contact details, and cancel via a private link. Admins manage ser

- Site: https://wildfern-salon.api.holode.xyz
- Support: support@wildfern-salon.api.holode.xyz
<!-- /foundation:identity -->

## What this is

Appointment booking for a hair salon: customers pick a service and staff member, see real availability from staff schedules, book with contact details, and cancel via a private link. Admins manage services, staff, weekly availability, and appointments.

## Who it is for

- Guest customer (browses services/staff, books, cancels via token link)
- Salon admin (manages services, staff, weekly availability, appointments)

## Main features

- **Book an appointment** — Guest picks a service, then a staff member, picks an available time slot generated from that staff member's weekly schedule minus overlaps and past times, enters contact details, and gets a confirmation with a private cancel link
- **Cancel an appointment** — Guest opens their private cancel link and confirms; slot becomes bookable again
- **Manage services** — Admin creates/edits/deactivates services with name, duration, price
- **Manage staff and availability** — Admin adds staff members and their recurring weekly availability windows
- **Manage appointments** — Admin views appointments by status/date and cancels on behalf of customers

## Core entities

- Service
- StaffMember
- ScheduleEntry
- Appointment

## Run locally

```bash
bundle install
bin/rails db:prepare
bin/dev
```

Requires Ruby, PostgreSQL, and the usual Rails toolchain. See `bin/setup` if present.

## Demo

4 services (Precision Cut 45min $65, Balayage 150min $220, Signature Blowout 30min $45, Deep Conditioning Ritual 30min $40); 3 staff members (Mara, June, Ellis) each with a full weekly availability schedule; one upcoming booked appointment and one cancelled appointment so the admin view demonstrates both states

## Deploy notes

Production `config.hosts` is derived from `domain` in `config/foundation.yml`. Keep that value aligned with the real host or every request will 403.
