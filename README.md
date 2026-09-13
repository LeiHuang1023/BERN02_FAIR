# BERN02_FAIR
The coursework of FAIR Principles and Reproducible Workflows
# A Reproducible Workflow with Simulated Data

Author: Lei Huang

## Overview

This project demonstrates a reproducible workflow using R and Quarto.
It generates 100 simulated observations, calculates summary statistics,
and creates a scatter plot.

The report includes the data-generation method, executable code,
results, software requirements, a risk assessment, and a discussion
of FAIR principles.

## Data

The data are generated within analysis.qmd using:

y = 2 + 3x + error

- x follows a uniform distribution between 0 and 10.
- The error follows a normal distribution with mean 0 and standard deviation 2.
- The random seed is 123.
- Each row represents one simulated observation.
- Both x and y are numeric and have no physical units.

The data are simulated and do not represent real-world observations.
No external dataset is required.

## Project files

| File | Purpose |
|---|---|
| analysis.qmd | Source document containing explanations and R code |
| analysis.html | Rendered report |
| simulated_data.csv | Generated data with columns x and y |
| renv.lock | Recorded R package versions |
| .Rprofile | Activates the project environment when R starts |
| renv/activate.R | Starts renv for the project |
| renv/settings.json | Project settings for renv |
| README.md | Project description and running instructions |

The RStudio project file has the extension .Rproj.

## Requirements

The workflow was tested on Windows with:

- R 4.3.3
- Quarto 1.5.57
- R package versions recorded in renv.lock

RStudio provides a convenient interface for opening the project
and rendering the report.

R and Quarto must be installed separately.
An internet connection is normally required to restore packages.

## How to reproduce the workflow

1. Download and extract the complete repository, or clone it with Git.
2. Locate this exercise folder and open its .Rproj file in RStudio.
3. Allow renv to install its recorded version if prompted.
4. Run the following command in the R Console:

```r
renv::restore()
```

5. Open analysis.qmd and click Render.

Alternatively, after restoring the environment, run this command
in a terminal from the exercise folder:

```bash
quarto render analysis.qmd
```

Rendering runs the simulation and analysis from the source document.
It generates analysis.html and writes simulated_data.csv.
An existing simulated_data.csv will be overwritten.

## Viewing the results

To read the report without running R, download analysis.html
and open it in a web browser.

The report contains the first six observations, summary statistics,
and a scatter plot. The red line shows the mean relationship used
to generate the data; it is not fitted to the observations.

## Reproducibility and limitations

The fixed seed and recorded software environment support reproducibility.
The renv lockfile fixes R package versions but does not install R or Quarto.

This workflow has only been tested on Windows.
Other operating systems may require additional setup.
See the report for the version-pinning rationale, risk assessment,
and discussion of FAIR principles.
