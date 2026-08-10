# hgse-cal

Helsinki GSE seminars and doctoral defences as subscribable calendar feeds.

Helsinki GSE's own per-series Google Calendars stopped being updated in
December 2024, and `helsinkigse.fi/seminar-calendar` returns 404. The events
page itself is current, so this repository republishes it in a form calendar
apps can subscribe to.

All feeds live under this base URL:

```
https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/
```

**If your calendar app refuses a feed**, try the same file through jsDelivr:

```
https://cdn.jsdelivr.net/gh/Lumikko-econ/hgse-cal@main/
```

Identical content, but served as `text/calendar` rather than GitHub's
`text/plain`, which some clients insist on. The trade-off is caching — jsDelivr
holds a copy for up to 12 hours, so changes show up later than on the raw URL.

## Pick one scheme

**Pick a single scheme and subscribe only within it.** Mixing them — say the
combined feed plus a per-series one — makes events appear twice.

### A. Everything in one calendar

`helsinki-gse.ics` — all 43 events.

### B. Split by interest (two calendars, two colours)

Calendar apps colour by *calendar*, not by event, so this is how you make some
series stand out while keeping the rest visible.

| Feed | Contains |
|---|---|
| `helsinki-gse-core.ics` | Industrial Organization, Colloquium, Microeconomics, Trade/Regional & Urban, doctoral defences. Reminder at 08:00 on the day. |
| `helsinki-gse-other.ics` | Everything else. No reminders. |

Together they are the complete schedule.

### C. Per series — pick your own fields

One feed per series, so you can take only what you care about. Subscribe to as
many as you like; they don't overlap.

| Feed | Events |
|---|---|
| `helsinki-gse-industrial-organization.ics` | 3 |
| `helsinki-gse-colloquium.ics` | 5 |
| `helsinki-gse-microeconomics.ics` | 4 |
| `helsinki-gse-trade-regional-and-urban-economics.ics` | 5 |
| `helsinki-gse-labor-public-economics.ics` | 6 |
| `helsinki-gse-environmental-economics.ics` | 5 |
| `helsinki-gse-macroeconomics.ics` | 3 |
| `helsinki-gse-economics-of-education-educa.ics` | 3 |
| `helsinki-gse-behavioral-economics.ics` | 2 |
| `helsinki-gse-development-economics.ics` | 1 |
| `helsinki-gse-econometrics.ics` | 1 |
| `helsinki-gse-doctoral-defences.ics` | 2 |
| `helsinki-gse-seminar.ics` | 3 (events HGSE left unfiled) |

Counts are for autumn 2026 and change as the term fills in. A new series on the
HGSE site gets its own feed automatically.

## Subscribing

### Outlook (including Outlook for Mac)

**Subscribe on the web, not in the desktop app.** Outlook for Mac does not
reliably support adding an internet calendar by URL — most versions have no
menu path for it, and its parser rejects many valid feeds.

1. Go to <https://outlook.office.com/calendar/>
2. **Add calendar** → **Subscribe from web**
3. Paste the feed URL, name it, pick a colour, **Import**
4. It appears in Outlook for Mac and on your phone automatically, through your
   account

Refresh cadence is Microsoft's to decide and can lag by several hours.

### Apple Calendar

File → New Calendar Subscription, paste the URL, set *Auto-refresh* to Every
day. Right-click the calendar → Get Info to change its colour. Each feed ships
a suggested colour that Apple picks up on first subscribe.

### Don't import

Importing takes a one-time snapshot, and re-importing later duplicates every
event. Subscribing keeps the calendar in sync: events carry stable UIDs, so a
changed time, venue or speaker updates in place.

## What's in an event

Series, speaker and affiliation, paper title where announced, host, venue, a
link back to the event page, and a Google Scholar search — for the paper once
its title is announced, otherwise for the speaker's own work.

**Check the venue.** Seminars alternate between Economicum (Arkadiankatu 7,
Helsinki) and the Aalto campuses in Otaniemi/Espoo, and the difference is a
half-hour trip.

Times and venues come from each event's detail page. Where a time has not been
published yet the entry is all-day rather than being given an invented one, and
its reminder fires at 08:00 that morning. HGSE does not publish abstracts, so
there are none to include.

## How it updates

A cron job regenerates the feeds from <https://www.helsinkigse.fi/events> and
pushes here only when something actually changed — so the commit history is a
log of schedule changes rather than of the job running. If the page layout ever
changes, the scraper parses zero events and stops without overwriting anything.
