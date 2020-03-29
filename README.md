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
\* see _zones.geojson_ for areas coordinates
