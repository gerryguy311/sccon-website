# simplycybercon.org

Website for Simply Cyber Con, the annual community conference. Static HTML,
deployed on Cloudflare Workers static assets, source of truth in this repo.
Replaces the old Carrd site.

## Layout

```
public/            everything served at the domain
  index.html       the page (all sections, CSS and JS inline)
  404.html         not-found page
  assets/          og image, sponsor logos, speaker photos
wrangler.jsonc     Cloudflare config
```

## Common edits

- **Schedule and speakers:** both come from Sessionize (event `j2hgkhsf`, views
  GridSmart and SpeakerWall). Edit sessions, times and speakers in Sessionize and
  the site updates on its own. No code change or deploy needed.
- **Add a sponsor logo:** drop the file in `public/assets/sponsors/`, then copy
  one of the `<a class="sponsor">` lines in the Sponsors section and point it at
  the new file and the sponsor's link.
- **Next year:** update dates in the hero, schedule, FAQ, the JSON-LD block in
  `<head>`, and the countdown target near the bottom of `index.html`.

## Deploy

Every push to `main` deploys automatically (Cloudflare Workers Builds, connected
to this GitHub repo). For a one-off manual deploy:

```
npx wrangler deploy
```

## Local preview

```
npx wrangler dev
```
