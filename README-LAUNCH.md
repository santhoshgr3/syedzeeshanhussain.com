# Deploying syedzeeshanhussain.com on Vercel

This folder is the complete website. It is ready to deploy as it is. Vercel needs no build step.

## Option A: Vercel website (no software needed)
1. Sign in at https://vercel.com (GitHub, Google or email).
2. Put this folder in a GitHub repository:
   - github.com → New repository → name it `syedzeeshanhussain` → *uploading an existing file* → drag in everything inside this folder → Commit.
3. Vercel → *Add New… → Project* → Import that repository.
4. Framework Preset: **Other**. Leave Build Command and Output Directory empty. Click **Deploy**.
5. You get a free address like `syedzeeshanhussain.vercel.app`. Open it and check the site.

## Option B: Vercel CLI (from this folder)
```
npm i -g vercel
cd C:\Users\HP\Downloads\szhussain-website
vercel            (first time: log in, accept defaults)
vercel --prod
```

## Connect the domain syedzeeshanhussain.com
1. Vercel → your project → *Settings → Domains* → add `syedzeeshanhussain.com` and also `www.syedzeeshanhussain.com` (set www to redirect to the main one).
2. Vercel shows the DNS records to add. At the company where you bought the domain (GoDaddy, Hostinger, BigRock, etc.), open DNS settings and add:
   - **A** record, name `@`, value `76.76.21.21`
   - **CNAME** record, name `www`, value `cname.vercel-dns.com`
   Use exactly what Vercel shows if it differs. Delete any old A record for `@` that points elsewhere.
3. Wait until Vercel shows the domain as *Valid* (minutes to a few hours). HTTPS is switched on automatically.

## After it is live
- Open the site on a phone and a laptop and scroll through the whole export journey once.
- Paste `https://syedzeeshanhussain.com` into WhatsApp to check the preview card.
- Google Search Console → add the domain → submit `https://syedzeeshanhussain.com/sitemap.xml`.

## Adding things later
- **Email:** once a mailbox exists (e.g. info@syedzeeshanhussain.com), ask Claude to add it to the contact section.
- **Track record:** real past shipments, IEC, GST and bank details can be added back as a section.
- **Trade destinations on the globe:** in `index.html`, find `var DESTINATIONS = [];` and add only confirmed ports, e.g.
  `var DESTINATIONS = [{name:"Jebel Ali, UAE", lat:25.01, lon:55.06}];`

Every change: edit the file, then redeploy (push to GitHub again, or run `vercel --prod`).

## Folder contents
- `index.html`: the website · `404.html`: page-not-found page
- `vercel.json`: caching and security headers for Vercel
- `assets/`: photos, icons, link preview image, world map data, `vendor/three.min.js` (3D library, MIT licence)
- `robots.txt`, `sitemap.xml`, `site.webmanifest`

World map data: Natural Earth (public domain).
