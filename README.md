# Infrastructure Risk WebGIS

[English](#infrastructure-risk-webgis) | [Deutsch](#deutsch)

Interactive web map that publishes the results of two ArcGIS Pro analyses in the browser – no GIS software needed:

1. **Pluvial flood hazard for buildings – Essen-Kupferdreh** (DGM1 NRW, 2,864 buildings)
2. **Vegetation risk along the 110 kV overhead line 0285** (DOP10 NRW, 33 spans)

**Live map:** https://konstantinoschantzis.github.io/Infrastructure-Risk-WebGIS/

---

## Features

- Two tabs, one per project, with map, key figures, bar chart and ranking table
- **Click** a building or span for its attributes (sink depth, Strahler order, canopy cover per distance zone, risk / priority class)
- **Filter** by risk / priority class and switch flow paths, towers and study area on and off
- **Click a row** in the ranking table to zoom to that street or span
- Basemap switch: light grey canvas or aerial imagery (both Esri)
- German / English interface, works on mobile

## Data and processing

| Tab | Analysis in ArcGIS Pro | Published layers |
|---|---|---|
| Heavy rain Kupferdreh | Fill, sink depth, D8 flow direction, flow accumulation, Strahler stream order, zonal statistics, spatial join | 2,864 buildings with risk class, 2,333 flow path segments, study area |
| Vegetation risk 110 kV | Random Trees classification on DOP10 (RGB + NIR), majority filter, distance zones, overlay per span | 33 spans with canopy cover and priority, 34 towers |

The layers were exported from ArcGIS Pro with *Features To JSON* (GeoJSON, WGS 84) and reduced to the attributes shown on the map (rounded coordinates, short field names) to keep the page fast.

Full analyses and methods:
- [Pluvial-Flood-Hazard-Buildings](https://github.com/KonstantinosChantzis/Pluvial-Flood-Hazard-Buildings)
- [Vegetation-Risk-Utility-Corridors](https://github.com/KonstantinosChantzis/Vegetation-Risk-Utility-Corridors)

## Repository structure

```
├── index.html   web map (HTML, CSS, JavaScript)
└── data/        GeoJSON layers of both projects (+ data.js for offline use)
```

## Run locally

Download the repository and open `index.html` in a browser – the data is bundled in `data/data.js`, so no server is needed.

**Tools:** ArcGIS Pro 3.7 · Leaflet 1.9 · JavaScript · GeoJSON · GitHub Pages

**Data sources:** DGM1 and DOP10 © Geobasis NRW (dl-de/zero-2-0) · buildings, line and towers © OpenStreetMap contributors (ODbL) · basemaps © Esri

---

<a name="deutsch"></a>

# Infrastruktur-Risiko WebGIS

[English](#infrastructure-risk-webgis) | [Deutsch](#deutsch)

Interaktive Webkarte, die die Ergebnisse zweier ArcGIS-Pro-Analysen im Browser zeigt – ohne GIS-Software:

1. **Starkregen-Gefahrenanalyse für Gebäude – Essen-Kupferdreh** (DGM1 NRW, 2.864 Gebäude)
2. **Vegetationsrisiko entlang der 110-kV-Freileitung 0285** (DOP10 NRW, 33 Spannfelder)

**Zur Karte:** https://konstantinoschantzis.github.io/Infrastructure-Risk-WebGIS/

## Funktionen

- Zwei Reiter, je Projekt mit Karte, Kennzahlen, Balkendiagramm und Rangliste
- **Klick** auf ein Gebäude oder Spannfeld zeigt die Attribute (Senkentiefe, Strahler-Ordnung, Baumkronenbedeckung je Abstandszone, Risiko- bzw. Prioritätsklasse)
- **Filter** nach Risiko- bzw. Prioritätsklasse, Fließwege, Masten und Untersuchungsgebiet ein- und ausblendbar
- **Klick auf eine Zeile** der Rangliste zoomt auf die Straße bzw. das Spannfeld
- Hintergrundkarte wählbar: heller Grundkarte oder Luftbild (beide Esri)
- Oberfläche Deutsch / Englisch, mobil nutzbar

## Daten und Verarbeitung

| Reiter | Analyse in ArcGIS Pro | Veröffentlichte Layer |
|---|---|---|
| Starkregen Kupferdreh | Fill, Senkentiefe, Fließrichtung D8, Fließakkumulation, Strahler-Ordnung, Zonale Statistik, räumliche Verbindung | 2.864 Gebäude mit Risikoklasse, 2.333 Fließwegabschnitte, Untersuchungsgebiet |
| Vegetationsrisiko 110 kV | Random-Trees-Klassifikation auf DOP10 (RGB + NIR), Mehrheitsfilter, Abstandszonen, Verschneidung je Spannfeld | 33 Spannfelder mit Bedeckung und Priorität, 34 Masten |

Die Layer wurden in ArcGIS Pro mit *Features To JSON* (GeoJSON, WGS 84) exportiert und auf die in der Karte gezeigten Attribute reduziert (gerundete Koordinaten, kurze Feldnamen), damit die Seite schnell lädt.

Vollständige Analysen: [Pluvial-Flood-Hazard-Buildings](https://github.com/KonstantinosChantzis/Pluvial-Flood-Hazard-Buildings) · [Vegetation-Risk-Utility-Corridors](https://github.com/KonstantinosChantzis/Vegetation-Risk-Utility-Corridors)

**Werkzeuge:** ArcGIS Pro 3.7 · Leaflet 1.9 · JavaScript · GeoJSON · GitHub Pages

**Datenquellen:** DGM1 und DOP10 © Geobasis NRW (dl-de/zero-2-0) · Gebäude, Leitung und Masten © OpenStreetMap-Mitwirkende (ODbL) · Hintergrundkarten © Esri

---

*Konstantinos Chantzis · 2026 · MIT License*
