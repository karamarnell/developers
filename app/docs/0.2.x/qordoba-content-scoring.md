---
title: Introducing Qordoba Content scoring
---

# Introducing Qordoba Content scoring


When you check with in Qordoba content editor, you can see an Qordoba Score for the document on the right side menu. The Qordoba conten score expresses the average of all category scores as a standardized score out of 100 that is easier for most users to understand. The higher the score, *the higher the quality of the content.* You can influence the calculation of the Qordoba Score by configuring the weighting of category scores.



###How the Qordoba Score is Calculated

Content scores help you to quantify the quality of a document and compare it with other documents. The Qordoba Score expresses the overall quality of your content as a score between 1 and 100. You also get similar scores for how well you did in each of the quality categories such as spelling or style. The overall Qordoba Score is simply an average of your individual category scores.


###How the Scores for Each Quality Category are Calculated
Each individual quality category is calculated according to the following formula:

```
Normalized document length / (Normalized document length + issue count)
```
This formula contains the following variables:

- Document length: The number of words in the document.

- Normalized document length: The number of words in the document divided by a factor of 75.

- Issue count: The number of issues that Qordoba found in the quality category, such as spelling.


The following table shows you what the calculation steps would be for a document with 1000 words and 12 spelling issues.


|Step	|Calculation	|Result|
| ------------- | ------------- | ------------- | 
|1. Calculate the normalized document length	|1000 / 75	|13.33|
|2. Add the normalized document length and the issue count	|13.33 + 12|	25.33|
|3. Divide the normalized document length by the result of the previous step	|13.33 / 25.33|	0.5263|
|4. Express the result as a percentage and round it to the nearest whole number	|0.5263 * 100| 53 |


#####Calculating the Overall Qordoba Score
The Qordoba Score is the average of all the category scores rounded down to the nearest whole number. For example, suppose that you check a document, open your Scorecard, and see the following scores in the Categories section:

| Category	| Score| 
| ------------- | ------------- |
| Grammar/Spelling	| 57| 
| Style| 	33| 
| Emotion| 	35| 
| Tone| 	25| 
| Plagiarism| 	35| 
If you take the average of all the category scores and round it down to the nearest whole number, you get a final Qordoba Score of 37.

###Weighting the Category Scores
You can configure the server to increase or decrease the influence that a category score has on the Qordoba Score. Weighting a category score helps writers prioritize the issues to correct in a document.

For example, suppose that want to encourage writers to remove all spelling issues in a document before addressing other issues. You set the weighting for the spelling category to 200%.

This way, the spelling category score counts twice as much as the same number of flags in any other category.

***You can configure the weighting for a category score from the Account -> Settings -> Content Score.***