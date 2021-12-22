(This dataset is in a beta stage - structure and data may change)  
Data last updated: 2021-12-15
<br><br>

# Employer Dataset Getting Started

This dataset contains information on ~95 000 Swedish employers<sup>1</sup> which can be of relevance for job matching applications.  
For each employer, it contains name and location information, recruitment statistics and estimated workforce growth.  

This dataset can be extended with more information, see [below](#extend).
<br><br>

## Downloads
**Table Employers**  
Download: [json](https://employer.blob.core.windows.net/data/table_employers.json.zip)  [csv](https://employer.blob.core.windows.net/data/table_employers.csv.zip)  [parquet](https://employer.blob.core.windows.net/data/table_employers.parquet)  
Description: Tabular structure of dimensions 17 columns x ~95 000 rows. Each row represents one employer and each column field contains one or many data points.  
Details: [Structure](#table-employers), [notebook example](https://colab.research.google.com/drive/1x_Wxtn3V8ow3axOb6N9dZidV9bPbStF4?usp=sharing)

**Collections**  
Download: [json](https://employer.blob.core.windows.net/data/collections.json.zip) [csv](https://employer.blob.core.windows.net/data/collections.csv.zip) [parquet](https://employer.blob.core.windows.net/data/collections.parquet)  
Description: Collections of organizational numbers for locations, occupations, competencies and traits and industry groups. Can be used to fetch relevant subsets of employers.  
Details: [Structure](#collections), [notebook example](https://colab.research.google.com/drive/1x_Wxtn3V8ow3axOb6N9dZidV9bPbStF4?usp=sharing)
<br><br>
## Examples
Application example: [Jobbometern](https://test-functions-36r.pages.dev/) (<u>src</u>)  
Notebook examples: [Load data](https://), (additional example in preparation)
<br><br><br>

## Structure

### Table Employers


| Column |  Example | Description |
|:-|:-|:-| 
| organization_number |55053 | 
| name | Arbetsförmedlingen | 
| adress | Solnavägen 1|  Main workplace adress.
| postal_code | 11000| 
| city  | Solna |
| municipality  | Solna |
| municipality_code  
| region | Stockholm |
| region_code | 01 |
| <br>size<br><br>[subcolumns:<br>est_class, term]| { 'est_class': 9, <br> 'term': '20 000-50 000'} | Estimated size of employer<sup>2</sup>
| <br>nr_ads<br><br>[subcolumns:<br>pb, other]| {'pb': 5205, 'other': 43 } | Nr ads from Platsbanken/[historical ads](https://jobtechdev.se/en/products/historical-jobs) dataset ('pb' dataset) and from the [joblinks](https://jobtechdev.se/en/products/ekosystem_foer_annonser) dataset ('other') which below fields use (est_top_occupations, est_top_occupations_ssyk, est_competencies_traits, est_competencies_traits_ssyk).
| top_occupations | [ { 'term': 'Arbetsförmedlare', 'concept': '', 'code': '', 'probability': 0 } | Top occupations (max 20) for employer from the pb dataset encoded as [occupation-names](https://jobtechdev.se/en/products/jobtech-taxonomy).
| <br>top_occupations_ssyk<br><br>[subcolumns:<br>pb, other] | {'pb': [ { 'term': 'Arbetsförmedlare', 'concept': '', 'code': '', 'probability': 0 }, {...}]| Top occupations (max 20) encoded as [SSYK](https://jobtechdev.se/en/products/jobtech-taxonomy) from the pb dataset ('pb') and estimated SSYK from the joblinks dataset ('other').
| competencies_traits | | Corresponding estimated competencies and traits (max 200 per occupation)[enriched](https://jobtechdev.se/en/products/jobad-enrichments) for each occupation from the pb dataset.
| <br>competencies_traits_ssyk<br><br>[subcolumns:<br>pb, other] | | Corresponding estimated competencies and traits [enriched](https://jobtechdev.se/en/products/jobad-enrichments) for each occupation encoded as SSYK.
| <br>seasonal | {'hiring': {'jan':0.1,...}, 'staffing': {} } | Estimated hiring and staffing per month from the pb dataset ('hiring') and the workforce taxes paid by the employer ('staffing')
| <br>workforce_growth<br><br>[subcolumns:<br>est_last_12_months,est_1_months,<br>est_3_months, est_12_months,<br>est_growth_class,est_growth_class_term]  | | Estimated workforce growth<sup>3</sup>: Growth during previous year ('last_12_month'), and time-series predicted growth and estimated standard deviation for coming months ('pred_months_t' / 'pred_months_t_std' for t ∈ {1,3,12} months).

<br>

### Collections

| Column | Example | Description |
|:-|:-|:-|
| type | "ssyk" | location ("country", "region", "municipality","city"), occupation ("occupation-name", "ssyk"), industry group ("industry group"), competencies ("competence") or traits ("trait")
| code | "2314" | When relevant, e.g. ssyk code or municipality code
| concept | "Xr_zTY_4f" | Corresponding concept from jobtech taxonomy
| organization_numbers| [5500001, 5500002, ...] | List of relevant organization numbers.
| indices | [4323, 16, 82001,...] | List of corresponding indices for employers in table employers.


## Extend

This dataset can be extended with additional employer information of relevance for job matching. Please contact us for more information.  
(Example: [Track number of new companies started](#)) 

## License
[CC0](https://creativecommons.org/publicdomain/zero/1.0/)

<br><br>
<sup>1</sup> Included are employers which have published ads on Platsbanken or employers which are limited companies ('aktiebolag') regardless if they have published ads or not. Small employers and 'enskild firma' are excluded from the dataset.  
<sup>2</sup> Size class.  
<sup>3</sup> Based <u>only</u> on total payroll taxes paid ('arbetsgivaravgifter'). No correction for wage increases. such as variation in tax deductions or paid bonuses. This disregards any other and should be viewed as an indication more than a full prediction of future workforce growth.
