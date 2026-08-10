# hgse-cal

Helsinki GSE seminars and doctoral defences as a subscribable calendar feed.

Helsinki GSE's own per-series Google Calendars stopped being updated in
December 2024, and `helsinkigse.fi/seminar-calendar` returns 404. The events
page itself is current, so this repository republishes it in a form calendar
apps can subscribe to.

## Subscribe

```
https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse.ics
```

**Apple Calendar** — File > New Calendar Subscription, paste the URL, set
*Auto-refresh* to Every day.

**Outlook** — Add calendar > Subscribe from web. Refresh interval is decided
by Outlook and can lag by several hours.

Do not *import* the file. Importing takes a one-time snapshot and re-importing
later duplicates every event. Subscribing keeps it in sync; events carry
stable UIDs, so a changed time or speaker updates in place.

## How it updates

A cron job regenerates the file from <https://www.helsinkigse.fi/events> and
pushes here only when something actually changed — so the commit history is a
log of schedule changes rather than of the job running.

Each entry carries the series, speaker, affiliation, title where announced,
and a link back to the event page. Events whose time has not been published
appear as all-day entries rather than being given an invented time.
