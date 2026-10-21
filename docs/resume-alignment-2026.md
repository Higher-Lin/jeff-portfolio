# Portfolio resume alignment — implementation record

Date: 2026-10-21 (Taiwan). Release state: review branch only; no merge or deployment authorized.

## Baseline and sources

- Default branch: `main`; baseline commit: `048d08140f038f06eabd15e5ffdfb1a6bbafeddd`.
- Working branch: `portfolio/resume-alignment-senior-2026`.
- Approved copy: `Jeff_Lin_Portfolio_Phase1_Review.md`, sections 4.2–4.10 and change items C01–C20.
- Fact checks: `Jeff_Lin_Global_Tech_Career_Radar_EN_Senior_2026.pdf` and `Jeff_Lin_Global_Tech_Career_Radar_ZH_Senior_2026.pdf`, retrieved from Project Sources.
- Explicit user correction overrides the first review: Bellwether's role is **Marketing Specialist / 行銷專員**. Senior describes professional positioning only.

## Changed files

- `index.html`: approved English copy, experience dates, contribution labels, focus areas, additional project summaries and grouped tools.
- `zh.html`: matching Traditional Chinese copy, official title and phrase-based hero punctuation.
- `styles.css`: small additions for focus cards, supplementary project cards and long-text wrapping.
- `docs/resume-alignment-2026.md`: this implementation and QA record.

## Content Change Log status

| Item | Status | Implementation |
|---|---|---|
| C01 | Preserved | Brand eyebrow and main headline retained in both languages. |
| C02 | Complete | Approved hero copy; Senior Creative Production appears in the positioning line. |
| C03 | Complete in source; visual QA pending | Chinese comma moved to the end of the first title line. |
| C04 | Complete | Proof strip uses 10+, 17, 50+, 5+ with contribution/date/context labels. |
| C05 | Complete | Three focus areas added below Positioning. |
| C06 | Complete | Wild-Influx uses contribution, review and coordination wording. |
| C07 | Complete with existing data limitation | 13 Shorts through Sep 2026; 7,011 remains section-level, selected-period data. No exact period invented. |
| C08 | Complete | Exhibition copy includes display coordination, 50+ exhibits and pre-show-only Munich support. |
| C09 | Complete | BBC and MIM text summaries; no invented media URLs. |
| C10 | Complete | Virtual Production and MPC FX summaries; technical experience restored. |
| C11 | Complete | Content Output & Channel Context separates personal contribution from company audience statistics. |
| C12 | Corrected per user and latest resumes | Marketing Specialist / 行銷專員; first-review Creative Multimedia Producer proposal superseded. |
| C13 | Complete | MPC Jan 2022–Jan 2023; HTC Apr–Jun 2021; MoonShine Aug 2016–Mar 2021. |
| C14 | Complete | MoonShine brand projects, cross-tool workflows and virtual production added. |
| C15 | Complete | Four capability cards retained and updated. |
| C16 | Complete | Tools grouped by production discipline; AI tools follow latest resumes. |
| C17 | Deferred as specified | Cheerdigiart remains omitted from selected experience. |
| C18 | Deferred as specified | Crystalband/Zanflex not added pending release status and public assets. |
| C19 | Conservative approved default | No budget figures or contacted-vendor counts published; responsibilities described. |
| C20 | Preserved | Existing images, links, logo, animations, JavaScript and Cloudflare analytics retained. |

## Copy exceptions and bilingual consistency

- The first review's suggested Bellwether title was incorrect. The official role remains Marketing Specialist, translated as 行銷專員 in Chinese.
- The new Senior positioning follows the latest resumes and explicit implementation instruction; no employer role is promoted to Senior or Manager.
- Existing SEO title and description are preserved under the second-round instruction. No Open Graph tags existed in the inspected source; none were removed or added.
- English and Chinese retain 4 flagship films + 13 Shorts = 17 contributions through September 2026. Channel views remain 35K+, and channel markets 5+, for July 2025–September 2026.
- 7,011 is unchanged, with section-level attribution. The source still lacks exact reporting dates; the channel date range is not applied to it.
- No claims of paid-media operation, pipeline ownership, budget approval, direct reports or annual strategy ownership were added.
- The existing Shorts image and outbound channel link remain. No embedded video player existed; no individual 9:16 video embed was introduced.

## QA evidence and limits

Completed:

- Balanced HTML start/end tags; unique IDs and valid internal anchor targets in both pages.
- All 12 anchor URLs per page match the baseline, including language, project, social and email links.
- All 10 image references per page match the baseline and their files exist.
- All local stylesheet/script/image paths resolve on disk, including relative GitHub Pages paths.
- Existing meta tags and script attributes unchanged; `script.js` has no diff.
- `node --check script.js` passed.
- `git diff --check` passed after whitespace cleanup.
- CSS brace balance checked. Existing responsive breakpoints retained; new focus cards use 3 columns on desktop and 1 below 900px, new case summaries use 2 columns and 1 below 650px.
- Source-level bilingual fact check for official role, dates, counts, channel scope and exclusion of unsupported claims.
- HTTP HEAD checks: both existing YouTube film URLs and the Shorts channel returned 200. LinkedIn returned 999 and remains unverified. HTTP status checks do not verify playback or destination content.

Not verified:

- Actual browser layout at 1440, 1024, 768, 390, 375 or 320px; no responsive pass is claimed.
- Runtime console errors, horizontal scrolling, menu clicks, language-switch clicks, animations and image loading in the changed pages.
- Third-party video playback, social destination access and analytics collection.
- No browser executable was installed. Playwright Chromium installation failed because the downloaded archive was incomplete/invalid. No screenshots or hosted preview are claimed.
- No build or test scripts, package manifest, repository instructions, or custom Actions workflows were present in the inspected tree.

## Deployment control

The existing GitHub Pages dynamic workflow's recent runs were on `main`; the latest inspected successful run was `37401085719`, for the baseline SHA. No custom PR-triggered deployment workflow exists in the repository. The connector did not expose the Pages settings endpoint, so the exact administrative source-directory setting was not read. No settings were changed. Only the named working branch is updated; no merge, main push or live publication is performed.

## Review, preview and rollback

1. Check out the PR branch and run `python3 -m http.server 8000` from the repository root. Open `/index.html` and `/zh.html` locally.
2. Check desktop, tablet and phone layouts; verify hero punctuation, long titles, cards, mobile menu and language switching. Play the existing YouTube links manually.
3. Confirm the retained 7,011 selected-period presentation and any future supplementary project media separately.
4. Merge only after explicit approval and visual/functional review. A merge to main may trigger GitHub Pages deployment; inspect that new workflow and verify both live languages afterwards.
5. Before merge, close the PR to keep live unchanged. After an authorized merge, revert that merge through a separate reviewed PR; avoid resetting shared branch history.
