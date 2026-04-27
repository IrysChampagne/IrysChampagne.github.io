# IrysChampagne.github.io

This is supposed to be an official website.  
Right now it is a Mother’s Day project.

Claude, ChatGPT and I spent a good morning on this!
(gotta juggle to avoid Claude usage limits)


---

## Purpose
Template for generating an interactive photo mosaic site.

---

## Requirements

- Hundreds of unique images (more = better)
  - Any format works
- Local Python environment (e.g., VS Code)
- One portrait image
  - Must be `.png`

---

## Converting HEIC → PNG

```bash
python -c "
from pillow_heif import register_heif_opener
register_heif_opener()
from PIL import Image
Image.open('me_mom.heic').save('me_mom.jpg', quality=90)
"
```

---

## Project Structure

```
project-folder/
│
├── mosaic_generator.py
├── me_mom.png
├── mosaic_manifest.json   (generated later)
├── index.html
└── photos/
    ├── img1.jpg
    ├── img2.jpg
    └── ...
```

---

## Step 1 — Generate Mosaic Locally

Run:

```bash
python mosaic_generator.py \
  --portrait me_mom.heic \
  --tiles ./photos/ \
  --output mosaic.jpg
```

Notes:
- Install required packages listed at the top of the script
- Adjust `GRID_COLS` and `GRID_ROWS` in the script to avoid distortion
- Output:
  - `mosaic.png`
  - `mosaic_manifest.json`

---

## Step 2 — Upload Mosaic

Use :contentReference[oaicite:0]{index=0}:

- Create account
- Upload `mosaic.png` to Media Library
- If file is too large (>10MB), compress first
- ChatGPT did the compressing for me.
- Update "src=.." for "id=mosaic-img" to your URL
- Mine is https://res.cloudinary.com/dmvo22ugr/image/upload/v1777301501/mosaic_np1j9m.jpg

---

## Step 3 — Deploy with GitHub Pages

Follow:
- :contentReference[oaicite:1]{index=1} Quickstart

Stop before editing README.

Add to repo:
- `index.html`
- `mosaic_manifest.json`
- portrait image(s)

---

## Step 4 — View Site

Open your GitHub Pages URL.  
Interactive mosaic should load.

Edit `index.html` to change titles (current version uses French placeholders).
