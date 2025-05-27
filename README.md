# SpatialProject_Legepladser
Spatial Analytics project investigating the equity of playgrounds in Denmark across municipalities.


## Table of Contents
1. [Project Description](#description)
2. [Project Structure](#structure)
3. [Installation](#installation)
4. [Data Source](#data)
5. [Usage](#usage)
6. [References](#references)

## Project Description
This project uses walking and cycling isochrones as well as municipality level income and child population data to analyse 
the spatial equity of playgrounds in Denmark. The project is divided into two main parts:
1. A script with the data preprocessing and initial plotting - Data_Processing.Rmd
2. A script with the spatial analysis and final plotting - Spatial_Analysis.Rmd

Statstics using the isochrone results and income and population data are calculated and plotted in the analysis script, to 
examine playground equity. The results are used in the written project associated with this script. The outputs of the script are 
saved as a csv file as well as through many plots. Each section of results is saved into a subfolder e.g. cycling stats and plots are 
in the cycling_stats subfolder folder.

## Repository Structure
```
SpatialProject_Legepladser/
│ 
├── data/
│   ├── Aarhus_legepladser.geojson
│   ├── Frederiksberg_legepladser.geojson
│   ├── København_legepladser.geojson
│   ├── RingkobingSkjern_legepladser.geojson
│   ├── Silkeborg_legepladser.geojson
│   ├── Vesthimmerland_legepladser.geojson
│   ├── income.csv
│   ├── Child014_Population.csv
│   ├── playgrounds_clean.rds
│   ├── muni_income.rds
│   ├── muni_population.rds
│   └── gadm
│         └── gadm41_DNK_2_pk.rds
│ 
├── Spatial_Analysis.Rmd
│ 
├── Data_Processing.Rmd
│
├── output/
│   ├── comparison_stats
│          ├── coverage_comparison.png
│          ├── pct_increase_coverage.png
│          ├── ...
│          └── joined_covered.csv
│   ├── cycling_stats
│   ├── playground_stats
│   └── walking_stats
│
└── README.md
```

## Installation
To get started with this project, follow these steps:

1. change directories into the  projects repository: /Spatial_ANalysis_Legepladser
   - If you cloned the repository, use `cd SpatialProject_Legepladser`
   - If you downloaded the repository as a zip file, extract it and then use `cd` to navigate to the extracted folder.
2. Ensure all packages required are installed - see Usage section in the ReadMe file.
3. Run the Data_Processing.Rmd script to preprocess the data and create the necessary files for the analysis.
   - Open the Data_Processing.Rmd file in RStudio or any R Markdown compatible editor.
   - Click on "Knit" to run the script and generate the output files.
   - This will create the `playgrounds_clean.rds`, `muni_income.rds`, and `muni_population.rds` files in the `data/` directory.
4. Run the Spatial_Analysis.Rmd script to perform the spatial analysis and generate the final outputs.
   - Open the Spatial_Analysis.Rmd file in RStudio or any R Markdown compatible editor.
   - Click on "Knit" to run the script and generate the output files.
   - This will create various plots and statistics in the `output/` directory.

## Data Source
The geojson data files are from OpenData.dk. The income and child population data are from Statistics Denmark. 
The isochrone data is from the OpenRouteService API, which provides walking and cycling isochrones for the playgrounds in the 
municipalities of Denmark. See the `data/` directory for the raw data files used in this project.
The gadm41_DNK_2_pk.rds file is from the GADM database, which provides administrative boundaries for Denmark.
The references for these data sources can be found below.

## Usage
The code was run in the desktop version of R (v. 4.3.1) and RStudio (v. 2024.12.1+563). The package dependencies can be seen 
in the table below

| Package    | Version | Acknowledgements                                                  |
|------------|---------|-------------------------------------------------------------------|
| ggplot2    | 3.5.1   | Wickham H (2016)                                                  |
| dplyr      | 1.1.3   | Wickham H, François R, Henry L, Müller K, Vaughan D (2023)        |
| tidyr      | 1.3.0   | Wickham H, Vaughan D, Girlich M (2023)                            |
| sf         | 1.0.19  | Pebesma E, Bivand R (2023); Pebesma E (2018)                      |
| leaflet    | 2.2.2   | Cheng J, Schloerke B, Karambelkar B, Xie Y (2024)                 |
| geodata    | 0.6.2   | Hijmans RJ, Barbosa M, Ghosh A, Mandel A (2024)                   |
| terra      | 1.8.15  | Hijmans R (2025)                                                  |
| units      | 0.8.5   | Pebesma E, Mailund T, Hiebert J (2016)                            |
| mapboxapi  | 0.6.2   | Walker K (2024)                                                   |

## References
Cheng J, Schloerke B, Karambelkar B, Xie Y (2024). _leaflet: Create Interactive Web Maps with the JavaScript, 'Leaflet' Library_. R package version 2.2.2, https://CRAN.R-project.org/package=leaflet

Datopian. (n.d.-a). Playgrounds in Aarhus - dataset. https://www.opendata.dk/city-of-aarhus/legepladser

Datopian. (n.d.-b). Playgrounds - dataset. https://www.opendata.dk/city-of-copenhagen/legepladser1

Datopian. (n.d.-c). Playgrounds Vesthimmerland - Dataset. https://www.opendata.dk/vesthimmerlands-kommune/legepladser-vesthimmerland

Datopian. (n.d.-d). 10.40.02. Municipal playgrounds - Dataset. https://www.opendata.dk/ringkobing-skjern/10-40-02-kommunale-legepladser

Datopian. (n.d.-e). Outdoor offer - Dataset. https://www.opendata.dk/city-of-frederiksberg/friluftstilbud_frederiksberg

Datopian. (n.d.-f). Facilities and urban space in Silkeborg Municipality - Dataset. https://www.opendata.dk/silkeborg-kommune/silkeborg-faciliteter

Hijmans RJ, Barbosa M, Ghosh A, Mandel A (2024). _geodata: Download Geographic Data_. R package version 0.6-2, https://CRAN.R-project.org/package=geodata

Hijmans R (2025). _terra: Spatial Data Analysis_. R package version 1.8-15, https://CRAN.R-project.org/package=terra

Hijmans R (2025). _raster: Geographic Data Analysis and Modeling_. R package version 3.6-31, https://CRAN.R-project.org/package=raster

Pebesma E, Bivand R (2023). _Spatial Data Science: With applications in R_. Chapman and Hall/CRC.  R package version 1.0.19, doi:10.1201/9780429459016, https://doi.org/10.1201/9780429459016, https://r-spatial.org/book/

Pebesma E (2018). “Simple Features for R: Standardized Support for Spatial Vector Data.” _The R Journal_, *10*(1), 439-446.  R package version 1.0.19, doi:10.32614/RJ-2018-009, https://doi.org/10.32614/RJ-2018-009, https://doi.org/10.32614/RJ-2018-009
  
Pebesma E, Mailund T, Hiebert J (2016). “Measurement Units in R.” _R Journal_, *8*(2), 486-494.  R package version 0.8.5, doi:10.32614/RJ-2016-061, https://doi.org/10.32614/RJ-2016-061

Posit team (2025). RStudio: Integrated Development Environment for R. Posit Software, PBC, Boston, MA. URL
  http://www.posit.co/.

Statistikbanken. (n.d. -a). https://www.statistikbanken.dk/INDKP101, municipalities, total sex, average income for all persons (kr.),  2023, Disposable income

Statistikbanken. (n.d. -b). https://www.statbank.dk/20021 , municipalities, total sexes, total age, total martial status, 2025Q1

Wickham H (2016). _ggplot2: Elegant Graphics for Data Analysis_. Springer-Verlag New York. ISBN 978-3-319-24277-4,  R package version 3.5.1, https://ggplot2.tidyverse.org

Wickham H, François R, Henry L, Müller K, Vaughan D (2023). _dplyr: A Grammar of Data Manipulation_. R package version 1.1.3, https://CRAN.R-project.org/package=dplyr

Wickham H, Vaughan D, Girlich M (2023). _tidyr: Tidy Messy Data_. R package version 1.3.0, https://CRAN.R-project.org/package=tidyr
  
Wickham H, Vaughan D, Girlich M (2023). _tidyr: Tidy Messy Data_. R package version 1.3.0, https://CRAN.R-project.org/package=tidyr

​​Walker K (2024). _mapboxapi: R Interface to 'Mapbox' Web Services_. R package version 0.6.2, https://CRAN.R-project.org/package=mapboxapi

