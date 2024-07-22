# Polymer End of Life Approximation

Notebook to estimate end of life volumes by plastic polymer per region and year combination.

<br>

## Purpose
This notebook approximates the polymer-level volumes reaching end of life in each region within the [Global Plastics AI Policy Tool](https://global-plastics-tool.org/) by distributing waste in each fate proportionally to the size of each sector at the time of waste generation. Having attributed waste by sector, a static matrix converts to polymers which are then summed across sectors. The notebook discusses limitations of this approach and alternatives after generating the output CSV file. This is provided as a convienence for the community but is not part of the "main tool" (see [tool repository](https://github.com/SchmidtDSE/plastics-prototype)) or its publications.

<br>

## Usage
The easiest way to use this notebook is to simply download its output: [polymer_eol_approximate.csv](https://global-plastics-tool.org/data/polymer_eol_approximate.csv). This artifact is regenerated by CI / CD through this repository. The `amount` column is in million metric tonnes.

<br>

## Limitations
There are two important limitations with this software to highlight for users.

### Legacy names

We provide these values as Majority World (MW) intead of Rest of World (ROW) and North America (NA) instead of NAFTA. These labels encompass the same parts of the world regardless of labeling convention though we encourage use of MW and NA. Alternative data exports with legacy names can be found in [the tool itself](https://global-plastics-tool.org/).

### Approximated sectors

Note that this is a slight approximation. Due to lifecycle distributions, the sector ratios at time of waste generation may not be the same as if one were to project backwards in time to get the prior sector ratios which generated the waste in question. However, this provides a sufficient estimation for many use cases in which approximation is accetable. Alternatively, one may generate more precise values by simulating the lifecycle distributions and summing volumes per-polymer while projecting forward future waste. For more details on this, see the [pipeline behind the Global Plastics AI Policy Tool](https://github.com/SchmidtDSE/plastics-pipeline).

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
