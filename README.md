# Eventi Sagre

Mappa interattiva di sagre e rievocazioni storiche in Friuli Venezia Giulia e Veneto Orientale per l'anno 2026.

Il progetto è una singola pagina HTML statica ([index.html](index.html)) che mostra:

- una **mappa** (Leaflet + tile OpenStreetMap) con un marker per ogni evento;
- un **elenco laterale** di card, filtrabile per tipo evento e per data;
- un **toggle** per mostrare/nascondere gli eventi già passati.

I dati degli eventi (nome, luogo, provincia, date, coordinate, tipo) sono incorporati direttamente nello script della pagina, in un array JavaScript (`events`), senza backend né build step: basta aprire il file nel browser.

## Fonti dati

I dati sono tratti da [paesiinfesta.com](https://paesiinfesta.com/):

- [Sagre in Friuli Venezia Giulia e Veneto Orientale](https://paesiinfesta.com/sagre-in-friuli-venezia-giulia-e-veneto-orientale/)
- [Rievocazioni storiche](https://paesiinfesta.com/rievocazioni-storiche/)

## Struttura del progetto

```
index.html      pagina principale (HTML + CSS + JS, tutto in un unico file)
index copy.html copia di lavoro/backup di index.html
LICENSE          licenza Unlicense (pubblico dominio)
README.md        questo file
```

## Tecnologie utilizzate

- HTML/CSS/JavaScript vanilla (nessun framework, nessuna build)
- [Leaflet 1.9.4](https://leafletjs.com/) per la mappa interattiva (caricato via CDN unpkg)
- Tile di [OpenStreetMap](https://www.openstreetmap.org/)

## Funzionalità

- **Filtro per tipo**: Tutti / Sagre / Rievocazioni, tramite i pulsanti in alto nell'elenco.
- **Filtro per data**: selezionando una data, vengono mostrati solo gli eventi in programma in quel giorno.
- **Eventi passati**: nascosti di default; un pulsante dedicato permette di mostrarli (evidenziati in stile "attenuato").
- **Sincronizzazione mappa/elenco**: cliccando su una card la mappa centra e apre il popup del marker corrispondente, e viceversa.

## Comandi utili

Non essendoci build step né dipendenze da installare, non sono richiesti comandi di build. Per lavorare sul progetto:

```bash
# Aprire il progetto in locale (macOS)
open index.html

# Avviare un server locale (utile per evitare limitazioni del browser su file://)
python3 -m http.server 8000
# poi visitare http://localhost:8000/index.html

# Vedere lo stato del repository
git status

# Vedere lo storico delle modifiche
git log --oneline

# Creare un commit
git add index.html
git commit -m "Descrizione della modifica"
```

## Licenza

Progetto rilasciato in pubblico dominio secondo i termini della licenza [Unlicense](LICENSE).
