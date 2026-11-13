# 🌲 Spokane Happenings: spokane-activities

One place to see what's going on around Spokane: **Spokane, Spokane Valley, Liberty Lake, North Spokane/Mead/Deer Park, Airway Heights/West Plains, Cheney and Coeur d'Alene/Post Falls**.

**Live site:** https://joemarcouxid.github.io/spokane-activities/

## What it does
- **Today · This Weekend · Next 7 Days · This Month · This Year** tabs, with a count on each
- **🎟 Plan Ahead**: concerts, shows and big ticketed events a week or more out (Arena, First Interstate Center, Fox, Knitting Factory, Northern Quest, BECU Live and more), with **🆕 newly announced** flags
- **⭐ My List**: tap ☆ to save events on your phone
- Filter by town and by kind, or search ("Zags", "food truck", "trivia", "kids")
- **🔄 Refresh** loads the latest scan; **Scan now** runs a fresh scan on GitHub
- **📅 Add** puts any event in your phone calendar (big events get reminders 2 weeks and 1 day before)
- **＋ Add a tip** for food truck posts, flyers and Facebook events the scanner can't see

## Heads-up for tickets
1. **Phone calendar:** on the Plan Ahead tab tap **Subscribe on this phone** (`webcal://joemarcouxid.github.io/spokane-activities/data/plan-ahead.ics`). Concerts and big events appear in your calendar with a reminder 3 weeks out.
2. **Email / GitHub app alert:** new concerts and big events open a "🎟 New events announced" issue. **Watch** this repo to get notified.

## How it works
Every 3 hours GitHub Actions runs `scripts/collect.py`. It reads the public calendars in `docs/data/sources.json` (Visit Spokane, The Inlander, Downtown Spokane Partnership, the libraries, the big venues, Songkick, AllEvents, HappeningNext, plus dated event posts on r/Spokane and Bluesky), removes duplicates, tags events by town and kind using `docs/data/region.json`, and writes `docs/data/events.json`. GitHub Pages serves `docs/`.

**Sources & status** at the bottom of the site shows which sources are working. Some sites block automated readers; edit `docs/data/sources.json` to add or change one.

This app shares its engine with [wenatchee-activities](https://github.com/joemarcouxid/wenatchee-activities). Only `docs/data/region.json` (towns, venues) and `docs/data/sources.json` differ.

## One-time setup
1. **Settings → Pages →** Source: *Deploy from a branch*, Branch: `main`, Folder: `/docs` → Save
2. **Actions → "Scan for events" → Run workflow** for the first scan (if Actions asks, click "I understand… enable")
3. **Watch** the repo so new-event alerts reach you
