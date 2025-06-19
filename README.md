# Design Flaws in the Polish Science Quality Evaluation System: A Technical Analysis of Latent Properties

This repository consists of the supplementary material for the publication
Tomasz P. Pawlak, Design Flaws in the Polish Science Quality Evaluation System: A Technical Analysis of Latent Properties,
Research Policy (in review)

It consists of four directories corresponding to four analyses in that publication:

* Optimization of scientific outcomes reporting
* Bias of institution size
* Subjective bias of criteria aggregation
* Conflicts of interest

Below, we describe the details of this data.

# Optimization of scientific outcomes reporting

## The estimate of the results of the 2022-2025 evaluation of quality of research in Poland

This directory consists of the estimate of the results of the 2022-2025 evaluation of quality of research of the Polish
science and higher education institutions based on the data in the [RADon](https://radon.nauka.gov.pl) system available
on 2025-06-02.

### Disclaimer

The RADon system does not provide all information necessary to calculate exact scores, e.g., it misses Full-Time
Equivalents (FTEs), employment end dates, dates of statements issued, past employees, complete lists of PhD students,
etc. Our investigation shows that the data for some institutions consists of invalid records, duplicate information,
inconsistent information, or simply incomplete information. Hence, the errors of estimates for various institutions may
vary significantly.

For all missing information, we applied 'reasonable defaults', e.g., FTE=1 for all employees, employment lasting until
the end of the evaluation period, discipline and N statements issued on the employment date only, all PhD students
having the promotion procedure initiated, etc. Since the RADon system does not provide the authorizations for the use
of a scientific outcome in evaluation, for each publication and intellectual property right, we selected the random
option out of all valid options.

### Optimization variants

For each institution three variants of the estimate are provided:

1. Optimization of penalties - the automatic selection of authorizations to minimize the penalties for no publications;
   **this should be considered the most reliable estimate of the current state of preparations**.
2. Optimization of penalties and k coefficient - the automatic selection of authorizations to minimize penalties for
   no publications and maximize disciplines' criterion 1 scores by manipulation k coefficients of publications.
3. Optimization of penalties, k, and disciplines - option 3 extended with the optimization of disciplines and N
   statements of employees in years 2023-2025.

### Data description

The directory consists of subdirectories corresponding to individual institutions satisfying the requirements of the
Polish Act on Higher Education and Science, Article 265., to be put under evaluation of quality of science. The 
subdirectories correspond to the official Polish names of the institutions. The science system institutions not 
satisfying these requirements are collected in the `non evaluated` directory.
The top-level directory contains also two special subdirectories `scientists` and `publications` containing raw input 
data downloaded from the RADon system.

The structure of each institution directory is as follows:

* `data` - the subdirectory consisting of the input data retrieved from the RADon system.
* `Evaluation optimize penalties.xlsx` - the spreadsheet containing the detailed results and the plan of statements 
   for the authorization of an institution for the use of scientific outcomes in evaluation, assuming the optimization 
   of penalties only.
* `Evaluation optimize penalties k.xlsx` - the spreadsheet containing the detailed results and the plan of statements
  for the authorization of an institution for the use of scientific outcomes in evaluation, assuming the optimization
  of penalties and these authorizations took place.
* `Evaluation optimize penalties k.xlsx` - the spreadsheet containing the detailed results and the plan of declarations 
  of working disciplines and the statements for the authorization of an institution for the use of scientific outcomes 
  in evaluation, assuming the optimization of penalties, authorizations, and disciplines took place.

All spreadsheets are in Polish.
  
# Bias of institution size

This directory consists of the demonstration of the bias of the institution size on the C1 score. It consists of two 
subdirectories:

* `data` - the subdirectory pertaining the input data retrieved from the Ministry through access to the public information 
  (C2 scores were calculated based on RADon data about projects and the remaining known values). This is the same as
  `Subjective bias of criteria aggregation/data`.
* `results` containing plots of the distribution of C1 scores against N numbers for all disciplines in the 2022 evaluation.

# Subjective bias of criteria aggregation

This directory consists of the data related to the demonstration of the potential of manipulating the allocation of 
scientific categories through the adjustment of the reference values. Its structure is as follows:

* `data` - the subdirectory pertaining to the input data retrieved from the Ministry through access to the public information
(C2 scores were calculated based on RADon data about projects and the remaining known values). This is the same as 
`Bias of institution size/data`.
* `Reference value optimizer.xlsx` - the spreadsheet taking as input the C1, C2, C3 scores of institutions in a single 
  discipline, the base reference values and outranking threshold, and the desired category allocation, and calculating 
  the minimal distortion to the reference values and outranking threshold that results in the desired category allocation.
  For desired allocations being infeasible, it minimizes the sum of errors for allocations. Refer to the spreadsheet 
  for technical details. Note that it requires Microsoft Excel desktop app with the solver addon.
* `Pareto fronts` - the subdirectory of visualizations of discrepancies between Pareto fronts and the actual category
  allocation for all disciplines in the 2022 evaluation.


# Conflicts of interest

This directory consists of a single spreadsheet `Conflicts of interest.xlsx` consisting of the list of active researchers 
in potential conflicts of interest in the 2022 evaluation, scraped from the websites of 
the [Polish Ministry of Science and Higher Education](https://www.gov.pl/web/science) (formerly the Ministry of Education and Science), 
the [Science Evaluation Committee](https://www.gov.pl/web/nauka/sklad-komisji-ewaluacji-nauki-w-kadencji-2019-2022), 
and the [National Information Processing Institution (OPI PIB)](https://opi.org.pl/en/) on 2022-06-23.

