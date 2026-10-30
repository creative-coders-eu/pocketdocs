# Pocketdocs website

The public website for Pocketdocs: ID & Doc Wallet, a private iPhone wallet for passports, ID cards and
other documents. It is served by GitHub Pages from this repository, `creative-coders-eu/pocketdocs`, at
https://creative-coders-eu.github.io/pocketdocs/

The app's source lives in a separate private repository. This repository holds only the website.

| Path | Page | Used as |
|---|---|---|
| `/` | Landing page | Marketing URL |
| `/privacy/` | Privacy Policy | App Store Connect Privacy Policy URL, in-app link |
| `/terms/` | Terms of Use (they add to Apple's Standard EULA, which governs the licence) | Terms of Use (EULA) link on the paywall and in the description, in-app link |
| `/support/` | Support and FAQ | App Store Connect Support URL, in-app link |
| `/404.html` | Not-found page | Served by GitHub Pages for missing URLs |

## How it's built

- Plain HTML and one stylesheet, `assets/site.css`. No build step, no JavaScript.
- No cookies, analytics, trackers, external fonts or third-party requests. Each page has a
  Content-Security-Policy meta tag that only allows this site's own stylesheet and images.
- Light and dark mode follow `prefers-color-scheme`. Colour tokens are at the top of `site.css`; every
  text colour pair meets WCAG AA contrast.
- Links are relative, except in `404.html`, whose links start with `/pocketdocs/` because GitHub Pages
  serves it at any depth. Change them if the site moves to a custom domain.
- The header and footer are repeated in every page. When you change one, change all five.

Preview with `python3 -m http.server 8000` in this folder.

## Keep in sync with the app

- **Prices** (US): Pro Yearly $19.99 with a 1-week free trial, Monthly $3.99, Lifetime $39.99. Free
  holds up to 5 documents; Pro adds unlimited documents, family members and custom reminders. Must match
  App Store Connect and the landing page, Terms §6–7 and Support.
- **Privacy facts** the pages promise: no networking code, no account, no SDKs, "Data Not Collected";
  iOS Data Protection "complete" plus AES-GCM page-image encryption with a this-device-only Keychain
  key; Face ID/passcode lock; data excluded from backups unless "Include in iPhone backup" is on;
  device-only clipboard cleared after 60 seconds; reminder text names only the document type;
  "Delete all data" in Settings. Update the pages if any of these change.
- **Legal pages** are at version 1.0. Any change updates the version and effective date and adds a
  change-log entry; Terms §19 limits the reasons the Terms may change.
- **Company details** (KSH art. 206 § 1) are in every footer, in the first and contact sections of the
  Privacy Policy and Terms, and on the Support page, including the note that the share capital
  contributions have not been paid in. Remove that note from every page once they are paid in.
- **Contact is email only:** admin@ccoders.eu.
- **App Store badge.** The landing page shows "Coming soon". At launch, replace it with Apple's official
  badge linked to the product page.
- **Icons.** `favicon.svg` (a vector redraw of the app icon), `favicon.ico`, `apple-touch-icon.png` and
  `assets/pocketdocs-icon-512.png` come from the app icon. Replace them whenever the icon changes.
