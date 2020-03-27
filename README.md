# covid-19-time-series
Daily updated COVID-19 global time-series in csv and json format

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
  - COUNTRIES
    ```python
    {
      "Country Name":
      {
        "Confirmed": {"YYYY-MM-DD": number, ...},
        "Deaths": {"YYYY-MM-DD": number, ...},
        "Recovered": {"YYYY-MM-DD": number, ...}
      },
      ...
    }
    ```
  - DETAILS (smaller areas: provinces, states, where available)
    ```python
    {
      "Area Name":
      {
        "Confirmed": {"YYYY-MM-DD": number, ...},
        "Deaths": {"YYYY-MM-DD": number, ...},
        "Recovered": {"YYYY-MM-DD": number, ...}
      },
      ...
    }
    ```
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
