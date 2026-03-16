# Blaine Bailey Concert Map

A static GitHub Pages-ready site that shows Blaine Bailey's past venues on an interactive map with:

- search
- state / year / month filters
- marker clustering
- custom sidebar list
- smooth fly-to map animations
- Google Maps route links

## Do you need the Excel file in GitHub?

No. The website reads from `data/venues.json`, not from the Excel workbook.

The Excel file was used only to prepare the dataset. Once this site folder exists, GitHub only needs:

- `index.html`
- `data/venues.json`
- `.nojekyll`
- optionally this `README.md`

## Files

- `index.html` → the full site
- `data/venues.json` → concert data source
- `.nojekyll` → prevents GitHub Pages from trying to process the site with Jekyll

## Fastest GitHub Pages setup

1. Create a new GitHub repository.
2. Upload all files from this folder to the root of the repository.
3. In GitHub, open **Settings** → **Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. For the branch, choose **main** and folder **/(root)**.
6. Save.
7. Wait for GitHub Pages to publish the site.

Your site URL will usually look like:

- `https://YOUR-USERNAME.github.io/REPOSITORY-NAME/`

## Important note

Do **not** just double-click `index.html` and open it as a local file for normal use. Since the site fetches `data/venues.json`, it works best from GitHub Pages or a local web server.

## Optional local test

If you want to preview it on your computer before uploading:

### Python

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## Customizing the site

### Add more venues

Edit `data/venues.json` and add another object using the same structure:

```json
{
  "id": 24,
  "name": "Example concert name",
  "month": "January",
  "monthNumber": 1,
  "day": 1,
  "year": 2026,
  "venue": "Example Venue",
  "address": "123 Main St",
  "city": "Tulsa",
  "state": "OK",
  "dateLabel": "January 1, 2026",
  "geocodeQuery": "123 Main St, Example Venue, Tulsa, OK, USA"
}
```

### Change colors

Open `index.html` and edit the CSS variables near the top inside `:root`.

## Coordinates

This version includes preloaded latitude and longitude values in `data/venues.json`, so all pins render immediately on GitHub Pages without browser-side geocoding delays.
