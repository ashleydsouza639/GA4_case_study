# GA4_case_study

Case study to analyze the Google Analytics 4 sample ecommerce dataset using Dataform.

## Source

`bigquery-public-data.ga4_obfuscated_sample_ecommerce.events_*`

## Dataform workflow

The project contains the following layers:

* Source: GA4 public dataset referenced using a Dataform declaration
* Silver: Purchase events with required fields extracted and `(data deleted)` traffic source records removed
* Gold: Monthly purchase metrics grouped by traffic source medium

## Silver

`purchase_traffic_source_medium`

Contains purchase events with:

* Event date
* Traffic source medium
* User ID
* GA session ID
* Event value in USD
* Total item quantity

## Gold

`top_traffic_source_medium`

Aggregates the Silver data by month and traffic source medium.

Metrics:

* Purchased value in USD
* Total purchased items
* Average items per purchase

## Data lineage

GA4 source → Silver → Gold

Below is the project code structure:
<img width="767" height="391" alt="image" src="https://github.com/user-attachments/assets/65f89d6a-aeb6-42db-bd7a-5c3771261b7a" />

You can start execution once you commit the code 
<img width="959" height="418" alt="image" src="https://github.com/user-attachments/assets/e7b02763-708e-472a-8656-849dd94b5849" />



You can see the Dataform graph is included in `dataform_lineage.png` as well as below:
<img width="959" height="450" alt="image" src="https://github.com/user-attachments/assets/7820ecdb-31e0-43f1-989d-e24ae106343d" />

