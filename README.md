# Catalog Parfumuri

Catalog static cu 132 de parfumuri — căutare, categorii (Femei / Bărbați / Unisex), sortare,
favorite, temă deschisă/închisă și ilustrație de flacon pentru fiecare produs.

Un singur fișier: **`index.html`**. Fără build, fără dependențe, fără server.

## Publicare pe GitHub Pages

1. Creează un repository nou (public) pe GitHub.
2. Urcă `index.html` în rădăcina repo-ului (Add file → Upload files → Commit).
3. Settings → Pages → *Build and deployment* → Source: **Deploy from a branch**,
   Branch: **main** / folder: **/ (root)** → Save.
4. După ~1 minut site-ul e live la `https://<utilizator>.github.io/<repo>/`.

## Fotografii reale (opțional)

Site-ul are ilustrații de flacon generate în SVG, potrivite ca formă și culoare fiecărui parfum.
Ca să folosești fotografii reale:

1. Creează folderul `img/` lângă `index.html`.
2. Pune pozele denumite după codul produsului: `001.jpg`, `089.jpg`, `118.jpg` …
3. În `index.html` caută linia `const PHOTOS=false` și schimb-o în `const PHOTOS=true`.

Dacă o poză lipsește, cardul revine automat la ilustrație — nu rămâne gol.
Pentru `.webp` sau `.png`, schimbă și `PHOTO_EXT`.

## Editarea produselor

Lista e în `index.html`, în blocul `const RAW`, câte un parfum pe linie:

```
categorie|cod|brand|nume|treaptă de preț
```

- categorie: `f` = femei, `m` = bărbați, `u` = unisex
- treapta de preț e definită mai sus, în `TIER`
  (`A` = 30ML 18€ / 70ML 35€, `E` = 50ML 52€ etc.)

Aspectul flaconului (siluetă, culoare, capac) se setează în blocul `const LOOK`.

## Link-uri partajabile

Filtrele intră în URL, deci poți trimite direct o selecție:

- `?cat=f` — doar parfumuri de damă
- `?q=sauvage` — rezultatele căutării
- `?sort=asc` — sortat după preț crescător
