# Subscription Sweep

A phone-sized web app that finds the subscriptions you pay for and helps you cancel the ones you don't want.

The app is one file: [`app/subscription-sweep.html`](app/subscription-sweep.html).

## What it does

- **Finds subscriptions in three ways**
  - Links straight to your phone's own subscription lists: App Store (iPhone), Google Play (Android), PayPal automatic payments and Amazon memberships. Each of these lists every subscription billed through that account.
  - **Scans a bank statement.** You can upload a CSV, PDF, OFX/QFX or text file, or paste transactions. The scan runs on the phone. It spots about 60 known services from how they appear on statements (`NETFLIX.COM`, `APPLE.COM/BILL`, `GOOGLE *YouTubePremium`, `PAYPAL *HULU` and so on), plus any charge that repeats weekly, monthly, every 3 months or yearly at a steady amount.
  - When the app is opened inside Claude, **Ask Claude to read it** can also read screenshots and messy PDFs.
  - A searchable list of popular services with typical US prices, to tick off by hand.
- **One Cancel button per subscription.** It opens the right cancel page and says what to look for there. If you pay through Apple, Google Play, Amazon or PayPal, it sends you to that company's list instead, because cancelling on the service's own website won't stop those charges. You then mark the subscription as cancelled, and the app keeps a running total of what you're saving.
- Shows your monthly and yearly totals and what renews next.

## Limits

No app can cancel a subscription for you without signing in as you. The company always asks you to confirm on its own site, and often offers a discount to stay. The Cancel button gets you to the right page in one tap, and you confirm there.

Cancel links and typical prices are for the US and can go out of date. Every cancel screen also has a "Search how to cancel" link as a fallback.

## Where your data is saved

- **Opened as a Claude artifact:** your list is saved to your Claude account. Only the artifact's owner can read or change it.
- **Opened as a plain file:** your list is saved in that browser's local storage.

Statements you scan on the phone are never uploaded. Only **Ask Claude to read it** sends statement text or screenshots to Claude.
