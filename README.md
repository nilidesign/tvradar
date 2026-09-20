# tvradar.no

Oversikt over hvem som har TV-rettighetene til sport i Norge — hvilken kanal eller
strømmetjeneste som sender hver liga, og når avtalen går ut.

Statisk nettside uten byggesteg, database eller avhengigheter. Hele siden er én fil.

## Filer

| Fil | Hva det er |
|---|---|
| `index.html` | Hele nettstedet: markup, stil og data |
| `CNAME` | Domenet GitHub Pages skal svare på |

## Oppdatere rettighetsdataene

All data ligger i ett avgrenset område nær bunnen av `index.html`, merket:

```
/* ======= REDIGER HER. Dette er hele datagrunnlaget for siden. ======= */
```

Én rad per turnering:

```js
{sport:"Fotball", comp:"Premier League", svc:"viaplay", ch:"Viaplay / V Sport", slutt:"2028-06-30", v:1}
```

- `svc` — hvem som eier rettigheten, må matche en `id` i `SERVICES`
- `ch` — kanalene eller tjenestene sendingene faktisk går på
- `slutt` — datoen avtalen løper ut, brukes til tidslinjen og nedtellingen
- `v` — `1` når rettigheten er bekreftet mot en nyhetskilde, `0` når den må verifiseres

Husk å oppdatere `SIST_OPPDATERT` øverst i samme blokk. Den vises i footeren.

Når alle radene er verifisert, fjern `<div class="draft">`-banneret øverst i `<body>`.

## Publisering

Push til `main`. GitHub Pages bygger og publiserer automatisk.

## Design

Laget av [NiliDesign](https://nilidesign.com/html/index-no.html).
