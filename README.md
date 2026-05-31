# Mint & Molar Dental Care

Website for Mint & Molar Dental Care, a family dentistry practice in Frederick, MD. Built with Jekyll and managed via PagesCMS.

## Tech Stack

- **Jekyll** — static site generator
- **PagesCMS** — content management via `.pages.yml`
- **Scaffold** — internal CSS grid/layout system
- **GitHub** — source and deployment

## Local Development

```bash
jekyll serve
```

The site will be available at `http://localhost:4000`.

## Content Management

Content is managed via [PagesCMS](https://pagescms.org). The following are editable through the CMS:

| Section | File(s) | Notes |
|---|---|---|
| Posts | `_posts/` | Blog/announcement posts |
| Services | `_services/` | Service cards shown on home and services page |
| Team | `_team/` | Doctor and staff profiles |
| Contact | `_data/contact.yml` | Phone, email, address |
| Hours | `_data/hours.yml` | Per-day hours — do not add or remove entries |
| Holiday Closures | `_data/holidays.yml` | Date + banner message |
| Legal | `legal/` | Privacy policy, terms, etc. |

## Data Structure

### Hours (`_data/hours.yml`)
One entry per day of the week. Jekyll groups consecutive days with the same time into ranges for display. **Do not add or remove entries** — always 7 entries, Mon–Sun.

```yaml
- day: "Monday"
  abbr: "Mon"
  time: "8am - 5pm"
```

### Holiday Closures (`_data/holidays.yml`)
When a date matches today, a banner appears site-wide and the hours card shows "Closed Today". Matching runs client-side so no rebuild is needed.

```yaml
- holiday: "Thanksgiving"
  date: "2025-11-27"
  message: "We're closed for Thanksgiving and will reopen Monday, December 1st."
```

### Team (`_team/`)
- `role: doctor` — renders as a wide two-column card with education table
- `role: staff` — renders as a grid card

### Services (`_services/`)
Ordered by the `order` field. Used on both the home page and the services page.

## Pending

- Favicon + Apple touch icon (assets needed)
- `og:image` social share image (asset needed)
- Geo coordinates for JSON-LD (lat/long for the practice location)
- See [open issues](https://github.com/naher94/mintmolar.com/issues) for full list
