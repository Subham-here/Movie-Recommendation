# A recommender system of movies for OTT platform

## Project Overview
Intention was to crate a content based recommender system which will suggest movies based on the 

## Data Preprocessing
### 1.	Filtering of data
After loading the dataset, first I have pre processed the data a bit. There were several “revenue” fields which had ‘0’, there were fields like “vote_average” and “vote_count” where there were values as low as 0 and 0.5. So, to avoid these data I have applied filters to the fields where I will only consider 
revenue which is greater than 20,000, budget greater than 15,000, minimum number of people who voted greater than 100 and average rating greater than 7.2 

![image](https://github.com/Subham-here/Movie-Recommendation/assets/170924246/56654906-0588-4e4f-8450-6bf809f926c5)

 
### 2.	Normalizing the data
There’s one more thing to be taken into consideration. The variables or the factors that I am going to use for the calculation has very different ranges (Where voting_average varies from 0 to 9, and on contrary movies budget has very huge range). So, to bring the values in the same range, I have normalized the values using z-Score normalization method.
 
 
	![image](https://github.com/Subham-here/Movie-Recommendation/assets/170924246/d888b5b1-f876-4e17-928b-2b3b0651485c)
  ![image](https://github.com/Subham-here/Movie-Recommendation/assets/170924246/16c18560-af31-4ceb-a662-ddc4420a3692)


### 4.	Replacing the normalized values in the dataset
Then I have replaced the above columns with the normalized values what I have just created and also, added an extra column for ‘Rating’ just to show the rating of the recommended movies.

 ![image](https://github.com/Subham-here/Movie-Recommendation/assets/170924246/3eaf6737-efe5-40bd-b8a7-f0a396e3ff47)


## Calculation of the Metric
To get the popularity score, added a column ‘My_Recommendation’ and populated the calculated values as

                                            (Revenue/budget) * vote_average * vote_count
                                            
Intuition is that the movies which are generating high revenue must be popular enough, and then average rating and number of people voted are taken into consideration
 
## My Recommendation List
Then, I have the sorted My_reccomendation in ascending order to get the top recommended movies.
 
 ![image](https://github.com/Subham-here/Movie-Recommendation/assets/170924246/0bea84d3-35f8-433f-961e-87417ff5b07c)


