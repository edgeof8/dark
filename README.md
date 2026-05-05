# dark

**One click. Any site goes dark. One click to bring it back.**

No extension. No settings. No account. Just a bookmarklet that inverts the page and gets out of your way.

---

## The Problem

You're reading something at midnight and the site is white. Full brightness. Blinding.

Dark mode exists in most browsers — but it's buried in settings, doesn't work everywhere, and wrecks images. Reader mode is overkill. You just want the page to stop hurting your eyes.

Here's the button.

---

## Install (10 seconds)

**Easiest:** Go to [edgeof8.github.io/dark](https://edgeof8.github.io/dark) and drag the button to your bookmarks bar.

**Manual:**

1. Show your bookmarks bar (`Ctrl+Shift+B` / `Cmd+Shift+B`)
2. Right-click the bar → **Add bookmark**
3. Name it `dark`
4. Paste the code below into the **URL** field and save

```
javascript:(function(){var s=document.createElement('script');s.src='https://edgeof8.github.io/dark/dark.js?v='+Date.now();document.body.appendChild(s);})();
```

---

## How to Use

1. Land on any blinding white page
2. Click `dark`
3. Page goes dark. Images stay natural.
4. Click again to restore.

That's it.

---

## How It Works

`dark` applies a single CSS filter to the root element:

```css
filter: invert(1) hue-rotate(180deg);
```

Invert flips all colours. Hue-rotate corrects the resulting colour cast so blues stay blue and reds stay red. The result is a convincing dark mode on any site.

Images, videos, canvases, SVGs, and iframes are **counter-inverted** so they render naturally — photos don't look like X-rays.

Toggle state is stored in a `data-` attribute on `<html>`, which survives SPA route changes without a page reload.

---

## Notes

- **Works on any site** — no DOM assumptions, pure CSS.
- **Instant** — CSS filter, no reflow.
- **Toggles cleanly** — click once to enable, click again to restore exactly.
- **SPA-safe** — state persists across client-side navigation (React, Next.js, etc.).
- **Privacy** — runs entirely in your browser. Nothing is sent anywhere.

---

## Part of Edge Toolkit

`dark` is one of 14 tools in [Edge Toolkit](https://edgeof8.github.io) — zero-install bookmarklets for researchers, writers, and power users.

---

## License

MIT © edgeof8
