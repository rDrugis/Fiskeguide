# Fiskeguide

Oppslagsside for sjøfiske fra båt i Norge: arter, sesonger, regler, redskap og agn, håndbok og ordliste.

Kart, dybder, fiskeplasser og algoritmeforslag ligger i søsterprosjektet [Fiskesim](https://rdrugis.github.io/fiskesim/).

**Åpne siden:** `https://<brukernavn>.github.io/<repo>/`

Hele siden er én fil (`index.html`). Den trenger ingen server, innlogging eller API-nøkler.

> Regler endres: sjekk alltid Fiskeridirektoratet før du fisker.

## Slik virker den

- Siden henter ingen data fra nettet utover skrifttypen. Valgt område, sted og måned lagres bare i nettleseren din (localStorage).

## Bruke den selv

1. Fork repoet, eller last ned `index.html`.
2. Slå på GitHub Pages: **Settings → Pages → Deploy from a branch → `main` / root**.
3. Siden er klar på `https://<brukernavn>.github.io/<repo>/`. Du kan også åpne `index.html` rett fra disk i nettleseren.

Kildekoden ligger i `index.html`. Hvis du bygger fra delene (`shell.html`, `data.js`, `app.js`), lager `python3 build.py` en ny `index.html`.

## Kilder

Tekst om arter, sesonger og teknikk er skrevet om med egne ord, med lenke til kilden der den står (blant annet Havforskningsinstituttet, Store norske leksikon, NJFF, Hooked og Mattilsynet). Regeltekst fra lover og forskrifter er ikke vernet av opphavsrett (åndsverkloven § 14).

## Lisens

Koden er lisensiert under MIT, se [LICENSE](LICENSE). Kildehenvisningene på siden må stå.
