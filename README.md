# Fragrance Analysis and Recommendations

## NOTE: 
IF NOTEBOOKS' PREVIEWS IN GITHUB NOT RENDERING, PLEASE SEE LINKS BELOW FOR HTML RENDERINGS: <br> 
* Part 1- Dataset Analysis and Survey Analysis https://nbviewer.org/github/nisha-kaushal/Fragrance_Analysis_and_Recommendations/blob/main/Fragrance_Deep_Dive_Part_1.ipynb <br>
* Part 2- Recommendation System https://nbviewer.org/github/nisha-kaushal/Fragrance_Analysis_and_Recommendations/blob/main/Deep_Dive_Part_2_Fragrance_Recommendation_System.ipynb

## Why This Project? 
This project holds significant importance in the realm of data science and consumer preferences. By meticulously analyzing fragrance notes and comparing them to individual preferences, it provides valuable insights into the intricate world of scent preferences. This not only enhances our understanding of consumer behavior but also empowers businesses in the fragrance industry to tailor their offerings to specific demographics. Furthermore, the recommendation system introduces a personalized element, revolutionizing how consumers discover and select fragrances. This innovation has the potential to revolutionize the fragrance market, creating a more tailored and satisfying experience for consumers while offering businesses the opportunity to refine their product offerings. Overall, this project not only showcases the power of data-driven insights but also addresses a tangible need in a thriving industry.

## Goal 
For Part 1, the overall goal is to analyze different fragrances based on their notes, and compare the findings to the notes preferences of surveyed users. <br>
For Part 2, the goal is to create a recommender system that can recommend 5 fragrances to a user based on fragrance notes they want in the fragrance. 

## Data Source 
* Part of the data was found on Kaggle, [here](https://www.kaggle.com/datasets/nandini1999/perfume-recommendation-dataset) <br> 
  * Because there were not many data entries in the dataset, I attempted to webscrape the data from the popular online fragrance database, Fragrantica. However, Fragrantica has limitations in the amount of times one can gather data from the website, so I had to result to hard-coding many of the data points. <br>
* Survey Data Conducted through Google Forms. The survey is still available to contribute to future updates, and can be found [here](https://docs.google.com/forms/d/e/1FAIpQLScGjr5oM_CzUVDHIQ3sr-TISh51U84lXy1rsC9utzrQgFmzBg/viewform)

## Part 1: Analysis of Notes in Popular Fragrances and Survey Respondent's Note Preferences 

One of the first parts of the data that I am interested in is the density of different brands in the data, ie, the amount of fragrances per brand. Using Atair, I created a bar graph to show the top 40 brnads represented in the data, based on how many of their fragrances are in the dataset. <br>
![image](https://github.com/nisha-kaushal/Fragrance_Analysis_and_Recommendations/assets/100887571/d6236c10-5800-40d3-a1fb-4837d92a24c2)

Once I found the top brands, I became interested in the way brands represent their fragrances' smells in the product descriptions vs. what the official listed notes are. The data included the official listed notes, and I extracted the notes that are mentioned in the product descriptions. Using these two separate lists for each fragrance, I found the cosine similarities. Below are the distributions of cosine similarities: <br>
![image](https://github.com/nisha-kaushal/Fragrance_Analysis_and_Recommendations/assets/100887571/75ebdd05-e611-437d-8bed-3c94ab5ebae9) <br> 
It seems that, while there are similarities between the original (/"official") notes and the product description-extracted notes, not many fragrances have them exactly matching (cosine = 1.0). From this, I gather that this means that the descriptions may be focusing on a few notes or fragrance categories rather than all of the notes that are in the fragrance. 


### Notes in Fragrances 
Now that I am on the topic of the fragrance notes, I want to look into what fragrance notes are the most prominent across the fragrances in the dataset. <br>
Top 50 notes used in Fragrances <br> 
![image](https://github.com/nisha-kaushal/Fragrance_Analysis_and_Recommendations/assets/100887571/a446a94e-b78f-4887-805f-9af029eb5894)


### Survey
Most Used Notes in Fragrances vs Preferred Notes by Survey Respondents
![image](https://github.com/nisha-kaushal/Fragrance_Analysis_and_Recommendations/assets/100887571/f08f091d-4572-4845-b89b-14ed5d3da72f)

### Notes Frequency Among Fragrances vs. Notes Frequency in Participant Responses: Analysis

While the survey is still open, currently there have been a total of 70 responses collected (this number/notebook may be updated periodically when/if new responses arrive). 

Before looking into the notes themselves, the first noticeable difference between the two charts is the general percentages. The percentages for the fragrances (left chart) range between 8% and 26%, while the range for the responses (right chart) range from 33% to 57% (maximum percentage subject to change if new responses are received). This discrepency is likely because the participants were only given 60 notes to choose from, plus an "Other" option, and there are more notes represented among the fragrances apart from those 60. Because of this, instead of focusing on the exact percentages themselves, __*I will be basing my analysis on the relative greater/lesser relationships between notes in each individual chart.*__ <br> 

#### Matching Scents
The following scents are present in both the top 17 scents in the fragrances and the top answers of the participants (the notes that were present in over 33% of the participants' responses): **musk, vanilla, sandalwood, rose, jasmine, and lemon**. 
#### Should brands cater towards the responses that are more prevalent in the responses given in the survey?
If a brand were to send a survey like the one used in this report, should they focus primariluy on the top answers that the participants choose? <br> 

While brands have to consider consumers' preferences, they also have to consider bringing about unique fragrances that can attract. While brands may consider incorporating the popular notes among consumers, adding in notes that may not be frequently used adds to the general uniqueness of a fragrance. 

While brands should take into consideration the responses to surveys similar to the one I have given, I do not think they should make it a case to cater towards just the popular scent notes. The uniqueness of different fragrances comes from the combination of scents, including the addition of a scent that may not be well known or popular. 

## Part 2: Fragrance Recommendation System 
