# Platform options for the website rebuild

*Last updated 2026-09-15 — this is a working notes document from the start
of the process. It exists to surface tradeoffs for board/committee
discussion, not to make the call. No option below is ruled out.*

## Why this doc exists

The rework plan ([rework-plan.html](rework-plan.html)) settled the
higher-level goal — leave WordPress — but not what replaces it. That
choice affects volunteers' day-to-day ability to edit the site for years,
so it belongs to whatever committee takes this up, informed by the
tradeoffs below rather than a single recommendation.

## Confirmed fact that affects every option

51 Walden has **full cPanel/FTP access** to its existing InMotion Hosting
account, which runs a **standard LAMP stack** (Linux, Apache, MySQL, PHP).
This matters regardless of which platform gets picked:

- It means a hand-coded static site is a real option, not just a
  theoretical one — the hosting to run it is already paid for.
- It means server-side pieces like a rental-inquiry form can run as a
  simple PHP script on that same account, without a new paid service,
  *if* the site ends up living there.
- It's irrelevant to Squarespace, Webflow, or Wix, which host themselves —
  those would leave InMotion unused (though still paid for, unless the
  hosting plan itself gets cancelled or repurposed).

## Options on the table

**WordPress, kept as-is or re-themed**
Lowest disruption, but keeps the plugin/core-patching burden and the
page-builder complexity that motivated this whole rework in the first
place. Included for completeness, not because it addresses the original
ask.

**Squarespace**
A dashboard any non-technical volunteer can use for text and photo
changes, native donation/event/form tooling, no patching. Costs a new
monthly subscription on top of hosting that's already paid for, and
trades away some design flexibility for its templates.

**Webflow**
More design range than Squarespace, still no-code, still no patching. The
visual builder has a steeper learning curve for whoever ends up
maintaining it — a real cost for an all-volunteer committee where that
person may change year to year.

**Wix**
Similar low-maintenance profile to Squarespace, with weaker content
modeling for something this site specifically needs: four resident groups
(Concord Band, Concord Players, Concord Orchestra, Opera51) that want a
consistent, repeatable page template.

**Static HTML on the existing InMotion account**
No new subscription — runs on hosting already paid for. Total design
control, hand-coded rather than fit into a template. The real cost is
losing a dashboard: every edit is a file change, not a click in a WYSIWYG
editor. That cost scales with how often the site actually needs to
change — historically, a handful of times a season, not weekly — and can
be softened by isolating the few things that do change often (the next
event, each resident group's season blurb) into a couple of small,
clearly labeled files with a short edit guide next to them.

## Questions for the committee, not answered here

- How much does a monthly subscription matter, given InMotion hosting is
  already a sunk cost either way?
- Who is expected to make routine content edits, and how comfortable are
  they (or whoever that turns out to be, over the years) with editing a
  text file versus using a visual editor?
- Does design distinctiveness matter enough to trade away a built-in
  dashboard, or is turnkey ease worth more than a fully custom look?

## Status

Open. For committee discussion at whatever point the board takes this up
— not a recommendation, and no option here is closed off.
