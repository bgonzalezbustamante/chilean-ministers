# chilean-ministers
**Data Set on Chilean Undersecretaries (1990-2014)**

[![Version](https://img.shields.io/badge/version-v2.1.0-blue.svg)](CHANGELOG.md) [![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](STATUS.md) [![GitHub issues](https://img.shields.io/github/issues/bgonzalezbustamante/chilean-ministers.svg)](https://github.com/bgonzalezbustamante/chilean-ministers/issues/) [![GitHub issues-closed](https://img.shields.io/github/issues-closed/bgonzalezbustamante/chilean-ministers.svg)](https://github.com/bgonzalezbustamante/chilean-ministers/issues?q=is%3Aissue+is%3Aclosed) [![DOI](https://zenodo.org/badge/428418754.svg)](https://zenodo.org/badge/latestdoi/428418754) [![License](https://img.shields.io/badge/license-CC--BY--4.0-black)](LICENSE.md) [![R](https://img.shields.io/badge/made%20with-R%20v4.1.0-1f425f.svg)](https://cran.r-project.org/)

## Overview

This repository contains a data set on Chilean ministers between 1990 and 2014 in Comma-Separated Values (CSV) format with Unicode encoding (UTF-8). The data collection was carried out based on official sources such as archives of Congress and ministers, the National Library, and press archives. Part of this data has been used in the following articles and book chapter:

- González-Bustamante, B. (2020). The Politics‐Administration Dichotomy: A Case Study of the Chilean Executive during the Democratic Post‐Transition. *Bulletin of Latin American Research, 39*(5), 582-597. DOI: [10.1111/blar.13044](https://doi.org/10.1111/blar.13044)

- González-Bustamante, B., Olivares, A. (2018). La élite política gubernamental en Chile: Supervivencia de ministros. In A. Codato and F. Espinoza (eds.), *Las Élites en las Américas: Diferentes Perspectivas*. Curitiba: Editora Universidade Federal do Paraná. URL: [https://www.researchgate.net](https://www.researchgate.net/publication/325699783_Elites_en_las_Americas_diferentes_perspectivas_Elites_in_the_Americas_Different_Perspectives)

- González-Bustamante, B., Olivares, A. (2016). Cambios de gabinete y supervivencia de los ministros en Chile durante los gobiernos de la Concertación (1990-2010). Colombia Internacional, 87, 81-108. [10.7440/colombiaint87.2016.04](https://doi.org/10.7440/colombiaint87.2016.04)

## Metadata and Preservation

This data is stored with version control on a GitHub repository. Furthermore, a Digital Object Identifier is provided by Zenodo. The structure of the repository is detailed below.

*chilean-ministers* \
|-- .gitignore \
|-- CHANGELOG.md \
|-- chilean-ministers.Rproj \
|-- CITATION.cff \
|-- LICENSE.md \
|-- README.md \
|-- STATUS.md \
|-- code \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|-- eda_ministers_files \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|-- figure-gfm \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|-- plot1-1.png \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|-- plot2-1.png \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|-- plot3-1.png \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|-- eda_ministers.md \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|-- eda_ministers.Rmd \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|-- potential_inconsistencies.md \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|-- potential_inconsistencies.Rmd \
|-- data \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|-- chl_ministers.csv 

4 directories and 15 files.

In addition, this README file in Markdown (MD) format provides specific information to ensure the reusability of the data.

## Store and Backup

The GitHub repository has controlled access with Two-Factor Authentication (2FA) with two physical USB security devices (Bastián González-Bustamante, [ORCID iD 0000-0003-1510-6820](https://orcid.org/0000-0003-1510-6820)) and a mobile application (Alejandro Olivares, [ORCID iD 0000-0001-6934-2437](https://orcid.org/0000-0001-6934-2437)). USB devices and the mobile application issue one-time passwords to generate a cryptographic authentication FIDO2 and U2F.

Moreover, the repository is backed up on Hierarchical File Server (HFS) for recovery in case of incidents. This backup is located on the University of Oxford hub connected to Code42 Cloud Backup encrypted with 256-bit AES. The backup is performed with every release on GitHub and receives weekly light maintenance and a deep one every month. This backup will be secured until May 2024. An extension of this period will be evaluated on budget availability.

## Getting Started

### Software

We use R version 4.1.0 (2021-05-18) -- "Camp Pontanezen".

Required R libraries are: "DataExplorer" and "ggplot2".

We recommend that users run exploratory data analysis code from the root directory using the R project "chilean-ministers.Rproj".

### Replication Instructions

The folder "code" contains the exploratory data analysis in R, RMD and MD formats ([**eda_ministers.md**](code/eda_ministers.md)).

The files will be overwritten if you run the R script contained in "eda_ministers.Rmd".

### Codebook

The file "chl_ministers.csv" is the data set on Chilean undersecretaries between 1990 and 2014. This set contains 232 observations.

- **id**. Unique ID for each minister-portfolio observation.

- **country**. Country name.

- **name**. Officeholder name.

- **sex**. Officeholder sex.

- **age**. Officeholder age when was appointed.

- **president**. President in office.

- **start_president**. Start date of presidential term.

- **end_president**. End date of presidential term.

- **ministry**. Portfolio name.

- **start_minister**. Officeholder start date.

- **end_minister**. Officeholder end date.

- **non_party**. Dummy for non-partisan ministers.

- **president_party**. Dummy for ministers of the president’s party.

- **economist**. Dummy for economist ministers.

- **lawyer**. Dummy for lawyer ministers.

- **inner_circle**. Dummy for members of the president’s inner circle.

- **party_leader**. Dummy for party leaders.

- **exp_executive**. Dummy for former cabinet members.

- **exp_congress**. Dummy for former Congress members.

- **exp_ngo**. Dummy for former NGOs members.

- **exp_thinktanks**. Dummy for former think tanks members.

- **exp_business**. Dummy for trajectories in business.

- **political_kinship**. Dummy for ministers with political kinship.

A number of other variables can be calculated with aggregate data from different sources considering the appointment dates and departure of officeholders. In addition, data from González-Bustamante and Olivares (2021)[^1] can be used to compare and obtain some variables from cabinet members.

## License

This data is released under a [Creative Commons Attribution 4.0 International license (CC BY 4.0)](LICENSE.md). This open-access license allows the data to be shared, reused, adapted as long as appropriate acknowledgement is given.

## Citation

González-Bustamante, B., & Olivares, A. (2021). Data Set on Chilean Ministers (1990-2014) (Version 2.1.0 -- Long Lab) [Data set].

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

[November 27, 2021](CHANGELOG.md).

[^1]: González-Bustamante, B., & Olivares, A. (2021). Data Set on Chilean Undersecretaries (1990-2014) (Version 1.3.1 -- Fragrant Disk) [Data set]. DOI: [10.5281/zenodo.5715384](https://doi.org/10.5281/zenodo.5715384)
