# chilean-ministers
**Data Set on Chilean Ministers (1990-2014)**

[![Version](https://img.shields.io/badge/version-v3.2.2-blue.svg)](CHANGELOG.md) [![Project Status: Inactive – The project has reached a stable, usable state but is no longer being actively developed; support/maintenance will be provided as time allows.](https://www.repostatus.org/badges/latest/inactive.svg)](STATUS.md) [![GitHub issues](https://img.shields.io/github/issues/bgonzalezbustamante/chilean-ministers.svg)](https://github.com/bgonzalezbustamante/chilean-ministers/issues/) [![GitHub issues-closed](https://img.shields.io/github/issues-closed/bgonzalezbustamante/chilean-ministers.svg)](https://github.com/bgonzalezbustamante/chilean-ministers/issues?q=is%3Aissue+is%3Aclosed) [![DOI](https://zenodo.org/badge/432335926.svg)](https://zenodo.org/badge/latestdoi/432335926) [![License](https://img.shields.io/badge/license-CC--BY--4.0-black)](LICENSE.md) [![R](https://img.shields.io/badge/made%20with-R%20v4.1.0-1f425f.svg)](https://cran.r-project.org/) [![Latex](https://img.shields.io/badge/made%20with-LaTeX-1f425f.svg)](https://www.latex-project.org/)

## Overview

This repository contains a data set on Chilean ministers between 1990 and 2014 in Comma-Separated Values `CSV` format with Unicode encoding `UTF-8`. The data collection was carried out based on official sources such as archives of Congress and ministries, the National Library, and press archives. Part of this data set has been used in the following articles and book chapter:

- González-Bustamante, B. (2020). The Politics‐Administration Dichotomy: A Case Study of the Chilean Executive during the Democratic Post‐Transition. *Bulletin of Latin American Research, 39*(5), 582-597. DOI: [10.1111/blar.13044](https://doi.org/10.1111/blar.13044)

- González-Bustamante, B., & Olivares, A. (2018). La élite política gubernamental en Chile: Supervivencia de ministros. In A. Codato and F. Espinoza (eds.), *Las Élites en las Américas: Diferentes Perspectivas*. Curitiba: Editora Universidade Federal do Paraná. URL: [https://www.researchgate.net](https://www.researchgate.net/publication/325699783_Elites_en_las_Americas_diferentes_perspectivas_Elites_in_the_Americas_Different_Perspectives)

- González-Bustamante, B., & Olivares, A. (2016). Cambios de gabinete y supervivencia de los ministros en Chile durante los gobiernos de la Concertación (1990-2010). *Colombia Internacional*, 87, 81-108. DOI: [10.7440/colombiaint87.2016.04](https://doi.org/10.7440/colombiaint87.2016.04)

Download the [`BibTeX`](refs/BIB-Ministers.bib), which includes the bibliographical data of this repository.

## Metadata and Preservation

This data set is stored with version control on a GitHub repository. Furthermore, a Digital Object Identifier is provided by Zenodo. The structure of the repository is detailed below.

``` r
chilean-ministers
|-- .gitignore
|-- CHANGELOG.md
|-- chilean-ministers.Rproj
|-- CITATION.cff
|-- CODE_OF_CONDUCT.md
|-- LICENSE.md
|-- README.md
|-- STATUS.md
|-- code
    |-- eda_ministers.R
|-- data
    |-- tidy
        |-- Chilean_cabinets_1990_2014.csv
|-- demo
    |-- eda_ministers.md
    |-- eda_ministers.Rmd
    |-- eda_ministers_files
        |-- figure-gfm
            |-- plot1-1.png
            |-- plot2-1.png
            |-- plot2-2.png
            |-- plot3-1.png
            |-- plot4-1.png
|-- docs
    |-- codebook_ministers.pdf
    |-- codebook_ministers.synctex.gz
    |-- codebook_ministers.tex
|-- refs
    |-- BIB-Ministers.bib
```

8 directories and 21 files.

In addition, this `README` file in Markdown `MD` format provides specific information to ensure the reusability of the data.
## Storage and Backup

The GitHub repository has controlled access with Two-Factor Authentication `2FA` with two physical USB security devices (Bastián González-Bustamante, [ORCID iD 0000-0003-1510-6820](https://orcid.org/0000-0003-1510-6820)) and a mobile application (Alejandro Olivares, [ORCID iD 0000-0001-6934-2437](https://orcid.org/0000-0001-6934-2437)). USB devices and the mobile application issue one-time passwords to generate a cryptographic authentication `FIDO2` and `U2F`.

Moreover, the repository is backed up on Hierarchical File Server `HFS` for recovery in case of incidents. This backup is located on the University of Oxford hub connected to `Code42` Cloud Backup encrypted with `256-bit AES`. The backup is performed with every change on GitHub and receives weekly light maintenance and a deep one every month. This backup will be secured until May 2024. An extension of this period will be evaluated on budget availability.

## Getting Started

### Software

We used `R` version 4.1.0 (2021-05-18) -- "Camp Pontanezen" and the following packages: `DataExplorer` v0.8.2, `knitr` v1.37, `rmarkdown` v2.11, and `tidyverse` v1.3.1.

We recommend that users import the data directly using the code below or, if they wish, run exploratory data analysis code from the root directory using the `R` project `chilean-ministers.Rproj`.

### Import Data

#### R Code

``` r
## GitHub Repository
github_1 <- "https://raw.githubusercontent.com/"
github_2 <- "bgonzalezbustamante/chilean-ministers/main/data/tidy/"

## Chilean Ministers Data
chilean_ministers <- read.csv(paste(github_1, github_2, "Chilean_cabinets_1990_2014.csv", sep = ""),
                              header = T, sep = ",", encoding = "UTF-8")
```
#### Python Code

``` python
import pandas as pd

## GitHub Repository
github_1 = "https://raw.githubusercontent.com/"
github_2 = "bgonzalezbustamante/chilean-ministers/main/data/tidy/"

## Chilean Ministers Data
url = github_1 + github_2 + "Chilean_cabinets_1990_2014.csv"
df = pd.read_csv(url, index_col=0)
```

### Replication Instructions

Folder `code` contains the exploratory data analysis in `R` format.

Folder `demo` contains the exploratory data analysis in `RMD` and `MD` formats: [`eda_ministers.md`](demo/eda_ministers.md).

The files will be overwritten if you run the `R` script contained in `eda_ministers.Rmd`.

### Codebook

The file `Chilean_cabinets_1990_2014.csv` in `data/tidy` subfolder is the data set on Chilean ministers between 1990 and 2014. This set contains 232 observations. The codebook is also available in [`PDF`](docs/codebook_ministers.pdf).

- `id`. Unique ID for each minister-portfolio observation.

- `country`. Country name.

- `name`. Officeholder name.

- `sex`. Officeholder sex.[^1]

- `age`. Officeholder age when was appointed.

- `president`. President in office.

- `start_president`. Start date of presidential term in the format `YYYY-MM-DD`.

- `end_president`. End date of presidential term in the format `YYYY-MM-DD`.

- `ministry`. Portfolio name.[^2]

- `start_minister`. Officeholder start date in the format `YYYY-MM-DD`.

- `end_minister`. Officeholder end date in the format `YYYY-MM-DD`.

- `non_party`. A dummy variable indicating whether the minister is non-partisan.

- `president_party`. A dummy variable indicating whether the minister is a member of the president's party.

- `economist`. A dummy variable indicating whether the minister is an economist.

- `lawyer`. A dummy variable indicating whether the minister is a lawyer.

- `inner_circle`. A dummy variable indicating whether the minister is a member of the president's inner circle.

- `party_leader`. A dummy variable indicating whether the minister is a party leader.

- `exp_executive`. A dummy variable indicating whether the minister is a former cabinet member.

- `exp_congress`. A dummy variable indicating whether the minister was a former Congress member.

- `exp_ngo`. A dummy variable indicating whether the minister is a former NGOs member.

- `exp_thinktanks`. A dummy variable indicating whether the minister is a former think tank member.

- `exp_business`. A dummy variable indicating whether the minister has a previous trajectory in business.

- `political_kinship`. A dummy variable indicating whether the minister has political kinship.

A number of other variables can be calculated with aggregate data from different sources considering the appointment dates and departure of officeholders. In addition, data from González-Bustamante and Olivares (2022)[^3] can be used to compare and obtain some variables from undersecretaries.

## License

This data set is released under a [Creative Commons Attribution 4.0 International license (CC BY 4.0)](LICENSE.md). This open-access license allows the data to be shared, reused, adapted as long as appropriate acknowledgement is given.

## Contribute

Contributions are entirely welcome. You just need to [open an issue](https://github.com/bgonzalezbustamante/chilean-ministers/issues/new) with your comment or idea.

For more substantial contributions, please fork this repository and make changes. Pull requests are also welcome.

Please read our [code of conduct](CODE_OF_CONDUCT.md) first. Minor contributions will be acknowledged, and significant ones will be considered on our contributor roles taxonomy.

## Citation

González-Bustamante, B., & Olivares, A. (2022). Data Set on Chilean Ministers (1990-2014) (Version 3.2.2 -- Old Mode) [Data set]. DOI: [10.5281/zenodo.5744536](https://doi.org/10.5281/zenodo.5744536)

## Authors

Bastián González-Bustamante \
bastian.gonzalezbustamante@politics.ox.ac.uk \
[ORCID iD 0000-0003-1510-6820](https://orcid.org/0000-0003-1510-6820) \
https://bgonzalezbustamante.com

Alejandro Olivares \
alejandro.olivares@uct.cl \
[ORCID iD 0000-0001-6934-2437](https://orcid.org/0000-0001-6934-2437)

## CRediT - Contributor Roles Taxonomy

Bastián González-Bustamante ([ORCID iD 0000-0003-1510-6820](https://orcid.org/0000-0003-1510-6820)): Conceptualisation, data curation, formal analysis, funding acquisition, methodology, project administration, resources, software, validation, and visualisation.

Alejandro Olivares ([ORCID iD 0000-0001-6934-2437](https://orcid.org/0000-0001-6934-2437)): Conceptualisation, funding acquisition, investigation, methodology, project administration, resources, and validation.

### Latest Revision

[March 14, 2022](CHANGELOG.md).

[^1]: In version 2.3.0 (Bold Fog), we have corrected the sex of one misclassified observation of the Ricardo Lagos government. This implies a slight drop in the presence of women in the cabinet from 24.53% to 22.64% and subtle differences in coefficients of the models in some of our previous publications.
[^2]: The labels `SEGEGOB`, `SEGPRES`, and `SERNAM` correspond to the following ministries: *Secretaría General de Gobierno*, *Secretaría General de la Presidencia*, and *Servicio Nacional de la Mujer*. In addition, `CORFO` is an acronym for *Corporación de Fomento de la Producción*.
[^3]: González-Bustamante, B., & Olivares, A. (2022). Data Set on Chilean Undersecretaries (1990-2022) (Version 2.0.0 -- Sparkling Shape) [Data set]. DOI: [10.5281/zenodo.5715384](https://doi.org/10.5281/zenodo.5715384)
