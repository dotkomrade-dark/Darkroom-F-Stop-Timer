# F-Stop Timer

A darkroom exposure calculator for f-stop printing — test strips and
dodge/burn offsets, calculated in stops rather than raw seconds so timings
stay correct no matter what your base exposure is.

Single self-contained HTML file. No build step, no dependencies, no
tracking, nothing loaded from a CDN — open it and it works, online or off.

## Run it

**Locally:** download `fstop-timer.html` and open it in any browser.

**Hosted (GitHub Pages):**
1. Repo Settings → Pages
2. Source: Deploy from a branch → `main` → `/ (root)`
3. Save. GitHub will publish at `https://<username>.github.io/<repo>/fstop-timer.html`
   (or rename the file to `index.html` if you want it at the repo's root URL)

**On a phone:** open the hosted URL in Chrome or Safari, then use
"Add to Home Screen" from the browser menu for a full-screen icon — it's
not a formal installable PWA (no manifest/service worker yet) but this
gets you the same one-tap access.

## What it does

**Test strip tab** — set a base time and a stop increment, and it builds
a table of exposures for a test strip: either sequential from the base, or
centered on it with equal or custom step counts on either side. Tap any
row to send that time straight to the Dodge/Burn tab as its new base time.

**Dodge/burn tab** — set a base time and step through positive (burn) or
negative (dodge) stop offsets. Burn times are shown as the *additional*
time to run after the base exposure; dodge times are shown as how long to
hold back light *during* the base exposure — these are different physical
actions, so the tool doesn't just show a raw recalculated total.

**Shared rounding control** (bottom of the page) rounds all displayed
times to the nearest whole second or tenth of a second, since most
enlarger timers can't be set with arbitrary precision. Times under 2
seconds are flagged as hard to hand-time accurately, and if rounding ever
collapses two adjacent test strip steps to the same value, that's flagged
too.

## Status

This is the reference version for a native Android port (Kotlin/Jetpack
Compose) built separately. This HTML version is the one to treat as
source of truth for behaviour while that's in progress.

## License

Add a license of your choice here before making the repo public, if you
haven't already (e.g. MIT if you're fine with others reusing/adapting it).
