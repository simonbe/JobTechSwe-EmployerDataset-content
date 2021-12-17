(Under construction. Data last updated: 2021-12-15)

# Employer Dataset Getting Started

This dataset contains information on 9X 000 Swedish employers which can be of relevance for job matching applications.  
For each employer, it contains name and location information, recruitment statistics and estimated workforce growth.  

The dataset can be extended with more information, see [below](#extend).
 

## Downloads
**Table Employers**  
Download: [json](X)  [csv](X)  [parquet](https://minio.arbetsformedlingen.se/historiska-annonser/employer_2/table_employers.parquet)  
Description: Main file with information for 9X 000 employers. Table structure where each row represent one employer.<sup>1</sup>.  
Details: [Notebook example](https://colab.research.google.com/drive/1x_Wxtn3V8ow3axOb6N9dZidV9bPbStF4?usp=sharing), [file structure](#structure)

**Collections**  
Download: [json](X) [csv](X) [parquet](https://minio.arbetsformedlingen.se/historiska-annonser/employer_2/collections.parquet)  
Description: Collections of organizational numbers for location, industry, estimated occupations, competencies and traits. Can be used as easy access for subsets of employers.  
Details: [Notebook example](https://colab.research.google.com/drive/1x_Wxtn3V8ow3axOb6N9dZidV9bPbStF4?usp=sharing), [file structure](#structure)

## Examples
Notebook example: [Load data](https://)  
Notebook example: Similarity  
Application example: [Jobbometern](https://test-functions-36r.pages.dev/), [src](https://)  

## Structure
**Table Employers**

| Column |  Example | Description |
|:-|:-|:-| 
| organization_number |55053 | 
| name | Arbetsförmedlingen | 
| adress | Solnavägen 1|  Main workplace adress
| city  | Solna |
| municipality  | Solna |
| municipality_code  
| county | Stockholm |
| county_code | 01 |
| size_class | { '9', '20 000-50 000'} | Estimated size of employer<sup>4</sup>
| nr_ads_pb | 5205 | Available ads from Platsbanken (pb) from the [historical ads](https://jobtechdev.se/en/products/historical-jobs) dataset.
| nr_ads_extern | 0 | Available external ads not published on Platsbanken from the [joblinks](https://jobtechdev.se/en/products/ekosystem_foer_annonser) dataset.
| est_top_occupations_pb | | Estimated top occupations encoded as [occupation-names](https://jobtechdev.se/en/products/jobtech-taxonomy) from pb.
| est_top_ssyk4_pb | | Estimated top occupations encoded as [SSYK4](https://jobtechdev.se/en/products/jobtech-taxonomy) from pb ads.
| est_top_ssyk4_extern | | Estimated top occupations encoded as [SSYK4](https://jobtechdev.se/en/products/jobtech-taxonomy) from external ads.
| est_competencies_traits_pb | | Estimated competencies and traits [enriched](https://jobtechdev.se/en/products/jobad-enrichments) from pb ads.
| est_competencies_traits_extern | | Estimated competencies and traits [enriched](https://jobtechdev.se/en/products/jobad-enrichments) from external ads.
| est_seasonal | {'hiring': {'jan':0.1,...}, 'staffing': { 'jan': 0.1, ...} | Estimated hiring and staffing (i.e. histograms over months) from pb ads ('hiring') and workforce taxes paid ('staffing')
| est_workforce_growth | | Estimated workforce growth: Previous year ('slope_last_year'), time series prediction 1-month '1-month', 3-month and 12-month

  

**Collections**

| Column | Example | Description |
|:-|:-|:-|
| type | |
| code | |
| concept | |
| organization_numbers| |
| indices | 


## Extend
Description  
Example, src
  


## License
[CC0](https://creativecommons.org/publicdomain/zero/1.0/)

## Details
<sup>1</sup> Only either limited companies (Aktiebolag) or employers which have been active on Platsbanken. Small employers are excluded from the dataset.  
<sup>2</sup> Name, organization number and address for main workplace.  
<sup>3</sup> 
