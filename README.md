# covid-19-time-series
Daily updated COVID-19 global time-series in csv and json format

## Reference
csv data are mirrored from <a href="https://github.com/CSSEGISandData/COVID-19">Johns Hopkins University repository</a> and <a href="https://github.com/AuraVisionLabs/covid19-lockdown-tracker">AuraVisionLabs</a>.

All json data are generated from csv.

These data are used for Max Pierini <a href="https://www.maxpierini.it/ncov/">COVID-19 maps, plots and forecasts website</a>.

***

## Structure 

- json
  - WORLD, WORLD_EXCEPT_CHINA, ITALY, EUROPE*, AFRICA*, NORTH_AMERICA*, SOUTH_AMERICA*, ASIA*, OCEANIA*
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
  - all COVID-* csv are:
    | Province/State | Country/Region | Lat | Lon | M/D/YY |
    | --- | --- | --- | --- | --- |
    | `string` | `string` | `float` | `float` | `int` |
  - _lockdowns.csv_ if the same of <a href="https://github.com/AuraVisionLabs/covid19-lockdown-tracker">AuraVisionLabs</a> added `lat` and `lon` coordinates (`float`)

---
\* see _zones.geojson_ for areas coordinates
