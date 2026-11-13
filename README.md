# Dharma Grantham — Little Readers' Corner

A child-friendly, responsive reading portal for two Telugu books.

## GitHub Pages setup

1. Open **Settings → Pages**.
2. Choose **Deploy from a branch**, select `main` and `/ (root)`.
3. Upload the reviewed PDF files to the repository root:
   - `book1.pdf` — చిన్న కథలు, గొప్ప విలువలు
   - `book2.pdf` — చిన్న శ్లోకాలు మరియు గొప్ప విలువలు
4. Visit the published Pages URL and test both books on desktop and mobile.

## Reader reviews — static GitHub-only workflow

This site has no review backend. It uses browser `localStorage` to save a visitor's draft review on that same device. It then lets the visitor download a JSON submission file. The file must be sent to the Dharma Grantham owner separately; it is **not automatically transmitted** to the owner and is **not automatically published**.

### Publish approved reviews

1. Receive a visitor's `dharma-grantham-review-submissions.json` file.
2. Review it manually. Remove spam, private information and any review that should not be published. For children's privacy, prefer first names or nicknames; do not publish contact details or identifying information.
3. Open `reviews.json` in this repository.
4. Add only approved review objects to its `reviews` array. Each object uses:
   - `name` — display name
   - `book` — book title
   - `rating` — integer from 1 to 5
   - `review` — review text
5. Commit the updated `reviews.json` to `main`. GitHub Pages will publish the updated review cards after deployment.

Example:

```json
{
  "reviews": [
    {
      "name": "A Parent",
      "book": "చిన్న కథలు, గొప్ప విలువలు",
      "rating": 5,
      "review": "My child enjoyed the stories."
    }
  ]
}
```

The page reads `reviews.json` and fills the review cards from the approved public list. Empty placeholders remain when there are no published reviews.

### Important limitations

- Browser-saved pending reviews exist only in the browser/profile/device where they were submitted. Clearing site data can erase them.
- The visitor must download and send the JSON file to you through a channel you choose.
- Publishing is a manual owner action. This is deliberate: static GitHub Pages cannot securely accept and globally share anonymous submissions by itself.
- Never place a GitHub token or repository write credential in frontend JavaScript.
- Do not describe a submitted local review as received by Dharma Grantham until the JSON file has actually been delivered to the owner.

## Reading mode

The PDF reader renders pages onto a canvas with page and zoom controls. This hides normal browser PDF print/download controls, but it is not DRM: public PDF files can still be retrieved by technically capable visitors.
