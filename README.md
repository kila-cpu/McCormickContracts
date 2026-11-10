# McCormick Contracts — Site & Plant platform demo

Interactive click-through demo prepared by DMC Consultancy Ltd for the ten
modules McCormick Contracts chose. One page with three portals, all running against the
same in-memory data, so a defect logged on the phone shows up as a job card in
the office straight away.

| Module | Site team app (phone) | Office backend |
| --- | --- | --- |
| **Clock in & out with geo-tagging** | Pick a job type at clock-in: Driver (picks vehicle), Operator / Labourer (site, plus machine if on one), Mechanic (nothing). Operators / labourers can only clock in inside the site boundary. The home screen, to-dos and tab bar then change to that job's tools; Health & safety is on every view and "All modules" opens the rest. One-tap clock-out with GPS. "Demo: off site" toggle shows the block | Today board with job type and machine/vehicle, map, weekly timesheets with approve, off-site clock-out flags, CSV export |
| **Employee records, onboarding & video induction** | New starter (Jamie, PIN 6666) does details → cert photos → 3 induction videos (no skipping) → quiz → sign policies | Employee records, certs & expiries, onboarding checklist, approve; add employee sends an invite and they appear on the phone; induction completion matrix |
| **Vehicle walkaround checklists** | Your past walkarounds first (grouped by day, tap to see defects, photos, signature), then ＋ for a new check. Vehicle dropdown pre-filled from clock-in. Daily check (HGV-only items for tippers/low-loaders), photos, signature. Defects raise job cards automatically | Fleet with today's check status, CVRT/tax, walkaround history and full results |
| **Plant checklists – GA2 (incl. equipment records with GA1 upload)** | Your past GA2s first, then ＋ for a new check. Machine dropdown pre-filled from clock-in. Weekly GA2 per machine, shows linked lifting gear GA1 status, "not safe" tags the machine out | Plant register, GA2 history, equipment records with GA1 upload & due dates |
| **Plant, vehicle & tyre job cards** | Raise with photo; tyre cards use an axle diagram. Fitters (Ciarán, 5555) start, add parts/hours and sign off | Board with filters, assign fitter, parts & labour costing, status |
| **Project Hub** | Site details, document categories (Drawings Register, Safety Documentation, Project Photos, Submittals, DOP Specification, Documents, Permits & Inspection Reports) – view and add files or photos, read & sign RAMS, who's on site, plant on site | Per-project overview, team & hours, plant, dayworks, loads, H&S, documents grouped by category with upload to any category |
| **Dayworks** | Labour/plant hours, materials, photos, client signs on the phone | Auto-priced from role and plant rates, approve/query, email to client, export |
| **Agg Loads** | Today's loads (customer, category, collection, delivery) with Map / New load / Tip. New load → Site or Quarry collection wizard: auto docket no., customer, vehicle, order no., collection / quarry address, tip location (each with ＋ add), vehicle type, category, type, weight, comments, driver + customer signatures, save as template. Quarry starts with a docket photo. Tip records the weighbridge ticket and tip docket photo | Waste / product / cement loads with search and filters (driver, truck, source, destination, dates), EWC, WTD, weighbridge, Article 27, rate, POD / signed / tip docket viewer, add / edit / delete, CSV export options |
| **Health & Safety Hub** | Report near miss/hazard/incident, sign toolbox talks, foreman gives a talk | Incidents with actions, toolbox talks, RAMS sign-off tracker, inspections, cert expiries |
| **Plant Locator** | Map + list, move a machine to another site | Map with pins, movement history, move |

## Demo accounts (phone)

| Name | Role | PIN |
| --- | --- | --- |
| Seán Brennan | Foreman | 1111 |
| Mick Doherty | Machine driver | 2222 |
| Tomasz Nowak | Plant operator | 3333 |
| Liam Gallagher | HGV driver | 4444 |
| Ciarán Walsh | Fitter | 5555 |
| Paddy Rooney | Groundworker | 7777 |
| Jamie Fox | New starter (onboarding) | 6666 |

## Running it

```bash
npm start          # http://localhost:3000
```

or without Node: `python3 -m http.server 3000 --directory public`

## Known limits of a wireframe

- GPS is simulated around each site; the map is a stylised drawing, not a real basemap.
- Videos are simulated players (progress only); upload records the filename.
- PDFs, emails, SMS and push reminders show a toast describing what would happen. CSV exports are real.
- Data lives in the browser tab and resets on reload (or Me → Reset demo data).
- Logo artwork supplied by McCormick Contracts (`public/logo.png`).
