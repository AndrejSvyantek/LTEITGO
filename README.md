# LTE IT GO

**L**ow **T**emperature **E**xotherm **I**n**T**eractive **G**raphical **O**bservatory.

LTE IT GO consistes of a HTML file for extracting lethal temperature exotherms from differential thermal analysis (DTA) of dormant plant buds to monitor cold hardiness. Calculations run in the browser.

## Steps to Use
**Download.** Save [`LTEITGO_v01.01.01.html`](LTEITGO_v01.01.01.html) and open it in a browser. It works offline.

## Load data

1. **Synthetic demo, is present inside the app.** On **Data & mapping**, press **Load the synthetic demo**. The temperatures, treatments (`Control`, `TrtA`, `TrtB`), and blocks are invented so maps, statistics, and plots can be tried. They are not experimental results. Every cell on trays A–C is filled. A few cells have fewer exotherms than a full sample, so they are flagged and left out of a sigmoid fit.
2. **Use Your own file.** Drop a CSV, TSV, or semicolon-delimited export. Several files can be open at once, each with its own column mapping.

Required columns: collection event, freezer run, tray, cell, and the LTE temperature in °C. Optional columns: year, treatment, and block. The Data tab guesses the mapping and marks guesses **auto**. Change any guess before you trust the later tabs. Any column you do not map to a role can still be used as a factor.

## Privacy

Opening the downloaded file does not need a network connection.

Do not commit unpublished trial files to a public fork of this repository.

## Estimators

There are three plotting positions and three estimators to arrive at your LTE values.

Plotting positions 
- halfway ranks
- expected ranks
- min-to-max ranks

Estimators
- linear interpolation of the cumulative curve
- two-parameter logistic
- four-parameter logistic

Cells that cannot be fitted fall back to interpolation and are flagged.
