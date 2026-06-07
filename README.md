# Pintrill Quiz — Which Collection Are You?

An interactive personality quiz that matches users to a Pintrill collection and drives them directly to product pages. Built as a single self-contained HTML file — no dependencies, no external CDN, no broken images.

---

## What's inside

- **5-question personality quiz** with lifestyle photo answer options
- **4 result collections:** Peanuts · Basquiat · Godzilla · Sonic the Hedgehog
- **Per-result product shelf** — 5 clickable product tiles with images linking directly to pintrill.com
- **Animated scrolling teal grid** background
- **3D Pintrill logo** fixed to the left side on desktop, rotated above quiz on mobile
- **PP Neue Bit Bold** font embedded (licensed)
- **Roboto Mono** for body text via Google Fonts
- All images base64-embedded — works on any host with zero external dependencies

---

## Files

| File | Description |
|------|-------------|
| `index.html` | The complete quiz — everything embedded in one file |
| `README.md` | This file |

---

## Hosting on GitHub Pages

1. Go to **Settings → Pages**
2. Source: **Deploy from a branch**
3. Branch: `main` / Folder: `/ (root)`
4. Save — live at `https://yourusername.github.io/pintrill-quiz` in ~60 seconds

---

## Embedding on Unbounce

Add a **Custom HTML** widget and paste:

```html
<iframe
  src="https://yourusername.github.io/pintrill-quiz"
  width="100%"
  height="950"
  frameborder="0"
  scrolling="auto"
  style="border:none; display:block;">
</iframe>
```

Adjust `height` if content is cut off.

---

## Updating content

All editable content is in the `<script>` block near the top of `index.html`.

### Change a question or answer label
Find the `QS` array and edit `label` or `text` fields.

### Update product links
Find the `RESULTS` object, locate the collection (e.g. `peanuts`), and edit the `products` array — each item has `label`, `url`, and `img`.

### Swap a result image
Find `const IMGS = {` and replace the base64 string for the relevant key (e.g. `peanuts_main`, `godzilla_main`).

### Add a new collection result
1. Add a new key to `RESULTS` with `headline`, `name`, `desc`, `mainKey`, `thumbKeys`, `shopLabel`, `shopUrl`, and `products`
2. Update quiz option `v:` values to point to the new key
3. Add the key to the `scores` object in state

---

## Quiz scoring

Each answer adds 1 point to one of 4 buckets: `peanuts`, `basquiat`, `godzilla`, `sonic`. The result with the most points wins. Ties go to whichever collection appears first in the sort.

---

## Notes

- File size is ~7MB due to embedded images and font — loads fine on any connection
- The PP Neue Bit Bold font is licensed to Pintrill — do not redistribute
- Quiz results and product links should be reviewed before each campaign
