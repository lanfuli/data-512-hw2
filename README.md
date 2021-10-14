# data-512-hw2
Goal:
- The goal of this assignment is to explore the concept of bias through data on Wikipedia articles - specifically, articles on political figures from a variety of countries.

Data Link:
- https://figshare.com/articles/dataset/Untitled_Item/5513449
- https://docs.google.com/spreadsheets/d/1CFJO2zna2No5KqNm9rPK5PCACoXKzb-nycJFhV689Iw/edit#gid=283125346
- https://www.prb.org/international/indicator/population/table/

Getting Article Quality Predictions API:
- https://github.com/wikimedia/ores

Step 1 and 2 : Getting the Article and Population Data and Cleaning Data
- a. Get the data from WPDS_2020_data: https://docs.google.com/spreadsheets/d/1CFJO2zna2No5KqNm9rPK5PCACoXKzb-nycJFhV689Iw/edit#gid=283125346
- b. Clean the data
    - i: sub-region only(wpds_2020_data_sub_rmw.csv)
    - ii: country only(wpds_2020_data_ctry_rmw.csv)

Step 3: Getting Article Quality Predictions
- a. Call the ores api, getting the score data from the api by rev_id(50 ids each time) to void application crash, it will take 3-5 minutes to finish
- b. Map the socre to the WPDS_2020_data(page_data_2)
- c. Save the data into 2 csv file:
    - i: No NA score page_data_score_nna.csv
    - ii: NA score na_score.csv

Step 4: Combining the Datasets
- a. Merge the dataframe: page_data_score_nna, wpds_2020_data_ctry_rmw
- b. Save no match data to no_match.csv
- c. Save data_merge_match.csv contains all articles analyzed, the corresponding country and population, and their predicted quality score.

Step 5: Analysis

- Top 10 countries by coverage: 10 highest-ranked countries in terms of number of politician articles as a proportion of country population

<img width="438" alt="Screen Shot 2021-10-14 at 3 28 37 PM" src="https://user-images.githubusercontent.com/16252490/137404175-aebd11b4-b1b1-4ba1-86a1-d20b53ebbdfe.png">


- Bottom 10 countries by coverage: 10 lowest-ranked countries in terms of number of politician articles as a proportion of country population

<img width="346" alt="Screen Shot 2021-10-14 at 3 29 26 PM" src="https://user-images.githubusercontent.com/16252490/137404256-ba0b86c9-5517-4c66-bbc8-1b9b7105522b.png">


- Top 10 countries by relative quality: 10 highest-ranked countries in terms of the relative proportion of politician articles that are of GA and FA-quality

<img width="574" alt="Screen Shot 2021-10-14 at 3 30 22 PM" src="https://user-images.githubusercontent.com/16252490/137404323-2e17ad96-350c-449b-9fa0-761f8c6b44f2.png">



- Bottom 10 countries by relative quality: 10 lowest-ranked countries in terms of the relative proportion of politician articles that are of GA and FA-quality

<img width="498" alt="Screen Shot 2021-10-14 at 3 30 44 PM" src="https://user-images.githubusercontent.com/16252490/137404351-e6a56008-fa29-46d2-bc96-20971118b023.png">


- Geographic regions by coverage: Ranking of geographic regions (in descending order) in terms of the total count of politician articles from countries in each region as a proportion of total regional population


<img width="505" alt="Screen Shot 2021-10-14 at 3 31 20 PM" src="https://user-images.githubusercontent.com/16252490/137404389-c9527c07-ee6f-4ddc-9907-f9e16bb4f6f4.png">



Geographic regions by coverage: Ranking of geographic regions (in descending order) in terms of the relative proportion of politician articles from countries in each region that are of GA and FA-quality

<img width="569" alt="Screen Shot 2021-10-14 at 3 31 39 PM" src="https://user-images.githubusercontent.com/16252490/137404418-96cc6ffc-2299-4e14-a915-9e93efc688c0.png">



