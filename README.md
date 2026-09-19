# Apophis 2029 Close Approach: The Effect of Lunar & Planetary Perturbations

N-body simulation study of the historic 2029 close approach of the potentially hazardous asteroid (99942) Apophis to Earth, using `rebound` and real ephemeris data from JPL Horizons.

## Overview

On April 13, 2029, Apophis will pass within roughly 32,000 km of Earth's surface — well inside the geostationary satellite belt. This project integrates Apophis's orbit for a full year leading up to the flyby under five different N-body scenarios (from "Sun only" to "all planets"), to test how sensitive the predicted close-approach distance is to which gravitational perturbers are included.

## Key Result

Whether the Moon is accounted for matters far more than how many planets are included:

| Scenario | Minimum distance | Difference from actual (~38,378 km) |
|---|---|---|
| Sun + Earth-Moon barycenter | **41,669 km** | 3,291 km |
| Sun + barycenter + Venus + Mars | 55,367 km | 16,989 km |
| Sun only | 890,809 km | 852,431 km |
| All planets (no barycenter) | 893,543 km | 855,164 km |
| Sun + Earth | 895,787 km | 857,408 km |

Scenarios that treat the Earth-Moon system as a single point mass (ignoring the ~1.2%-of-Earth's-mass Moon) miss the real flyby distance by nearly a million kilometers — a striking demonstration of how sensitive close-encounter geometry is to small errors in initial conditions.

## Tools

- Python, [`rebound`](https://rebound.readthedocs.io) (`ias15` high-precision N-body integrator)
- [`pymcel`](https://pypi.org/project/pymcel) for JPL Horizons queries and physical constants
- NumPy, pandas, Matplotlib

## Contents

- `Apophis_2029_Close_Approach.ipynb` — full analysis: five-scenario comparison, results table, and a geocentric trajectory plot of Apophis relative to Earth and the geostationary orbit.

## Running it

Open the notebook in Jupyter or Google Colab and run all cells (the first cell installs `pymcel` and `rebound`). An internet connection is required to query JPL Horizons.

## Data Sources

- JPL Horizons / JPL Small-Body Database (state vectors for the planets, Earth-Moon barycenter, and Apophis).
- `rebound` (Rein & Liu 2012).

## Author

Javier David Nieto Mora — [github.com/javiernieto18](https://github.com/javiernieto18)
