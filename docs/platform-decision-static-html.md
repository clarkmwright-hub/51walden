# Platform decision: static HTML on InMotion, not Squarespace

*2026-09-15 — supersedes the Squarespace recommendation in [rework-plan.html](rework-plan.html), section 03.*

## Context

The original rework plan recommended Squarespace on the theory that an
all-volunteer board with no developer on staff needs a zero-maintenance,
WYSIWYG platform. Two facts change that calculus:

- **Content churn is historically low.** The site only really changes a
  handful of times a season — a new "Up Next" event, an occasional
  resident-group season update, a rare news item (e.g. the HVAC upgrade
  post). It isn't being edited weekly.
- **Hosting is already paid for.** 51 Walden is on InMotion Hosting today.
  A static HTML/CSS/JS site runs on that same plan at no additional cost —
  Squarespace would have been a new recurring subscription on top of
  hosting that's already sunk.

Given that, a hand-built static site is worth reconsidering as the primary
option, with the tradeoffs made explicit below.

## Why it's the best choice here

- **Full build, no platform gap.** The whole site can be built end-to-end
  as code — no step where a human has to sit in a drag-and-drop editor to
  finish what a plan describes. Design control is total: the playbill
  direction in the visual plan becomes real CSS, not a template
  compromise.
- **No new subscription.** InMotion is sunk cost; static files serve from
  the existing shared hosting plan with no extra line item.
- **No plugin surface, no core patching.** None of WordPress's security
  treadmill — there's no CMS to exploit.
- **Matches the actual update cadence.** At 4–6 real content changes a
  season, the lack of a dashboard costs little.

## Why it's the worst choice, specifically

- **No WYSIWYG.** Every edit is: open a file, change text, re-upload via
  FTP/cPanel. There is no login a non-technical board member can use to
  change a headline.
- **Two features need more than flat HTML.** Static files can't process a
  submission server-side, so:
  - The **rental inquiry form** needs either a third-party form service or
    a small server-side script.
  - **Donation processing**, if not just a Stripe/Donorbox button embed,
    needs the same.
  - InMotion's shared Linux plans typically support PHP, so a simple
    `mail()`-based script can likely handle the rental form without
    introducing a new paid service — worth confirming against the actual
    plan.
- **Single point of failure.** If the one person who can edit HTML and
  push it live moves on, a "quick update before Saturday's show" stops
  being quick.

## Mitigation: isolate what actually changes

To blunt the single-point-of-failure risk, the build should isolate the
handful of things that genuinely change often into small, clearly labeled
files — not buried inside page layout markup:

- The "Up Next" event block
- Each resident group's current-season blurb

Paired with a one-page "how to update the next event" guide sitting next
to those files. This was already planned as an ongoing maintenance step
(Act V of the rework plan); on a coded site it carries more weight than it
would have on Squarespace, so it needs to actually get written and kept
next to the files it documents, not left as a future to-do.

## Open questions before build starts

- Does someone on the board/volunteer side have cPanel or FTP/SFTP access
  to the InMotion account?
- Is the InMotion plan Linux/shared with PHP support? (Almost certainly
  yes, but confirms whether the rental form is a free PHP script or needs
  a third-party form service instead.)

## Status

Pending confirmation before scaffolding the static site.
