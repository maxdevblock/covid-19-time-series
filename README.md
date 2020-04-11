# covid-19-time-series
Daily updated COVID-19 global time-series in csv and json format

## Reference
COVID-\*.csv data are mirrored from <a href="https://github.com/CSSEGISandData/COVID-19">Johns Hopkins University repository</a>.

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
  - _lockdowns.csv_ is
    | Country | Place | Start date | End date | Level | lat | lon |
    | --- | --- | --- | --- | --- | --- | --- |
    | `string` | `string` | `YYYY-MM-DD` | `YYYY-MM-DD` | `string` | `float` | `float` |
    
    parsed from [Wikipedia](https://en.wikipedia.org/wiki/National_responses_to_the_2019%E2%80%9320_coronavirus_pandemic)

---
\* see _zones.geojson_ for areas coordinates
