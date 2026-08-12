# Amara 24/7 — route costing & revenue model (mobile)

An Android-framed interactive prototype of a route costing app for a road-freight
transporter. Set the rig and the cost base once, add routes, and every route is
costed on the same basis and ranked by margin.

## Screens

| Tab | What it does |
| --- | --- |
| Board | Best route on the board — margin gauge, net per month, cost-base completeness meter, ranked route list |
| Cost base | All ~40 inputs in collapsed sections: contract, rig & diesel, cycle time, running costs, wash & allowances, fixed costs, backloads |
| Docket | Margin headline, net profit, rand-per-km breakdown, feasibility/tank/loss flags, monthly cash flow ledger, diesel × rate sensitivity heat grid, 16 metrics |
| Compare | Every route on the same cost base, sortable by margin, net or cost per km |

Plus: routes editor, save/load scenarios, offline mode, share-as-PDF/WhatsApp,
dark / lite themes, and a refresh action that clears entries.

Every field starts empty — the model computes only from figures you enter, and
shows "—" until a route has km, a rate per ton and a cost base that yields loads.

## Files

- `Amara 24-7.dc.html` — the app (markup + logic in one file)
- `support.js` — runtime that renders the component
- `android-frame.jsx` — Android device frame (status bar, app chrome, gesture nav)
- `_ds/industry-.../styles.css` — Industry design system tokens and component classes

## Running it

It is static — no build step. Serve the folder over HTTP:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/Amara%2024-7.dc.html
```

Opening the file directly with `file://` will not work; the runtime fetches
sibling files.

## Publishing to GitHub

```bash
git init
git add .
git commit -m "Amara 24/7 — route costing prototype"
git branch -M main
git remote add origin https://github.com/<you>/<repo>.git
git push -u origin main
```

For a live link, enable GitHub Pages on the `main` branch (root) in the repo's
Settings → Pages.

## Note on the model

A planning estimate, excluding VAT and tax. Consumption baselines are planning
figures for a laden 34 t combination on good road, not OEM warranted values;
tank capacities vary by build. Replace both with your own fuel data.
