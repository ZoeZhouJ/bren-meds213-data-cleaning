# Cleaning the shorebird survey data

## Objectives

The goal of this repository is to provide a well-documented, and cleaned version of the Arctic Shorebird Demographics Network (ASDN) data set, specifically focusing on the cover values for shorebird surveys.

## DATA & FILE OVERVIEW

### 1. File List:

-   `eds213_data_cleaning_assign_ZHOU.qmd` and associated files and html for easier viewing: Contains the code used to clean data and generate the final cleaned data set.
-   `data-cleaning_empty.qmd`: A template for in-class data cleaning.
-   `data-cleaning_zhou.qmd`: Code for cleaning the shorebird survey data and snow cover column in snow survey table.
-   `data/raw/01_ASDN_Readme.txt`: Contains metadata information about the original data set.
-   `data/raw/ASDN_Daily_species.csv`: Data set containing shorebird species information.
-   `data/raw/ASDN_Snow_survey.csv`: Data set containing original snow survey data.
-   `data/processed/all_cover_fixed_ZHOU.csv`: The final cleaned data set with cover values for shorebird surveys. -`data/processed/snow_cover.csv`: The final cleaned snow survey data set. -`data/processed/species_precense.csv`: The shorebird species presence data set.
-   `renv/`: R package management directory for reproducibility.


### 2. Relationship Between Files

```         
├── README.md
├── bren-meds213-data-cleaning.Rproj
├── data
│   ├── processed
│   │   ├── all_cover_fixed_ZHOU.csv        
│   │   ├── snow_cover.csv        
│   │   └── species_presence.csv
│   └── raw
│       ├── 01_ASDN_Readme.txt
│       ├── ASDN_Daily_species.csv
│       └── ASDN_Snow_survey.csv                 
├── data-cleaning_empty.qmd
├── data-cleaning_zhou.qmd
├── eds213_data_cleaning_assign_ZHOU.qmd
├── eds213_data_cleaning_assufb_ZHOU.html
├── docs      # Rendered document for easier viewing
└── renv
    ├── activate.R
    ├── library
    ├── staging
    └── settings.json
```

### 3. Additional related data collected that was not included in the current data packges:

