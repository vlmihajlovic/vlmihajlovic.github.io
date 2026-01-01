# Projekat: Portfolio aplikacija (Vladimir Mihajlovic)

## Kratak opis

- Cilj: responsive sajt na srpskom koji prikazuje sve aplikacije (glavna stranica) + pojedinacne detaljne stranice.
- Izvor podataka: Play Store developer stranica. Trenutno dodata app `BG prevoz`.
- Glavne boje: narandzasta (#ff7a00, #f25f00), tamna pozadina (#050a19), svetli tekst.

## Struktura fajlova (trenutno)

- `index.html`: pocetna (naslov + podnaslov, vizuelni panel desno, lista aplikacija; bez hero sekcije).
- `apps/bg-prevoz.html`: detalji za BG prevoz.
- `app-ads.txt`: postojece, nismo dirali.

## Dizajn smernice

- Tamna pozadina sa gradijentima i “glassy” karticama; akcenti su narandzasti.
- Font: Space Grotesk (Google Fonts).
- CTA stil: primarni (gradient narandzasta) + sekundarni/ghost (border + blur).
- Grid layoutovi: `repeat(auto-fit, minmax(...))` za responzivnost bez puno media query-ja.

## Stanje stranica (trenutno)

- `index.html`: uvod (naslov “Mobilne aplikacije” + podnaslov), desno vizuelni panel (App Store & Play). Lista aplikacija: BG prevoz sa tagovima poravnatim uz naziv, dugme “Detalji” desno; nema Play Store dugmeta na kartici.
- `apps/bg-prevoz.html`: hero u tri kolone (ikonica, tekst, CTA desno vertikalno centriran). Sekcije: “Screenshots” (5 Play Store slika u gridu), zatim “Opis aplikacije” sa punim srpskim “About this app” tekstom (sve tacke + napomena). “Brzi pregled” uklonjen.

## Pending taskovi (prioritet)

1. Uvuci sve preostale aplikacije sa Play Store linka: naziv, opis (About this app), ikonica, ocena. Dodati u `index.html` + kreirati stranice u `apps/`.
2. Dodati ENG verziju (dvojezicno): toggle ili odvojene stranice (`/en/`).
3. Dodati SEO meta + Open Graph (title/description/image) po stranici.
4. Animacije/transitioni: trenutno samo hover; po zelji dodati scroll reveal za uvod/listu.
5. Kontakt/CTA sekcija: forma ili linkovi (LinkedIn, GitHub, email) u footeru.

## Zahtevi za pocetnu stranicu

- Hero ne treba da istice BG prevoz; kopija i vizuel treba da budu uopsteni.
- Vizuel moze biti mozaik/kolaz svih aplikacija (ikonice), ne jedna aplikacija.
- Glavni naslov i opis su genericki (nije vezano za jednu aplikaciju). (uradjeno)
- Opisi iz Play Store (About this app): koristiti tekst sa store-a (ne generisati). Za BG prevoz srpski tekst je unet na detaljnoj stranici.

## Napomene / tehnicki detalji

- Ostati u ASCII za tekst dok ne predjemo na dvojezicni set; `meta charset="utf-8"` je vec tu.
- Ne dirati postojece `.DS_Store` i `app-ads.txt`.
- Pri dodavanju novih aplikacija: imenovati fajl `apps/<slug>.html`, koristiti isti stil (kopija BG prevoz stranice uz sadrzaj app-a).
- Responsive target: mobilni (320px+), tablet, desktop 1200px.

## Podaci potrebni za detaljne stranice (po aplikaciji)

- Play Store paket i link (npr. `dev.mihajlovic.bgprevoz`), naziv aplikacije i ikonica URL.
- Ocena (ratingValue sa store-a) i kratak opis iz „About this app“ (SR verzija).
- Minimum 5 screenshotova (landscape 1052x592 gde postoji; fallback portrait), Play Store URL, iOS App Store URL (ako postoji).
- Ako postoji iOS verzija: navedite App Store link i da li se razlikuje naziv/opis/ocena.
- Prateci QR link ide na univerzalni redirect: `apps/store-redirect.html?android=<PlayURL>&ios=<AppStoreURL>`.
