# covid-19-time-series
Daily updated COVID-19 global time-series in csv and json format

## Reference
All csv data are mirrored from <a href="https://github.com/CSSEGISandData/COVID-19">Johns Hopkins University repository</a>.

All json data are generated from csv.

These data are used for Max Pierini <a href="https://www.maxpierini.it/ncov/covid-19.php">COVID-19 plots and forecasts website</a>.

***

## Structure 

- json
  - WORLD
    ```python
    {
      "Confirmed": {"YYYY-MM-DD": int, ...},
      "Deaths": {"YYYY-MM-DD": int, ...},
      "Recovered": {"YYYY-MM-DD": int, ...}
    }
    ```
  - WORLD EXCEPT CHINA
    ```python
    {
      "Confirmed": {"YYYY-MM-DD": int, ...},
      "Deaths": {"YYYY-MM-DD": int, ...},
      "Recovered": {"YYYY-MM-DD": int, ...}
    }
    ```
  - EUROPE (geographic area)*
    ```python
    {
      "Confirmed": {"YYYY-MM-DD": int, ...},
      "Deaths": {"YYYY-MM-DD": int, ...},
      "Recovered": {"YYYY-MM-DD": int, ...}
    }
    ```
   - AFRICA (continent)*
    ```python
    {
      "Confirmed": {"YYYY-MM-DD": int, ...},
      "Deaths": {"YYYY-MM-DD": int, ...},
      "Recovered": {"YYYY-MM-DD": int, ...}
    }
    ```
  - COUNTRIES
    ```python
    {
      "Country Name":
      {
        "Confirmed": {"YYYY-MM-DD": int, ...},
        "Deaths": {"YYYY-MM-DD": int, ...},
        "Recovered": {"YYYY-MM-DD": int, ...}
      },
      ...
    }
    ```
  - DETAILS (smaller areas: provinces, states, where available)
    ```python
    {
      "Area Name":
      {
        "Confirmed": {"YYYY-MM-DD": int, ...},
        "Deaths": {"YYYY-MM-DD": int, ...},
        "Recovered": {"YYYY-MM-DD": int, ...}
      },
      ...
    }
    ```
- csv
  - all csv are:
    | Province/State | Country/Region | Lat | Lon | M/D/YY |
    | --- | --- | --- | --- | --- |
    | `string` | `string` | `float` | `float` | `int` |

---
\* EUROPE is calculated as: all points within the following area (`[lon, lat]`):
```json
[
    [-31.640625000000004, 65.22621580443068],
    [-14.414062500000002, 34.61488236933614],
    [6.679687500000001, 38.072307761177434],
    [11.370849609375002, 37.16119853011621],
    [17.797851562500004, 33.397115779277804],
    [28.125000000000004, 34.59920735944525],
    [25.8837890625, 39.67474804022493],
    [36.51855468750001, 44.98072199499916],
    [40.34179687500001, 49.72470047954782],
    [28.125000000000004, 60.30413916215259],
    [33.31054687500001, 71.38259358177613],
    [-9.492187500000002, 71.68874457897826],
    [-31.640625000000004, 65.22621580443068]
]
```
\* AFRICA is calculated as: all points within the following area (`[lon, lat]`):
```json
[
    [-5.822753906250001, 35.8982639097007],
    [-27.773437500000004, 21.622900762503807],
    [-25.400390625, 9.284004953723443],
    [17.050781250000004, -40.36817383631919],
    [52.82226562500001, -37.07827065362777],
    [65.56640625000001, -7.003095280765394],
    [50.80078125, 12.648184681156543],
    [43.76953125, 11.703272060234015],
    [33.31054687500001, 32.625219206745705],
    [13.095703125, 34.74557902553385],
    [10.371093750000002, 38.135341501071856],
    [-5.822753906250001, 35.8982639097007],
]
```
