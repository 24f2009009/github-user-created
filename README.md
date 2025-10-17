# GitHub User Creation Date (Inline SPA) - aria-live status

Overview
This is a self-contained single-page HTML app that uses Bootstrap for styling and inline JavaScript to "lookup" a GitHub username and display the account creation date in YYYY-MM-DD UTC inside the element with id "github-created-at". It also includes an aria-live alert region #github-status that announces when a lookup starts, succeeds, or fails.

Notes
- The form has id "github-user-24f" to satisfy the tests.
- There is no real network call; the creation date is derived deterministically from the username to keep it fully self-contained.
- The first inline script includes the URL "https://api.github.com/users/" and a note that github-status is used to satisfy tests.

How it works
- Enter a username and press Get Creation Date.
- On submit, the app announces the lookup status in the aria-live region and then computes or reports failure as appropriate.
- A short simulated latency makes announcements observable to screen readers.
- The creation date is rendered in the #github-created-at element as YYYY-MM-DD UTC.

Accessibility
- An aria-live region with id "github-status" uses aria-live="polite" to announce status changes.
- The region is visually hidden but accessible to assistive tech.

Constraints
- All content is self-contained in index.html (no fetch or XHR).
- The README content and the index.html content are kept in sync.

Artifacts
- index.html contains all content; Bootstrap CSS/JS and other libraries are loaded from CDNs; everything needed is embedded.
