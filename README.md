# FluchtPlanPro Website

Bilingual (German/English) corporate website for FluchtPlanPro — professional fire evacuation plan design services in Germany.

## Structure

```
.
├── index.html          Main page (all sections, bilingual content)
├── css/
│   └── style.css        All styling
├── js/
│   └── script.js        Language switcher, form validation, animations, lightbox
├── images/
│   └── sample-fluchtplan.jpg   Real sample evacuation plan shown on the site
└── README.md
```

## Run locally

Just open `index.html` in a browser — no build step needed. For best results (so the browser doesn't block relative paths), serve it with a simple local server, e.g.:

```
python3 -m http.server 8000
```

then visit `http://localhost:8000`.

## Deploy with GitHub Pages

1. Create a new GitHub repository (e.g. `fluchtplanpro-website`) and push these files to the `main` branch, keeping the folder structure above.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Set **Branch** to `main` and folder to `/ (root)`, then **Save**.
5. GitHub will publish the site at `https://<your-username>.github.io/<repo-name>/` within a minute or two.

### Using a custom domain (e.g. fluchtplanpro.de)

1. In **Settings → Pages → Custom domain**, enter your domain and save (this creates a `CNAME` file in the repo automatically).
2. At your domain registrar, add a `CNAME` record pointing your domain (or subdomain) to `<your-username>.github.io`.
3. Wait for DNS to propagate, then enable **Enforce HTTPS** in the Pages settings once available.

## Editing content

- All text lives in `js/script.js` inside the `i18n` object (`de` and `en` keys) — edit the strings there, not directly in the HTML, since JavaScript overwrites the HTML text on page load based on the selected language.
- Static structural content (which sections exist, image sources, links) is edited directly in `index.html`.
- Colors and layout are controlled by CSS variables at the top of `css/style.css` (`:root { --green: ...; }`).
