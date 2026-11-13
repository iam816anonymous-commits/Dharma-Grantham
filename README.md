# Dharma Grantham — Little Readers' Corner

A responsive, child-friendly reading portal for the two Telugu books. The site is designed for browser reading only; it does not include visible download links or download buttons.

## Deploy with GitHub Pages

1. Open **Settings → Pages** in this repository.
2. Choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
3. Upload the two final PDF files to the repository root using these exact names:
   - `book1.pdf` — చిన్న కథలు, గొప్ప విలువలు
   - `book2.pdf` — చిన్న శ్లోకాలు మరియు గొప్ప విలువలు
4. Open the published website and test both books on desktop and mobile.

The PDF files are not included in this initial commit. Add the final reviewed versions when ready.

## Important: connect feedback before inviting readers

The feedback form is currently a front-end placeholder. It validates the rating and fields, but does not persist or send submissions until a secure feedback endpoint is configured. Add a `feedback-endpoint` meta tag in `index.html` whose value is your HTTPS endpoint URL. The endpoint should validate input, rate-limit abuse, protect personal information, and store feedback for moderation. Keep database/service secrets on the server; never put admin keys in this page.

## Reading-only caveat

The page removes obvious download links and asks the browser PDF viewer to hide its toolbar. This is a convenience barrier, **not DRM**. A public PDF URL can still be retrieved by a determined visitor, and browser/PDF viewers may expose print or save controls depending on device and browser. Do not upload confidential or paid-final master files here. Publish watermarked preview copies if redistribution is a concern.

## Current status

- Responsive child-friendly single page: included.
- In-page PDF reader: wired to the two filenames above.
- Bookmark reminder: included.
- Feedback UI: included, but backend integration is still required.
- PDF assets: waiting for the final files to be uploaded.
