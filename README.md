# hgse-cal

Helsinki GSE seminars and doctoral defences as subscribable calendar feeds,
updated every morning except Sunday from the
[Helsinki GSE events page](https://www.helsinkigse.fi/events).

## Feeds

<!-- feeds:start -->

**Pick one or the other.** Taking the combined feed *and* a per-series
one shows those events twice.

### Everything in one calendar

| Calendar | Subscription URL | Events |
|---|---|---:|
| Everything | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse.ics` | 478 |

### One calendar per series

Take as many as you like. A seminar run jointly by two research
groups appears in both of their calendars, and so does a job talk or
a defence — under its own series as well as its kind. Either will
show twice if you subscribe to both.

| Calendar | Subscription URL | Events |
|---|---|---:|
| Behavioral Economics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-behavioral-economics.ics` | 21 |
| Colloquium | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-colloquium.ics` | 31 |
| Development Economics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-development-economics.ics` | 16 |
| Doctoral Defences | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-doctoral-defences.ics` | 26 |
| Econometrics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-econometrics.ics` | 11 |
| Economics of Education (Educa) | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-economics-of-education-educa.ics` | 18 |
| Environmental Economics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-environmental-economics.ics` | 33 |
| Industrial Organization | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-industrial-organization.ics` | 72 |
| Job Talks (practice) | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-job-talks-practice.ics` | 11 |
| Labor & Public Economics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-labor-public-economics.ics` | 71 |
| Macroeconomics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-macroeconomics.ics` | 15 |
| Microeconomics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-microeconomics.ics` | 22 |
| Trade, Regional and Urban Economics | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-trade-regional-and-urban-economics.ics` | 24 |
| VATT | `https://raw.githubusercontent.com/Lumikko-econ/hgse-cal/main/helsinki-gse-vatt.ics` | 51 |

<!-- feeds:end -->

---

## Subscribing

**Subscribe, don't import.** Importing takes a one-time snapshot, and
re-importing duplicates everything. Subscribed feeds stay in sync: events have
stable UIDs, so a changed time, venue or speaker updates in place.

Use the addresses in the tables above (`raw.githubusercontent.com/…`). If
you copy a file's address from GitHub's own page instead
(`github.com/…/blob/…`), the calendar app accepts it but shows no events:
that address serves the web page about the file, not the file itself.

| Client | How |
|---|---|
| **Outlook, Windows (classic)** | Calendar → **Home** → **Add Calendar** → **From Internet…** → paste → OK → Yes. `F9` forces a refresh. |
| **Outlook on the web / new Outlook** | <https://outlook.office.com/calendar/> → **Add calendar** → **Subscribe from web** → paste → **Import**. |
| **Outlook for Mac** | No working menu path — subscribe on the web (row above) and it syncs down through your account. |
| **Apple Calendar** | **File → New Calendar Subscription** → paste → set *Auto-refresh*. The only client that lets you choose the interval. |

**Seeing them side by side instead of overlaid?** Classic Outlook: click the
**←** arrow on a calendar tab, or **View → Overlay**. Outlook for Mac:
**View → Arrange Calendars → Overlay** (not available in Month view). On the
web: switch off **Split view**.

---

## What's in an event

Series, speaker and affiliation, title once announced, host, venue, and a link
to the event page.

Feeds are read-only — to add a note or an alert to a seminar, copy that event
into your own calendar and edit the copy.

**Check the venue**: seminars alternate between Economicum (Arkadiankatu 7,
Helsinki) and the Aalto campuses in Otaniemi, which is a half-hour apart.

Times and venues come from each event's detail page. Where no time has been
published the entry is all-day rather than being given an invented one. HGSE
publishes no abstracts, so there are none to include.

**Past seminars stay put.** HGSE's page lists upcoming events only, but these
feeds keep everything they have ever seen — so months later you can still scroll
back to find who spoke and what the paper was.

---

## How it updates

Every morning except Sunday, from <https://www.helsinkigse.fi/events>, pushed
only when something actually changed — so the commit history is a log of schedule
changes, not of the job running. If the page layout ever changes the scraper
parses zero events and stops without overwriting anything.

Your calendar app decides how often it re-reads the feed, so a newly announced
seminar may take a few hours to appear on your side.

---

Built and maintained by **Mikko Lumme**, Helsinki GSE / Aalto University.
If a series is missing, a link misbehaves, or something looks wrong, get in touch.
