# FFS Availability Tracker

A single-page browser tool for checking featured firm slot availability. Load a Feature Slots by Office export and it shows, for a chosen period, which areas have open slots, how many weeks a new or existing firm could book within the booking rules, and which firms are close to their 52-week cap.

The export is read locally in your browser. Nothing is uploaded, sent anywhere or stored, and the tool contains no booking data of its own.

## URLs

- Production: https://wearesunday.github.io/ffs-availability-tracker/ffs-availability-tracker.html
- Dev: https://wearesunday.github.io/ffs-availability-tracker/ffs-availability-tracker-dev.html

GitHub Pages serves the `main` branch from the repository root. After a push, allow a few minutes for the live pages to update (a hard refresh helps).

## Updating and promoting

1. **Make every change in the dev file** (`ffs-availability-tracker-dev.html`), commit with a message describing the change, and push to `main`.
2. **Test the dev URL** with a current export.
3. **Promote to production** once dev is signed off, by copying the dev file over the production file:

   ```
   cp ffs-availability-tracker-dev.html ffs-availability-tracker.html
   git add ffs-availability-tracker.html
   git commit -m "Promote dev to production: <short summary>"
   git push
   ```

4. Never edit `ffs-availability-tracker.html` directly. Production should only ever change by promotion from dev.

## Rolling back production

Find the last good commit with `git log -- ffs-availability-tracker.html`, then:

```
git checkout <commit> -- ffs-availability-tracker.html
git commit -m "Roll back production to <commit>"
git push
```

## Before publishing anything

GitHub Pages sites can be reached by anyone with the URL. Never commit exports, firm or booking data, names, contact details or credentials to this repository.