Additional related data not contained within this repository such as `Bird_nests`, `Bird_eggs`, and `Camp_assignment` etc can be found in the original data set hosted by the [NSF Arctic Data Center](https://arcticdata.io) at the following link: [ASDN Data Set](https://doi.org/10.18739/A2222R68W).

### 4. Are there multiple versions of the dataset?

Other processed versions of the data can be accessed through the [MEDS EDS-213 GitHub Repository](https://github.com/UCSB-Library-Research-Data-Services/bren-meds213-data-cleaning)

## DATA-SPECIFIC INFORMATION FOR:

### The Original Data Set

ARCTIC SHOREBIRD DEMOGRAPHICS NETWORK <https://doi.org/10.18739/A2222R68W>

Data set hosted by the [NSF Arctic Data Center](https://arcticdata.io) data repository

Field data on shorebird ecology and environmental conditions were collected from 1993-2014 at 16 field sites in Alaska, Canada, and Russia.

![Shorebird, copyright NYT](https://static01.nyt.com/images/2017/09/10/nyregion/10NATURE1/10NATURE1-superJumbo.jpg?quality=75&auto=webp)

Data were not collected every year at all sites. Studies of the population ecology of these birds included nest-monitoring to determine the timing of reproduction and reproductive success; live capture of birds to collect blood samples, feathers, and fecal samples for investigations of population structure and pathogens; banding of birds to determine annual survival rates; resighting of color-banded birds to determine space use and site fidelity; and use of light-sensitive geolocators to investigate migratory movements.

Data on climatic conditions, prey abundance, and predators were also collected. Environmental data included weather stations that recorded daily climatic conditions, surveys of seasonal snowmelt, weekly sampling of terrestrial and aquatic invertebrates that are prey of shorebirds, live trapping of small mammals (alternate prey for shorebird predators), and daily counts of potential predators (jaegers, falcons, foxes). Detailed field methods for each year are available in the `ASDN_protocol_201X.pdf` files. All research was conducted under permits from relevant federal, state, and university authorities.

See `01_ASDN_Readme.txt` provided in the [course data repository](https://github.com/UCSB-Library-Research-Data-Services/bren-meds213-spring-2024-class-data) for full metadata information about this data set.

### The Processed Data Set

For the file data/processed/all_cover_fixed_ZHOU.csv:

#### 1. Number of variables:

**11**

#### 2. Number of cases/rows:

**42,830**

#### 3. Variable List: \<list variable name(s), description(s), unit(s)and value labels as appropriate for each\>

| Column Name | Definition                                            | Units      |
|--------------|--------------------------------------------|--------------|
| Site        | Four-letter code of site at which data were collected | N/A        |
| Year        | Year in which data were collected                     | YYYY       |
| Date        | Date on which data were collected                     | DD-MM-YYYY |
| Plot        | Name of study plot on which survey was conducted      | N/A        |
| Location    | Name of dedicated snow-survey location, if applicable | N/A        |
| Snow_cover  | Percent cover of snow, including slush                | Percentage |
| Water_cover | Percent cover of water                                | Percentage |
| Land_cover  | Percent cover of exposed land                         | Percentage |
| Total_cover | Total sum (should always sum to 100)                  | Percentage |
| Observer    | Person who conducted the survey                       | N/A        |
| Notes       | Any relevant comments on the survey                   | N/A        |

#### 4. Missing data codes: <list code/symbol and definition>

`NA` Missing data. This value indicates that the original entry was either non-numeric (e.g., ".", "n/a", "-", "unk"), outside the valid range (e.g., negative values or values over 100), or could not be inferred from the other cover types. When possible, "." values were interpreted as 0 if the total cover was correctly calculated to 100 with other columns. The data set does not infer missing cover values from the other two. It only recalculates Total_cover from existing values.The Total_cover column was recalculated as the sum of the three cover types and set to NA if the sum did not equal 100. This ensures all values are numeric, valid, and consistent with metadata expectations.

#### 5. Specialized formats or other abbreviations used:

`Plot` and `Location` are alphanumeric identifiers for the study plot and snow-survey location, respectively. 
`Site` is abbreviated with a four-letter code that represents the sampling site.
`Observer` is the code of the person's name who conducted the survey.

## SHARING/ACCESS INFORMATION

#### 1. Licenses/restrictions placed on the data:

The original data is licensed under the Creative Commons Attribution 4.0 International License. To view a copy of this license, visit <http://creativecommons.org/licenses/by/4.0/>.

**The dataset is distributed 'as is' and with absolutely no warranty.** The data providers have invested considerable effort to ensure that the data are of highest quality, but it is possible that undetected errors remain. Data have been processed with several steps for quality assurance, but **the data providers accept no liability or guarantee that the data are up-to-date, correct, or complete. Access to data is provided on the understanding that the data providers are not responsible for any damages from inaccuracies in the data.**

#### 2. Links to publications that cite or use the data:

-   [Life-history tradeoffs revealed by seasonal declines in reproductive traits of Arctic-breeding shorebirds](https://www.researchgate.net/publication/320616760_Life-history_tradeoffs_revealed_by_seasonal_declines_in_reproductive_traits_of_Arctic-breeding_shorebirds)
-   [Annual adult survival drives trends in Arctic-breeding shorebirds but knowledge gaps in other vital rates remain](https://academic.oup.com/condor/article/122/3/duaa026/5857122)
-   [Environmental and ecological conditions at Arctic breeding sites have limited effects on true survival rates of adult shorebirds](https://bioone.org/journals/the-auk/volume-135/issue-1/AUK-17-107.1/Environmental-and-ecological-conditions-at-Arctic-breeding-sites-have-limited/10.1642/AUK-17-107.1.full)

#### 3. Links to other publicly accessible locations of the data:

-   The original data set is hosted by the [NSF Arctic Data Center](https://arcticdata.io) at the following link: [ASDN Data Set](https://doi.org/10.18739/A2222R68W).

-   Other processed versions of the data can be accessed through the [MEDS EDS-213 GitHub Repository](https://github.com/UCSB-Library-Research-Data-Services/bren-meds213-data-cleaning)

#### 4. Links/relationships to ancillary data sets: \<any supplementary data sources that support analysis or classification of the datasets, eg., plant taxonomy table.)\>

There are several ancillary data sets and external resources that support the analysis and classification of the ASDN data sets:

-   ASDN Field Protocol files: Detailed field methods for each year are available in the ASDN_protocol_201X.pdf files. Appendix G provides reference for habitat and vegetation classification

-   US Bird Banding Lab codes: Bird species names are abbreviated with lowercase US Bird Banding Lab four-letter codes in all data files.

-   External weather data: Other camps used permanent weather stations (e.g. in nearby towns, airports); those data are archived and made publicly available by NOAA (US), Environment Canada, or Reliable Prognosis (rp5.ru).

-   Invertebrate taxonomy expert:Inverts: Raw data on invertebrate taxa identified in prey samples by Robert Wisseman, Aquatic Biology Associates, Inc., Corvallis, OR.

#### 5. Was data derived from another source? If yes, list source(s):

-   This is a cleaned version of the original data set. The original dataset is direct field observation and measurements and is not derived from another publication.

-   `Lanctot, RB, SC Brown, and BK Sandercock. 2017. Arctic Shorebird Demographics Network. NSF Arctic Data Center. <doi:10.18739/A2CD5M>.`

#### 6. Recommended citation for the project:

-   Please acknowledge this dataset and the authors in any analysis, publication, presentation, or other output that uses these data. If you use the original dataset, we suggest you cite it as:

-   `Lanctot, RB, SC Brown, and BK Sandercock. 2017. Arctic Shorebird Demographics Network. NSF Arctic Data Center. doi: INSERT HERE.`

-   If you use the processed data from this repository, please cite the course EDS-213 and [Zoe Zhou](https://github.com/ZoeZhouJ/bren-meds213-data-cleaning).
