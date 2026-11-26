# Memory — website (GitHub Pages)

Static site: landing page, Privacy Policy, Terms of Use and account deletion page.
No build step. Push to GitHub and enable Pages.

| File | URL |
|---|---|
| `index.html` | `/` |
| `privacy.html` | `/privacy.html` → App Store / Play Console "Privacy Policy URL" |
| `terms.html` | `/terms.html` → paywall "Terms" link, App Store EULA field |
| `delete-account.html` | `/delete-account.html` → Play Console "Delete account URL" |
| `app-ads.txt` | `/app-ads.txt` → AdMob app-ads.txt doğrulaması (yayıncı kimliği: pub-3834148733890519). Alan adının köküne yayınlanmalı. |

## Fill in before publishing

Search the folder for `{{` and replace every placeholder:

| Placeholder | Example |
|---|---|
| `{{DEVELOPER_NAME}}` | Your name or company (as shown in the store) |
| `{{CONTACT_EMAIL}}` | support@yourdomain.com |
| `{{POSTAL_ADDRESS}}` | City, Country (a full address is recommended for GDPR/KVKK) |
| `{{EFFECTIVE_DATE}}` | December 1, 2026 |
| `{{GOVERNING_LAW}}` | the Republic of Türkiye |
| `{{INACTIVE_PERIOD}}` | 24 months |
| `{{ANALYTICS_PROVIDER}}` | PostHog or Amplitude (open decision Q4) |
| `{{CRASH_PROVIDER}}` | Sentry or Firebase Crashlytics |
| `{{AD_NETWORK}}` | Google AdMob or AppLovin MAX (open decision Q17) |

Also check before launch:
- The in-app paths named in the policy (`Me → Settings → Account → Delete account`,
  `Me → Settings → Privacy → Do Not Sell or Share`, `Me → Help`) must match the real app.
- If any provider in the privacy table is not used, remove its row.
- Have a lawyer review both legal pages before launch (see docs/13 §4).

## Publish

```bash
git init
git add .
git commit -m "Website: landing, privacy policy, terms"
git branch -M main
git remote add origin https://github.com/<user>/<repo>.git
git push -u origin main
```

GitHub → repo → **Settings → Pages** → Source: *Deploy from a branch* → `main` / `(root)` → Save.
Site: `https://<user>.github.io/<repo>/`
