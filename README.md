# SubTrack Pro

A private, single-file subscription manager for freelancers, business owners, and engineers who pay for AI tools, developer services, and other software every month.

SubTrack Pro shows what you spend, warns you before renewals, and suggests where you can cut costs. It runs entirely in your browser. There is no account, no server, and no tracking.

## Features

* **Dashboard:** monthly and yearly totals, a 12-month projection, spend by category, renewals in the next 30 days, and recommendations.
* **Recommendations:** advice based on your role (freelancer, business owner, or engineer). It flags unused tools, suggests checking annual pricing for monthly plans of $10 or more, and notes when you pay for several AI tools.
* **Reminders:** each subscription has its own lead time (1–30 days). The Reminders page lists renewals that fall inside that window. Browser notifications are optional.
* **Subscription management:** add, edit, delete, search, filter by category, and sort by renewal date, monthly cost, or name.
* **Known subscriptions:** pick from a dropdown of common tools (name, category and typical price fill in automatically), or choose "Other" and type your own.
* **Customisable settings:** choose your role from a list or type your own, and pick your currency from a list or enter a custom symbol.
* **Validation:** name and renewal date are required, cost must be between 0 and 100,000, lead time must be a whole number from 1 to 30, and duplicate names are rejected. The form shows the monthly and yearly equivalent as you type.
* **Guided tour and User Guide:** a short walkthrough appears on your first visit. You can replay it from the User Guide page.
* **Loading states:** placeholder blocks show while the dashboard and table render.
* **Themes:** a dark orange luxury theme by default, with a light theme available. Toggle from the header.
* **Data tools:** JSON backup and restore, CSV export, Xero-style CSV export, and a full local wipe.
* **Undo:** up to 50 recent changes.
* **Keyboard shortcuts:** `N` to add a subscription, `/` to jump to search, `Esc` to close dialogs, and `Ctrl`/`⌘` + `Z` to undo.

## Quick start

1. Download or clone this repository.
2. Open `index.html` in a modern browser (Chrome, Edge, Firefox, or Safari).
3. Either click **Load demo data** on the Settings page to explore, or click **+ Add** to enter your own subscriptions.

No build step, server, or package installation is needed.

## Where things are

|Control|Location|
|-|-|
|Add a subscription|**+ Add** button in the header, or press `N`|
|Edit or delete a subscription|**Edit** and **Delete** on each row of the Subscriptions page|
|Search, filter, sort|Subscriptions page toolbar|
|Export CSV|Subscriptions page|
|Export Xero CSV|Subscriptions page, next to Export CSV|
|Export JSON, import JSON|Settings → Data|
|Load demo data, delete all data|Settings → Data|
|Your role, currency, default lead time|Settings → Profile (click **Save settings**)|
|Browser notifications|Settings → Data → **Enable notifications**|
|Replay the tour|User Guide page|
|Light/dark theme|**Theme** button in the header|
|Undo|**Undo** button in the header, or `Ctrl`/`⌘` + `Z`|

## Working with your data

* **Backups:** use **Export JSON** regularly. The file contains every subscription and your settings, and you can restore it with **Import JSON**. Importing replaces your current data.
* **Spreadsheets:** **Export CSV** produces one row per subscription, including the monthly equivalent, for Excel or Google Sheets.
* **Xero:** **Export Xero CSV** produces a file in Xero's invoice import layout (ContactName, InvoiceNumber, dates, Total, AccountCode, TaxType, Currency). Review the account code `404` and tax type in Xero before importing, as they depend on your chart of accounts. CSV exports are export-only and cannot be imported.
* **Deleting everything:** **Delete all data** removes all subscriptions and resets settings. Undo cannot reverse it, so export a backup first.

## Notifications

Browser notifications only appear while SubTrack Pro is open in a tab. The app cannot send notifications when the browser is closed. You get at most one notification per day. The first time you enable them, the browser will ask for permission.

## Hosting

Because it is one static file, you can host it anywhere:

* **GitHub Pages:** Settings → Pages → deploy from the `main` branch.
* **Netlify or Cloudflare Pages:** drag and drop the folder.
* **Local use:** open the file directly.

## Privacy

All data is stored in your browser's `localStorage` under the key `subtrack.pro.v1`. Nothing is sent to any server. Clearing your browser's site data deletes everything, so export a JSON backup first.

Data is stored per browser and per device. It does not sync between computers or browsers.

## Limits

* **Currency:** each subscription is stored in the single currency you select in Settings. Multi-currency conversion is not supported yet.
* **Storage size:** browsers allow several megabytes of localStorage, which is far more than a typical list of subscriptions needs.
* **Private windows:** in some browsers, data saved in a private or incognito window is lost when the window closes.
* **Renewal dates:** the app assumes each subscription renews on the same day of the month (or week, quarter, or year). If a billing date moves, edit the subscription's next renewal date.

## Project structure

```
subtrack-pro/
├── index.html   # The entire application (HTML, CSS, JavaScript)
├── README.md
├── LICENSE      # MIT
└── .gitignore
```

## Customising

* **Categories:** edit the `<option>` list in the add/edit form inside `index.html`.
* **Recommendation rules:** edit `buildRecommendations()` in the script.
* **Renewal maths:** edit `CYCLE\_MULT` (monthly equivalents) and `nextRenewal()` (date roll-forward).

## Roadmap

* Multi-currency conversion
* Recurring-cost forecasting by year
* Printable monthly report

## Licence

MIT License



Copyright (c) 2026

