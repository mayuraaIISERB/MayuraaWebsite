# Mayuraa Dance Club — Website Guide

## File Structure
| File | Purpose |
|---|---|
| `index.html` | Home page — carousel, announcements, achievements |
| `people.html` | Team members, past coordinators, faculty advisors, Spotify playlist |
| `events.html` | Workshops and events (tenure-wise) |
| `competitions.html` | IICM competitions (year-wise) |
| `contact.html` | Instagram and YouTube links |
| `logo.jpg` | Club logo |
| `SAMAN___.TTF` | Samarkan font file — do NOT delete |

---

## How to Update the Website

1. Download the file you want to edit from this repository (e.g. `index.html`)
2. Open Claude at claude.ai
3. Upload the file and describe what you want changed
4. Download the updated file Claude gives you
5. Upload it back to this repository (same filename)
6. GitHub Pages updates automatically within 1–2 minutes

---

## How to Add Photos

All photos are hosted on Google Drive — nothing heavy is uploaded to GitHub.

### Step 1 — Upload photo to Google Drive
- Upload your photo to the shared **Mayuraa Website Media** folder on Google Drive
- Organise it in the right subfolder (e.g. Events → 2025–26 → Independence Day)

### Step 2 — Make the photo accessible
- Right click the photo in Google Drive
- Click **Share → Anyone with link can view**
- Click **Copy link**

The link will look like:
```
https://drive.google.com/file/d/1aBcDeFgHiJkLmNoPqRsTuVwXyZ/view
```

### Step 3 — Get the File ID
Copy only the part between `/d/` and `/view`:
```
1aBcDeFgHiJkLmNoPqRsTuVwXyZ
```
This is your **File ID**.

### Step 4 — Add the photo to the website code

Use this format wherever you want the photo to appear:
```html
<img src="https://drive.google.com/thumbnail?id=YOUR_FILE_ID&sz=w800">
```
Replace `YOUR_FILE_ID` with the actual ID from Step 3.

---

## Where to Add Photos — By Section

### Carousel (Home page)
Find a slide placeholder like this:
```html
<div class="carousel-slide"><div class="slide-placeholder">...Photo 1...</div></div>
```
Replace with:
```html
<div class="carousel-slide"><img src="https://drive.google.com/thumbnail?id=YOUR_FILE_ID&sz=w800"></div>
```

### Events / Workshops / Competitions
Find a media thumb placeholder like this:
```html
<div class="media-thumb">Photo</div>
```
Replace with:
```html
<img src="https://drive.google.com/thumbnail?id=YOUR_FILE_ID&sz=w800" style="width:100%;aspect-ratio:16/9;object-fit:cover;">
```

### People Section
Find a person photo placeholder like this:
```html
<div class="person-photo">Photo</div>
```
Replace with:
```html
<img src="https://drive.google.com/thumbnail?id=YOUR_FILE_ID&sz=w400" style="width:100%;aspect-ratio:1;object-fit:cover;border-radius:4px;">
```

> Use `sz=w400` for people photos (smaller) and `sz=w800` for event/carousel photos (larger) for faster loading.

---

## Colour Scheme
| Colour | Hex Code |
|---|---|
| Green (primary) | `#00A86B` |
| Gold (accent) | `#D4AF37` |
| Blue (section titles) | `#1B6CA8` |
| Black (background) | `#0A0A0A` |

---

## Social Links
- **Instagram:** [@mayuraa_iiserb](https://instagram.com/mayuraa_iiserb)
- **YouTube:** Coming soon

---

## How to Temporarily Disable the Website
1. Go to repository **Settings → Pages**
2. Click **Unpublish site**
3. To bring it back, go to Settings → Pages → Deploy from branch → main → Save

---

## How to Add a New Tenure / Year
For each section (workshops, events, competitions):
1. Add a new year button in the `year-tabs` div
2. Add a new content div with the matching ID
3. Add the new ID to the `showYear` function in the script

Ask Claude for help with this if needed — just share the relevant HTML file.

---

## Notes for Future Coordinators
- Always share the **latest version** of the HTML file when asking Claude for changes
- Keep the `SAMAN___.TTF` and `logo.jpg` files in the repository — deleting them breaks the site
- The Spotify playlist ID can be updated in `people.html` — search for `YOUR_PLAYLIST_ID`
- YouTube link can be updated in `contact.html` once the channel is created
