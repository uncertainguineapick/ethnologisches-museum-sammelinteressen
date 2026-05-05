# Daten zur GIS-basierten Analyse der Sammelinteressen des Ethnologischen Museums Berlin

> Projektarbeit von Firmin Forster (ORCID: [https://orcid.org/0000-0002-7051-8951](https://orcid.org/0000-0002-7051-8951))
> Folien der Projektpräsentation auf der DHNB2026 in Aarhus (auf englisch): [https://doi.org/10.5281/zenodo.19629975](https://doi.org/10.5281/zenodo.19629975)

## Abstract
Das Ethnologische Museum spielte durch einen Bundesratsbeschluss ab 1889 als zentrale Sammelstelle für Objekte aus den deutschen Kolonien eine wichtige Rolle im Deutschen Reich. Die Projektarbeit _Kolonialen Sammlungen auf der Spur. Eine Normdaten- und GIS-basierte Exploration der Sammlungsgeschichte des Ethnologischen Museums Berlin_ untersucht die räumliche und zeitliche Entwicklung der Sammelinteressen des Museums im Zeitraum von ca. 1870 bis 1950. 
Ausgangspunkt ist ein [Datensatz](./data/raw/em_entities.xlsx) mit 3.872 Einträgen zu Personen und Körperschaften. Nach der Datenbereinigung in OpenRefine und dem Abgleich von Koordinaten mit Wikidata wurden die Sammelinteressen als animierte Heatmap und [statische Gesamtkarte](./em_sammelinteressen_ff_static.png) visualisiert. Die Ergebnisse zeigen einen deutlichen Anstieg der Sammelinteressen ab den 1880er Jahren mit einem Höhepunkt zwischen 1905 und 1915, insbesondere in den deutschen Kolonien Afrikas und darüber hinaus in Lateinamerika und Ozeanien. Damit lässt sich zeigen, dass Sammelinteressen weit über formale Kolonien hinausgehen.
Die Unschärfen in den Ortsangaben stellen die Visualisierung vor technische Herausforderungen, werden hier jedoch zugleich als Einblicke in koloniale Weltvorstellungen verstanden.

![Sammelinteressen des EM 1870 bis 1950](./em_sammelinteressen_ff_animated.gif)

Die Projektarbeit ist im Rahmen des Projektmoduls im Masterstudiengang Digital Humanities an der Georg-August-Universität Göttingen im Wintersemester 2025/26 entstanden.

## Dateienverzeichnis

Der Ordner `data` enthält sämtliche Arbeitsdateien des Projekts.

```
data/
├── collectionsinterests/
│   └── em_sammelgebiet_full-coord_full-date.csv
├── gif/
│   ├── em_sammelinteressen_ff0000.png
│   ├── …
│   └── em_sammelinteressen_ff0089.png
├── openrefine/
│   ├── em_entities_openrefine.csv
│   └── em_ortsbezüge_koordinaten_openrefine.csv
├── qgis/
│   ├── ne_10m_coastline/
│   │   └── …
│   ├── ne_10m_ocean/
│   │   └── …
│   └── em_collectioninterests.qgz
└── raw/
    └── em_entities.xlsx
```


### `collectioninterests`
`em_sammelgebiet_full-coord_full-date.csv` enthält alle Sammelgebiete mit Informationen zur Erwähnungszeit der zugehörigen Entität, den Koordinaten, der Wikidata-ID, dem Namen und ID der zugeordneten Entität. Diese Datei wird für die Visualisierung in [QGIS](https://www.qgis.org/) genutzt, die Projektdatei findet sich hier: [`em_collectioninterests.qgz`](./data/qgis/em_collectioninterests.qgz).

### `gif`
Enthält 90 aus QGIS exportierte PNG-Dateien mit den Sammelinteressen der Jahre 1870 bis 1959.

### `openrefine`
`em_entities_openrefine.csv` ist die in OpenRefine aufbereitete und mit Koordinaten angereicherte Version von  [`em_entities.xlsx`](./data/raw/em_entities.xlsx).
`em_ortsbezüge_koordinaten_openrefine.csv` enthält alle individuelle Ortsbezeichnungen aus [`em_entities_openrefine.csv`](./data/openrefine/em_entities_openrefine.csv) und wurde zum Abgleich mit Wikidata benutzt.

### `qgis`
Die Ordner `ne_10m_coastline` und `ne_10m_ocean` enthalten Shapefiles von [Natural Earth](https://www.naturalearthdata.com/downloads/10m-physical-vectors/) als Basemap.
`em_collectioninterests.qgz` ist die Projektdatei für [QGIS](https://www.qgis.org/) (Version 3.34.15 LTR). Beim ersten Öffnen müssen die Ebenen neu mit [`em_sammelgebiet_full-coord_full-date.csv`](./data/collectioninterests/em_sammelgebiet_full-coord_full-date.csv) verknüpft werden.

### `raw`
`em_entities.xlsx` enthält die Rohdaten, wie sie vom Ethnologischen Museum zur Verfügung gestellt wurden.

## Verwendete Software

| Software        | Version     | Link                                                                                                       |
| --------------- | ----------- | ---------------------------------------------------------------------------------------------------------- |
| LibreOffice     | 25.8.4.2    | [https://de.libreoffice.org/](https://de.libreoffice.org/)                                                 |
| Microsoft Excel | 16.107.1    | [https://www.microsoft.com/de-de/microsoft-365/excel](https://www.microsoft.com/de-de/microsoft-365/excel) |
| OpenRefine      | 3.9.5       | [https://openrefine.org/](https://openrefine.org/)                                                         |
| QGIS            | 3.34.15 LTR | [https://www.qgis.org/](https://www.qgis.org/)                                                             |

## Lizenzierung & Nutzung
Dieses Repository steht unter der **[Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/)**. Das bedeutet: Du darfst die Daten teilen, verändern und kommerziell nutzen, solange du den Urheber nennst und unter gleichen Bedingungen weiterverbreitest (falls du bearbeitest).

## Zitationsempfehlung
Wenn Sie diese Daten in Ihrer eigenen Forschung verwenden, bitten wir um folgende Zitation im Literaturverzeichnis:

> Forster, F. (2026). *Daten zur GIS-basierten Analyse der Sammelinteressen des Ethnologischen Museums Berlin* [GitHub Repository]. https://github.com/uncertainguineapick/ethnologisches-museum-berlin-sammelinteressen (Zugriff am 24. März 2026).

## Bibliografie
- Deterts, D., Ortlieb, H., & Ethnologisches Museum, Staatliche Museen zu Berlin – Preußischer Kulturbesitz. (2024, April). Erweitertes Findbuch zum historischen Archiv und den historischen Sammlungsverzeichnissen im Ethnologischen Museum. [https://www.smb.museum/fileadmin/website/Museen_und_Sammlungen/Ethnologisches_Museum/02_Sammeln_und_Forschen/Forschung/Digitalisierung/Findbuch_Tektonik.pdf](https://www.smb.museum/fileadmin/website/Museen_und_Sammlungen/Ethnologisches_Museum/02_Sammeln_und_Forschen/Forschung/Digitalisierung/Findbuch_Tektonik.pdf).

- D’Ignazio, C., & Klein, L. F. (2020). Data Feminism. The MIT Press. [https://doi.org/10.7551/mitpress/11805.001.0001](https://doi.org/10.7551/mitpress/11805.001.0001).

- Ethnologisches Museum, Staatliche Museen zu Berlin – Preußischer Kulturbesitz. (2025). Culture Translocated: Entities in the Ethnological Museum [Xlsx]. [https://lab.sbb.berlin/culture-translocated/](https://lab.sbb.berlin/culture-translocated/) (Zugriff am 8. Oktober 2025).

- Forster, F., Goswami Choudhury, P., Süberkrüb, K., & Ziegler-Efimova, E. (2026, Januar 19). Uncertainties in the Archives. in: SBB Aktuell. Das Blog-Netzwerk Der Staatsbibliothek Zu Berlin – Beiträge Für Forschung Und Kultur. [https://blog.sbb.berlin/uncertainties-in-the-archives/](https://blog.sbb.berlin/uncertainties-in-the-archives/) (Zugriff am 23. Januar 2026).

- Friedman, B., & Nissenbaum, H. (1996). Bias in Computer Systems. in: ACM Transactions on Information Systems, 14(3), 330–347. [https://doi.org/10.1145/230538.230561](https://doi.org/10.1145/230538.230561).

- Lemercier, C. (2025, Dezember 17). In Defence of Dirty Data. Standardization, Source Criticism, and Digital/Quantitative History. vorgetragen auf: Digital History-Forschungskolloquium, Berlin. [https://www.youtube.com/watch?v=2LvFELxz1ro](https://www.youtube.com/watch?v=2LvFELxz1ro) (Zugriff am 28. Januar 2026).

## Danksagung

Diese Arbeit ist erst möglich geworden durch die großartige Unterstützung einiger Personen und Einrichtungen, denen ich an dieser Stelle meinen besonderen Dank aussprechen möchte:

- **Priyam Goswami Choudhury, Katharina Süberkrüb und Emily Ziegler-Efimova** für die produktive Zusammenarbeit und gemeinsame erste Exploration der Daten auf dem Hackathon [_culture.explore(data)_](https://lab.sbb.berlin/culture-explore-data/) des Stabi Lab an der Staatsbibliothek zu Berlin im Oktober 2025. Ein Blog-Post zu den Ergebnissen des Hackathons findet sich hier: [Uncertainties in the Archives - SBB aktuell](https://blog.sbb.berlin/uncertainties-in-the-archives/).

- Dem Team des [**Stabi Lab**](https://lab.sbb.berlin/provenienz-explorer/), namentlich **John Woitkowitz und Roman Kuhn**, für die Organisation des Hackathons, die freundliche und unterstützende Begleitung weit über den Hackathon hinaus sowie die Möglichkeit, die Ergebnisse des Hackathons als Blog-Post auf dem Blog der Staatsbibliothek zu Berlin veröffentlichen zu können.

- **Hendryk Ortlieb** vom Ethnologischen Museum Berlin für die Bereitstellung des Datensatzes und die vielen hilfreichen und interessierten Konversationen zu den Daten und dem Museum, auch in einem persönlichen Gespräch.

- **Susan Reichelt, Daniel Kurzawe und Christoph Kudella**, die es mir ermöglichten, verschiedene Aspekte und Herausforderungen dieses Projekts im Rahmen mehrerer Lehrveranstaltungen meines Masterstudiums Digital Humanities an der Universität Göttingen zu vertiefen und zu diskutieren.

- [**NFDI4Memory**](https://4memory.de/) für die finanzielle Unterstützung im Rahmen des Early Career Travel Grants, die es mir ermöglicht hat, Ergebnisse aus diesem Projekt auf der [DHNB 2026](https://dhnb.eu/conferences/dhnb2026/) in Aarhus, Dänemark, einem internationalen Publikum zu präsentieren.


---

Erstellt am 24. März 2026

Version: 1.0.1
