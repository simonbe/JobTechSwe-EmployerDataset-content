(under construction)

## Employer Dataset Getting Started

### Description
This dataset contains information on employers: Basic information and statistics of relevance to job matching applications.

### Table employers

**Columns**  
[organization_number, (name), alias_names, (adress), (sni), (est_size), est_top_occupations, est_competencies_traits, est_growth, est_seasonal trends]

**Dimensions**  
~96k (employers) x 11

**Download**  
[json](https://minio.arbetsformedlingen.se/historiska-annonser/employer/table_employers_json.zip) [csv](https://minio.arbetsformedlingen.se/historiska-annonser/employer/table_employers_csv.zip) [parquet](https://minio.arbetsformedlingen.se/historiska-annonser/employer/table_employers.parquet)

[**Code Example**](https://colab.research.google.com/drive/1x_Wxtn3V8ow3axOb6N9dZidV9bPbStF4?usp=sharing)  
  
### Collections

**Occupation+location to organization numbers**  
**Columns**: [occupation, location, location_code, [organization numbers], [indexes]]  
**Download**  
[json](https://minio.arbetsformedlingen.se/historiska-annonser/employer/loc_occ_json.zip) [csv](https://minio.arbetsformedlingen.se/historiska-annonser/employer/loc_occ_csv.zip) [parquet](https://minio.arbetsformedlingen.se/historiska-annonser/employer/loc_occ.parquet)

**SNI+location to organization numbers**  
**Columns**: [SNI_group, location, location_code, [organization numbers], [indexes]]  
**Download**  
[json](https://minio.arbetsformedlingen.se/historiska-annonser/employer/loc_sni_json.zip) [csv](https://minio.arbetsformedlingen.se/historiska-annonser/employer/loc_sni_csv.zip) [parquet](https://minio.arbetsformedlingen.se/historiska-annonser/employer/loc_occ.parquet)

Code Example

### Aggregations