# Women's Work: Making the Mediums — Moderated Participatory Archive (v5)

## What works
- Responsive public site with larger Arial/Helvetica type, dark mauve and light turquoise colors.
- Search and network showing **only reviewed, explicitly published records**, plus three clearly labeled demo research prompts.
- Submission form ready for a **Formspree endpoint** (not connected until you configure one).
- Separate local-only review workbench (`review-local.html`) that imports downloaded private Formspree JSON/CSV submissions, enables human review, and exports public `approved-records.json` containing **no private email/name fields**.
- Two editorial categories: community contribution approved for publication, and archival record verified. Archival verification requires evidence of MIT connection, Distinctive Collections holding, and period relevance.

## Publish to GitHub Pages
1. Create a public repository or use a project repository; upload `index.html` and `approved-records.json` to its root.
2. Under GitHub repository Settings → Pages, deploy from the `main` branch `/ (root)`.
3. In the Formspree dashboard, create a form and copy its endpoint, for example `https://formspree.io/f/abcdefgh`. In `index.html`, replace **only** `REPLACE_WITH_YOUR_FORMSPREE_ENDPOINT` with **your** endpoint. Commit the file. Do not paste account secret keys anywhere.
4. Test with a non-sensitive sample submission. Verify it arrives in **your Formspree dashboard** before advertising the site.
5. Be sure the submission wording and handling align with your project's ethics, consent and institutional review requirements before real participants are invited.

## Review and publish
1. Retrieve submissions from Formspree (dashboard or a CSV/JSON export when available for your plan). If your plan lacks exports, manually create a JSON array of form records, or use an upgraded service. This version does NOT automatically ingest or privately sync Formspree messages.
2. Keep `review-local.html` **on your own computer**, not in a public GitHub repository. Open it locally and import submissions; review each record. Back up your work via the private backup button (contains email addresses; keep private).
3. Request and document **separate publication permission** for story content and public attribution before ticking the permission checkbox. The initial form only grants permission for private review; **it is not permission to publish**.
4. Mark entries approved. Reserve 'Archival record verified' for evidence-backed records. Export `approved-records.json`.
5. Inspect the public JSON for accidental confidential/sensitive content, then replace `approved-records.json` in the GitHub Pages repository and commit. The public site will show the records once deployment completes.
6. To add records later without overwriting earlier approved records, import the *current* `approved-records.json` into the workbench along with new records; imported public records may require rechecking their permission state in the workbench. Keep a secure private backup of the full editorial review decisions.

## Important security and limitations
- GitHub Pages is **public static hosting**: do not publish private submissions, login secrets, private backups, or a purported private admin panel. `review-local.html` is not an authenticated moderation backend.
- Formspree receives submissions after setup; its dashboard and retention depend on the account plan. No automatic publication occurs.
- This simple client-side approach has no automated review synchronization, no participant accounts, no upload workflow, and no audit log. `approved-records.json` is public and should contain only consented content.
- Review of sensitive personal stories, oral histories, rights/permissions, and institutional human-participant requirements is needed before public recruitment.
- When opened via `file://`, some browsers block loading `approved-records.json`; test the public archive on GitHub Pages or a local web server (`python -m http.server`).
- Demo prompts are placeholders, not assertions about specific women or archival holdings.
