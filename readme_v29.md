# Logarithmic Timeline — v29
*Experimental, zoomable, vertical log-scale timeline of key events from the Big Bang → 2025.*

## What’s new in v29
- Comment tooltip: **inactivity autohide** (starts after 3 s idle, fades out in 3 s).
- Tooltip open: **300 ms delay** + **smooth fade-in**; follows pointer; **mobile-aware** left/right placement.
- Info box: **clear help text**, **status message** preserved, **author block** added (small font).
- License: **CC BY 4.0** shown **in infobox** and **as page footer** (low-key style).
- Title + version tag: `Logarithmic Timeline — Big Bang → 2025` + small `v29` span.

---

## How to use
- **Zoom**: pinch / wheel  
- **Pan/Scroll**: scroll or drag zoom window  
- **Focus theme**: click a card  
- **Read notes**: hover/tap event (tooltip with year + comments)

---

## Files touched in v29
- `log aikajana v29.html`
  - `applyOverlapFading()` → new `.event-label` handlers (delay + autohide + mobile placement + fade).
  - `#info-box` → updated `#help-message`, `#status-message`, added `#author` and `#license-info`.
  - Added fixed **footer** `#page-footer` with CC link.
  - Optional: `<h1 id="page-title">` updated, plus `<span style="font-size:0.75em">v29</span>`.

---

## Dev guardrails (keep features!)
> **When requesting changes, do not remove existing features.**  
> Always keep:
- Mobile-friendly tooltip placement (auto left/right + clamping)
- Tooltip fade **in/out** animations
- Long-press / click behavior for comments (if used)
- Info-box toggle and contents (help + status + author + license)
- Zoom behavior, axis decade ticks, minor grid
- Card styles (masks, shadows, label clamping)
**Reply with only changed lines or functions and say exactly what to replace where.**

---

## Known behaviors
- Tooltip hides if **no activity for 3 s**, fades out in **3 s**. Moving pointer resets timer.
- On narrow screens, tooltip **prefers left side** but flips to fit.

---

## License
- **Creative Commons BY 4.0** (link in info-box and page footer).  
- “Open experiment — no guarantees.”

---

## Changelog
- **v27**: minor-grid lines, sticky axis label, improved card backgrounds.
- **v28**: scroll-bar style zoom window, connector curves, auto-zoom hint to “ihmiskunta” card after 1.5 s.
- **v29**: inactivity-based comment tooltip fadeout, smoother fade-in/out, added author + license info, footer CC BY.

---

## Next ideas
- Theme filter (show/hide categories)
- Color legend + keyboard shortcuts
- Optional “lock tooltip” on click
- **Database selection: Fi / Eng toggle** (choose which JSON dataset to load)
