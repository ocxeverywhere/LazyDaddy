# Plan: Update Verified Play Store Website Details

## Context
The website still shows a mixed set of Play Store facts after the recent homepage refresh. As of July 18, 2026, the public Google Play listing for `io.ocxeverywhere.easyreader` confirms the updated date (`Jul 7, 2026`), download threshold (`10+`), content rating (`PEGI 3`), app availability, and current release-note themes, but it does not expose a trustworthy current version string or Play provider in the inspected public page. The website should reflect only verifiable Play facts and avoid implying unverified metadata is current.

## Approach
Update the Korean and English Play-information sections so they present only currently verified public listing details. Keep the confirmed date and downloads threshold, revise the rating labels to match the public listing wording more closely, remove or relabel unverified provider/version rows, and add a short "What's new" summary derived from the live Play listing. Do not change privacy-policy content for this task.

## Files to modify
- `C:\PrivateProject\LazyDaddy\index.html` — Adjust the Korean Play information card to remove unverified metadata, align rating wording to the live listing, and add a short verified release-notes summary.
- `C:\PrivateProject\LazyDaddy\en\index.html` — Apply the equivalent English Play information updates and verified release-notes summary.

## Reused code
- Existing bilingual detail-grid structure for store metadata in `C:\PrivateProject\LazyDaddy\index.html:110` and `C:\PrivateProject\LazyDaddy\en\index.html:109`.
- Existing section styling and plain list/panel patterns already used on both home pages in `C:\PrivateProject\LazyDaddy\assets\site.css`.

## Language(s) detected
html

## Verification
- Review `git diff --check`.
- Review `git diff -- C:\PrivateProject\LazyDaddy\index.html C:\PrivateProject\LazyDaddy\en\index.html`.
- Confirm the updated website text only claims Play facts visible on the public listing dated July 18, 2026: updated date `Jul 7, 2026`, downloads `10+`, rating `PEGI 3`, and availability on Google Play.
- Confirm no privacy-policy files or site-config files changed as part of this Play-info-only follow-up.
