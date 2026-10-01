# Morocco — Night-Time Lights subnational indicators
# Morocco — Indicateurs infranationaux de lumières nocturnes

> Produced during the **STG17 Technical Workshop — *Emerging Issues, Emerging Practice***
> (African Development Bank · AU STATAFRIC · Day 4 — *Africa after dark*).
> Produit lors de l'**atelier technique STG17**, jour 4.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/musttaleb2017/ntl-mar-stg17/blob/main/notebook.ipynb)

**Dashboard / Tableau de bord :** see the GitHub Pages URL of this repository.
**Verdict:** `EXPERIMENTAL` — see [`LIMITATIONS.md`](LIMITATIONS.md) **before citing anything**.

---

## EN — What this is

A reproducible pipeline that turns VIIRS night-time light rasters into subnational statistical indicators for
Morocco (MAR), across 3 administrative levels and seven
analytical scenarios: economic activity, electrification, urbanisation, spatial inequality, change detection,
shock monitoring and validation against official statistics.

**Night-time lights are a proxy.** They measure upward radiance at ~01:30 local time and nothing else. Every
indicator here is an *inference*, and the inference is tested in the validation scenario. Read `LIMITATIONS.md`.

### Contents
| Path | What |
|---|---|
| `index.html` | Bilingual (EN/FR) interactive dashboard |
| `data/*.csv` | Indicator tables, one per administrative level and year |
| `data/*.geojson` | Simplified ADM1 boundaries used by the map |
| `manifest.json` | Full run record: parameters, thresholds, software versions, artefact diagnostics |
| `LIMITATIONS.md` | Limitations statement — part of the deliverable, not an afterthought |
| `notebook.ipynb` | The complete, documented pipeline (open it in Colab with the badge above) |
| `requirements.txt` | Pinned minimum versions, for a local run |

### Reproduce
```bash
pip install numpy pandas geopandas rasterio shapely plotly matplotlib requests
jupyter lab notebook.ipynb     # set CONFIG["ISO3"] and CONFIG["PROVIDER"], run all
```

### Key parameters of this run
| Parameter | Value |
|---|---|
| Baseline → endline | 2015 → 2024 |
| Provider | `gee` |
| Noise floor | 0.25 nW·cm⁻²·sr⁻¹ |
| Urban-core threshold | 10.0 nW·cm⁻²·sr⁻¹ |
| Top-coding | p99.9 = 91.3 |
| Administrative levels | ADM0 (1), ADM1 (12), ADM2 (75) |
| Best Spearman ρ (validation) | 0.982 |

---

## FR — De quoi s'agit-il

Une chaîne de traitement reproductible qui transforme des rasters de lumières nocturnes VIIRS en indicateurs
statistiques infranationaux pour Morocco (MAR), sur
3 niveaux administratifs et sept scénarios d'analyse : activité économique,
électrification, urbanisation, inégalités spatiales, détection de changement, suivi des chocs et validation
face aux statistiques officielles.

**Les lumières nocturnes sont un indicateur indirect.** Elles mesurent une radiance ascendante vers 01h30 locale,
rien d'autre. Chaque indicateur est une *inférence*, testée dans le scénario de validation. Lire `LIMITATIONS.md`.

---

## Sources & licences
| Source | Licence |
|---|---|
| NOAA VIIRS DNB / NASA Black Marble | US Government work — attribution requested |
| geoBoundaries (gbOpen) | CC BY 4.0 |
| WorldPop | CC BY 4.0 |
| **Derived data in this repository** | **CC BY 4.0** |
| **Code in this repository** | **MIT** |

## Citation
See `CITATION.cff`.

## Maintenance
Maintainer / responsable : **National Statistical Office**
Last run / dernière exécution : `20261001T110458Z`
