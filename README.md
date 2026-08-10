# hgse-cal

Helsinki GSE seminars and doctoral defences as subscribable calendar feeds.

Helsinki GSE's own per-series Google Calendars stopped being updated in
December 2024, and `helsinkigse.fi/seminar-calendar` returns 404. The events
page itself is current, so this repository republishes it in a form calendar
apps can subscribe to.

## Subscribe

Calendar apps colour by *calendar*, not by event, so the schedule is published
as two feeds. Subscribe to both, then set a strong colour on the first and a
muted one on the second — everything stays visible, but the fields worth
turning up for stand out.

**Core** — Industrial Organization, Colloquium, Microeconomics, Trade/Regional
& Urban, and doctoral defences. Carries a reminder at 08:00 on
the morning of each event.

```
https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-core.ics
```

**Other** — everything else: Macro, Labor & Public, Development, Environmental,
Behavioral, Econometrics, Economics of Education. No reminders; browse when you feel like it.

```
https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-other.ics
```

A combined feed of all events is also published as `helsinki-gse.ics`.
**Subscribe to the two split feeds *or* the combined one — never both schemes,**
or every event appears twice.

### Apple Calendar

File > New Calendar Subscription, paste a URL, set *Auto-refresh* to Every day.
Then right-click the calendar in the sidebar > Get Info to set its colour.
Repeat for the second feed.

### Outlook

Add calendar > Subscribe from web. Refresh cadence is decided by Outlook and
can lag by several hours.

### Don't import

Importing takes a one-time snapshot, and re-importing later duplicates every
event. Subscribing keeps the calendar in sync: events carry stable UIDs, so a
changed time, venue or speaker updates in place.

## What's in an event

Series, speaker and affiliation, title where announced, host, venue, a link back
to the event page, and a Google Scholar search — for the paper once its title is
announced, otherwise for the speaker's own work. Core entries are prefixed with a star so they read as
distinct even in clients that ignore calendar colour.

Times and venues come from each event's detail page. Where a time has not been
published yet the entry is all-day rather than being given an invented one, and
its reminder fires at 08:00 that morning.

## How it updates

A cron job regenerates the feeds from <https://www.helsinkigse.fi/events> and
pushes here only when something actually changed — so the commit history is a
log of schedule changes rather than of the job running. If the page layout ever
changes, the scraper parses zero events and stops without overwriting anything.
