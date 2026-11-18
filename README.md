# Fiskeguide

Oppslagsside for sjøfiske fra båt i Norge: sjøkart med live vær, bølger, strøm og tidevann, arter, regler, fiskesteder, algoritmeforslag og utstyr.

**Åpne siden:** `https://<brukernavn>.github.io/<repo>/`

Hele siden er én fil (`index.html`). Den trenger ingen server, innlogging eller API-nøkler.

> **Ikke for navigasjon.** Kartene og dybdene er hentet fra åpne kartdata og er ikke godkjente sjøkart. Bruk godkjente sjøkart og kartplotter når du kjører båt. Regler endres: sjekk alltid Fiskeridirektoratet før du fisker.

## Slik virker den

- Nettleseren til hver besøkende henter data direkte fra kildene nedenfor når siden åpnes, når du bytter sted eller når du trykker «Oppdater». Ingenting går via en egen server.
- Lagrede fiskeplasser, båtstørrelse og andre innstillinger lagres bare i nettleseren din (localStorage). Siden samler ikke inn noe.
- MET og de andre tjenestene får nettleserens IP-adresse når data hentes. Det er slik alle direkte API-kall fra en nettleser virker.
- «Strømsparing» under «Kilder» slår av kart og automatisk henting.

## Bruke den selv

1. Fork repoet, eller last ned `index.html`.
2. Slå på GitHub Pages: **Settings → Pages → Deploy from a branch → `main` / root**.
3. Siden er klar på `https://<brukernavn>.github.io/<repo>/`. Du kan også åpne `index.html` rett fra disk i nettleseren.

Kildekoden ligger i `index.html`. Hvis du bygger fra delene (`shell.html`, `data.js`, `app.js`), lager `python3 build.py` en ny `index.html`.

## Datakilder og vilkår

| Kilde | Brukes til | Vilkår |
|---|---|---|
| [MET Norway](https://api.met.no) | Vær, bølger, strøm, sjøtemperatur, farevarsler | CC BY 4.0. Forespørsler fra nettleser identifiseres med `Origin`-headeren (sidens adresse), se [vilkårene](https://docs.api.met.no/doc/TermsOfService). |
| [Kartverket](https://kartverket.no/api-og-data) | Sjøkart, topografisk kart, dybdedata, tidevann, stedsnavn, maritime grenser | CC BY 4.0. Tidevanns-API-et er gratis, men Kartverket ber om at det ikke belastes unødig. |
| [Open-Meteo](https://open-meteo.com) | Bølgeperiode | Data under CC BY 4.0. Gratis API kun til **ikke-kommersiell bruk** (under 10 000 kall per døgn), se [vilkårene](https://open-meteo.com/en/terms). |
| [Fiskeridirektoratet](https://www.fiskeridir.no/Kart) | Fiskeplasser, gyteområder, oppdrettsanlegg | Åpne data, krever kildehenvisning. |
| [NGU](https://www.ngu.no) | Bunntype (marine bunnsedimenter) | Åpne data, krever kildehenvisning. |
| [Leaflet](https://leafletjs.com) 1.9.4 | Kartbibliotek (bakt inn i `index.html`) | BSD 2-Clause, lisensteksten følger med i fila. |

Tekst om arter, sesonger og teknikk er skrevet om med egne ord, med lenke til kilden der den står (blant annet Havforskningsinstituttet, Store norske leksikon, NJFF, Hooked og Mattilsynet). Regeltekst fra lover og forskrifter er ikke vernet av opphavsrett (åndsverkloven § 14).

**Kommersiell bruk:** Bølgeperioden fra Open-Meteo krever da betalt abonnement, eller at den fjernes.

## Begrensninger

- Algoritmeforslagene er beregnet fra dybdekart og (der den finnes) bunntype. De er ikke testet mot fangst.
- Driftprediksjonen bygger på modellstrøm fra MET og målte driftrater fra USCG og MET. Strømmen i sund og nær land kan avvike mye.
- Bunntypekartet fra NGU finnes bare der NGU har kartlagt bunnen.

## Lisens

Koden er lisensiert under MIT, se [LICENSE](LICENSE). Data fra kildene over har egne vilkår, og kildehenvisningene på siden må stå.
