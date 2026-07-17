# Plan: Update the LazyDaddy Website for v1.2.0

## Context

Bring the Korean home page, English home page, and published privacy policy in line with the approved v1.2.0 product direction and the app repository's authoritative release/privacy documents. The privacy and product copy can ship before or with the app rollout. Release metadata must remain deployment-gated: the public Google Play page currently exposes an updated date of July 7, 2026 and does not provide verifiable evidence that v1.2.0 is live; its download threshold and live version are also not reliably available from the inspected listing response. Do not infer any of those values from repository dates.

## Approach

1. Replace the body of the web privacy policy with a faithful HTML rendering of both sections in `composeApp/PRIVACY_POLICY.md`, preserving the May 12, 2026 effective date and publishing the July 16, 2026 revision. Include exported audio/MP4 storage, user-triggered translation, Firebase Analytics defaults/control/categories/prohibited content/retention limits, editable support-email diagnostics and retention, and the expanded English summary.
2. Update both home pages in parallel so they remain equivalent in scope: add first-run guidance/sample audio and Settings support/contact actions to the existing feature-card grid; correct Cloud TTS wording to distinguish generated/cached cloud audio from Android built-in TTS; and replace each privacy summary with concise disclosures for Cloud TTS, saved-book translation, Analytics, support drafts, and user-managed exports, linking to the full policy.
3. Keep the current feature artwork unless visual review confirms that it makes a false v1.2.0 claim or an approved replacement asset is supplied. Retain and refine descriptive alt text as needed. Convert Open Graph image references to absolute GitHub Pages URLs so previews resolve consistently from nested pages; keep Korean and English metadata equivalent in meaning without repositioning the product.
4. Treat store fields as deploy-time metadata. Before publishing, inspect the production Play listing directly. Set version to `1.2.0` only when that release is public, copy the listing's displayed update date and download threshold exactly, and revalidate Android requirement, rating, provider, and availability. If v1.2.0 is not live or a value cannot be verified, preserve the currently published field rather than inventing it.

## Files to modify

- `C:\PrivateProject\LazyDaddy\index.html` — Add Korean onboarding/support feature copy, correct TTS and privacy summaries, conditionally update verified Play metadata, and make the Open Graph image URL absolute.
- `C:\PrivateProject\LazyDaddy\en\index.html` — Apply equivalent English product/privacy changes, conditionally update the same verified Play metadata, and make the Open Graph image URL absolute.
- `C:\PrivateProject\LazyDaddy\privacy\index.html` — Replace the outdated policy with the July 16, 2026 Korean policy and expanded English summary from the app repository while preserving working navigation and third-party links.

## Reused code

- Existing bilingual detail grids and feature-card structures: `C:\PrivateProject\LazyDaddy\index.html:102`, `C:\PrivateProject\LazyDaddy\index.html:174`, `C:\PrivateProject\LazyDaddy\en\index.html:101`, `C:\PrivateProject\LazyDaddy\en\index.html:173`.
- Existing side-by-side TTS/privacy panels and policy links: `C:\PrivateProject\LazyDaddy\index.html:245`, `C:\PrivateProject\LazyDaddy\en\index.html:244`.
- Existing shared responsive styling in `C:\PrivateProject\LazyDaddy\assets\site.css`; use its current grids, panels, tables, and link styles without adding CSS unless the final content exposes a layout defect.
- Authoritative v1.2.0 product facts: `C:\PrivateProject\EasyReader\composeApp\RELEASE_NOTES.md:15`, `C:\PrivateProject\EasyReader\composeApp\RELEASE_NOTES.md:19`.
- Authoritative Analytics, support-email, export, translation, and deletion disclosures: `C:\PrivateProject\EasyReader\composeApp\PRIVACY_POLICY.md:71`, `C:\PrivateProject\EasyReader\composeApp\PRIVACY_POLICY.md:89`, `C:\PrivateProject\EasyReader\composeApp\PRIVACY_POLICY.md:119`, `C:\PrivateProject\EasyReader\composeApp\PRIVACY_POLICY.md:138`, `C:\PrivateProject\EasyReader\composeApp\PRIVACY_POLICY.md:203`.

## Language(s) detected

html

## Verification

1. Review `git diff --check` and `git diff -- C:\PrivateProject\LazyDaddy\index.html C:\PrivateProject\LazyDaddy\en\index.html C:\PrivateProject\LazyDaddy\privacy\index.html`; compare every policy statement against `C:\PrivateProject\EasyReader\composeApp\PRIVACY_POLICY.md` and product claims against `RELEASE_NOTES.md` / `STORE_LISTING.md`.
2. Search the rendered/source pages for stale claims (`1.1.11`, `May 25`, Cloud-TTS-only transfer wording) and confirm deliberate retention of old Play metadata only when v1.2.0 is not yet public.
3. Serve the repository locally (for example, `python -m http.server 8000`) and test `/`, `/en/`, and `/privacy/` at desktop and mobile widths. Check headings, grids, long policy tables/lists, language switchers, relative assets, policy links, Play/developer/mail links, icons, and image alt text.
4. Inspect page metadata and link previews: titles/descriptions remain aligned across languages, and each `og:image` resolves to an absolute public image URL.
5. Immediately before deployment, re-open the production Google Play listing and record the displayed version, update date, downloads threshold, Android requirement, rating, provider, and availability. Apply only verified values; if v1.2.0 has not rolled out, publish the privacy/product changes while retaining the existing store metadata.
6. After deployment, fetch all three public URLs and confirm HTTP success, July 16, 2026 on the policy, both `Firebase Analytics` and support-email disclosures, and functional navigation from every page. After the Play rollout, repeat the listing comparison and update the gated fields to v1.2.0 values.
