# Polymer End of Life Approximation

Notebook to estimate end of life volumes by plastic polymer per region and year combination.

<br>

## Purpose
This notebook approximates the amount of polymers reaching end of life in each region within the [Global Plastics AI Policy Tool](https://global-plastics-tool.org/) by distributing waste in each fate proportionally to the size of each sector at the time of waste generation. Having attributed waste by sector, a static matrix converts to polymers which are then summed across sectors. The notebook discusses limitations of this approach and alternatives after generating the output CSV file. This is provided as a convienence for the community but is not part of the central tool or its publications.

<br>

## Usage
The easiest way to use this notebook is to simply download its output by downloading the output [polymer_eol_approximate.csv](https://global-plastics-tool.org/data/polymer_eol_approximate.csv). This artifact is regenerated by CI / CD through this repository. The `amount` column is in million metric tonnes.

<br>

## Limitations
There are two important limitations with this software to highlight for users.

### Approximated sectors

Note that this is an approximation in that, due to lifecycle distributions, the current sector ratios may not be the same as the sector ratios if one were to project backwards in time to get the prior sector ratios which generated the waste in question. However, this provides an estimation for many use cases in which approximation is accetable. Even so, one may generate more precise values but simulating the lifecycle distributions and summing per-polymer while projecting forward future waste. For more details on this, see the [pipeline behind the Global Plastics AI Policy Tool](https://github.com/SchmidtDSE/plastics-pipeline).

### Legacy names

For historic compatibility, we provide these values as Rest of World (ROW) intead of Majority World (MW) and NAFTA instead of North America (NA). These labels encompass the same parts of the world in either labeling convention and we encourage use of MW and NA. However, we are leaving the legacy names in place for now to maintain compatibility for those relying on our outputs. Alternative data exports with updated names can be found in [the tool itself](https://global-plastics-tool.org/).

<br>

## Local environment
For those looking to execute this locally, simply install python requirements with `pip install -r requirements.txt`. Users may also consider creating a [virtual environment](https://the-hitchhikers-guide-to-packaging.readthedocs.io/en/latest/virtualenv.html).

<br>

## Development
The notebook can be run by executing `$ jupyter notebook` while in this repository's directory and navigating to the `PolymerEndLifeApproximation` notebook.

<br>

## Contributing
No explicit development standards are imposed at this time.

<br>

## Deployment
Merging to the `main` branch will cause the artifact to be rebuilt and deployed to production where the file can be downloaded as [polymer_eol_approximate.csv](https://global-plastics-tool.org/data/polymer_eol_approximate.csv).

<br>

## License
This code is released under the [BSD 3-Clause License](https://opensource.org/license/bsd-3-clause). See LICENSE.md for more details. Note that the data themselves are subject to [CC-BY-NC](https://creativecommons.org/licenses/by-nc/4.0/).
