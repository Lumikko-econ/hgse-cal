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

<!-- feeds:start -->

### A. Everything in one calendar

| Calendar | Subscription URL | Events |
|---|---|---:|
| Everything | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse.ics` | 43 |

### B. Split by interest (two calendars, two colours)

Calendar apps colour by *calendar*, not by event, so this is how you
make some series stand out while keeping the rest visible.

**Core** holds:

- Colloquium
- Industrial Organization
- Microeconomics
- Trade, Regional and Urban Economics
- Doctoral defences

**Other** holds everything else. Together they are the complete
schedule.

| Calendar | Subscription URL | Events |
|---|---|---:|
| Core | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-core.ics` | 19 |
| Other | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-other.ics` | 24 |

The core feed is the only one carrying reminders (09:00 on the day).

### C. Per series — pick your own fields

Subscribe to as many as you like; they do not overlap, and none of
them set reminders.

| Calendar | Subscription URL | Events |
|---|---|---:|
| Labor & Public Economics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-labor-public-economics.ics` | 6 |
| Colloquium | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-colloquium.ics` | 5 |
| Environmental Economics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-environmental-economics.ics` | 5 |
| Trade, Regional and Urban Economics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-trade-regional-and-urban-economics.ics` | 5 |
| Microeconomics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-microeconomics.ics` | 4 |
| Economics of Education (Educa) | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-economics-of-education-educa.ics` | 3 |
| Industrial Organization | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-industrial-organization.ics` | 3 |
| Macroeconomics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-macroeconomics.ics` | 3 |
| Seminar | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-seminar.ics` | 3 |
| Behavioral Economics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-behavioral-economics.ics` | 2 |
| Doctoral Defences | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-doctoral-defences.ics` | 2 |
| Development Economics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-development-economics.ics` | 1 |
| Econometrics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-econometrics.ics` | 1 |

<!-- feeds:end -->

## Subscribing

> ⚠️ **Use the `raw.githubusercontent.com` URL, not the `github.com/.../blob/`
> one.** The blob URL returns a normal HTTP 200 — but it serves a web page, not
> a calendar, so Outlook accepts it and then silently finds no events. This is
> the single most common way this goes wrong. Copy the URLs from the tables
> above rather than from GitHub's file view.

### Outlook on Windows — classic

The Windows desktop app supports this properly, unlike the Mac one.

1. Go to **Calendar** (not Mail)
2. **Home** tab → **Add Calendar** → **From Internet…**
   *(older builds: **Add/Open Calendar** → **From Internet…**)*
3. Paste the feed URL → **OK** → **Yes** when asked whether to subscribe and
   receive updates

Repeat for each feed. Refreshes on the Send/Receive schedule; **F9** forces one.
Microsoft notes the first sync can take more than 24 hours.

**To overlay them into one grid:** each calendar opens as its own side-by-side
tab — click the small **←** arrow on a calendar's tab to merge it into the one
on its left, or use **View → Overlay**. Click the arrow again to separate them.

### Outlook on Windows — new Outlook

The new app is the web version in a desktop shell, so it follows the web steps
below. Tell them apart by the **Try the new Outlook** toggle in the top-right —
if it's there and switched on, you're in the new one.

### Outlook on the web (and new Outlook, any platform)

1. <https://outlook.office.com/calendar/>
2. **Add calendar** in the left pane → **Subscribe from web**
3. Paste the feed URL, name it, pick a colour → **Import**

Updates roughly every few hours; the first one can take longer. Calendars are
**merged into one view by default** here — if yours are side by side, switch off
the **Split view** toggle in the view selector at the top.

### Outlook for Mac

**Subscribe on the web, not in the desktop app.** Outlook for Mac has no
reliable menu path for adding an internet calendar by URL. Use the web steps
above — the subscription syncs down to the Mac app and your phone through your
account automatically.

**To overlay:** **View → Arrange Calendars → Overlay**. Note this does *not*
work in **Month** view — switch to Week or Day first, or the menu item appears
to do nothing.

### Apple Calendar

**File → New Calendar Subscription**, paste the URL, set *Auto-refresh* to
Every day. Right-click the calendar → **Get Info** to change its colour. Each
feed ships a suggested colour that Apple picks up on first subscribe.

This is the only client that lets you set the refresh interval yourself.

### Don't import

Importing takes a one-time snapshot, and re-importing later duplicates every
event. Subscribing keeps the calendar in sync: events carry stable UIDs, so a
changed time, venue or speaker updates in place.

Subscribed calendars mirror the source and are read-only. To add your own
reminder or note to a particular seminar, copy that event into your personal
calendar and edit the copy.

## What's in an event

Series, speaker and affiliation, paper title where announced, host, venue, a
link back to the event page, and a Google Scholar search — for the paper once
its title is announced, otherwise for the speaker's own work.

**Check the venue.** Seminars alternate between Economicum (Arkadiankatu 7,
Helsinki) and the Aalto campuses in Otaniemi/Espoo, and the difference is a
half-hour trip.

Times and venues come from each event's detail page. Where a time has not been
published yet the entry is all-day rather than being given an invented one, and
its reminder fires at 09:00 that morning. HGSE does not publish abstracts, so
there are none to include.

## How it updates

A cron job regenerates the feeds from <https://www.helsinkigse.fi/events> and
pushes here only when something actually changed — so the commit history is a
log of schedule changes rather than of the job running. If the page layout ever
changes, the scraper parses zero events and stops without overwriting anything.
