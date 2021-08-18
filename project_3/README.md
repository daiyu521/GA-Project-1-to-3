## Executive Summary

When talking about the Marketing, we always need to mention about the target audience. Identifying a target audience provides a clear focus on whom your business will serve. Determining this information also keeps a target audience at a manageable level. 

The data-driven Digital revolution makes today's marketing solution becoming more targeted every day. An automated classification of users into groups can make Marketers' life simple. Marketer can monitor and classify users based on how they talk about a product or brand online. The classifier can be trained to identify promoters or detractors. Thus, making brands to serve the target group better.

Microsoft’s Xbox 360 has proven to other brands that Reddit is an excellent platform with funneling the customers into the right subreddit. By providing a subreddit from the community to share their experiences with the Xbox 360. Xbox 360 even could know what customers will move onto when support ends for the xbox 360 next year. This success story shows how influential the target audience is for todays'business.

As a company that runs a famous game forum online with a large Gamer community to share their passion for gaming with people worldwide, we urge to have a classification model that could classify the gamers to different Groups to serve both our partners and gamer community better.

#### Problem Statement

We are a company run a famous game forum online that has a large Gamer community to share their passion for gaming with people worldwide. In the same time, our company also partner with game providers to market their product.

Sony and Xbox recently opened pre-orders for their next-gen consoles. More people prefer to do an online pre-order during the coronavirus pandemic instead of visiting the physical stores. One of the wholesalers on Amazon worked with us to advertise their pre-order news/links to the target customers repectively.

To serve our gamer community better and benefit our partner simultaneously, our marketing team was tasked us with developing a model to classify the potential PS5 and Xbox users based on their postings. In this project, we will collect the gamers' Posts from Reddit PS5 and XboxseriesX communities by using Reddit API. The algorithms used for text classifications are multinomial naive Bayes and logistic regression. Further, we will evaluate their performance by accessing their accuracies, sensitivities, and specificities etc. to conclude which method is better for implementation.

#### Target Audience:

- Primary stakeholders: Peer data scientists and Semi-tech marketing staffs
- secondary stakeholders: The game wholeseller

## Data Dictionary

|Features                    | Type    |Description
|:---------------------------|:--------|:----------------------------------------------------------------------------------------
| title                      | object  |Post title
| selftext                   | object  |Post content under the title
| subreddit                  | object  |Target variable
| feature                    | object  |combined text for Post title and post content

## Conclusion

Reddit is a social news platform that allows users to discuss and vote on content that other users have submitted. The sub-Reddit funnels users with questions into the right channels to get resolved. Collecting the gamers' Posts from the subreddits PS5 and XboxseriesX by using Reddit API allows us to develop a text classification model to determine the potential PS5 and XboxSeriesX users based on their posts. 

The Documents collected from Reddit are preprocessed by removing the HTML code artifacts, stopwords, and punctuations and returning to based form words. We found the documents contain those unnecessary pieces of information for modeling during the Data Exploring Analysis. Considering the complexity of this project's features, we use the Multinomial NB and Logistic Regression modeling method to predict the outcomes.

After comparing the Multinomial NB model's performance with the logistic regression model, we decided to choose the Multinomial NB model as our classifier. Due to its better accuracy, higher f1_score, lower misclassification Rate, and better ability to generalize the new data. (see below talbe:)

|                           |MNB         |LR          |
|-------------------------- |------------|------------|
|Accuracy                   |0.8476      |0.8453      |   
|Misclassification Rate     |0.1524      |0.1547      | 
|Precision                  |0.8995      |0.9076      | 
|Recall                     |0.7834      |0.7696      | 
|Specificity                |0.912       |0.9213      | 
|Train\Test mean accuracy   |0.837\0.831 |0.838\0.828 |
|f1_score                   |0.8470      |0.8444      | 

We can predict about 85% accuracy for the potential game consoles users according to their posting with this model. The implementation of this model in our game forum will help our partners reach their products to the right customers and serve our gamer community better as well. Besides, I recommend that the marketing team and our partner use this model to predict the potential PS5 users for advertisement purposes. This model shows higher specificity, lower recall, which means it works much better in predicting potential PS5 users. Of Course,  The marketing team and our partner can use it for the XboxseriesX as well, but there will be a higher misclassification rate than predicting PS5, it will result in losing more valuable XboxSerieX customers in the long run. Further, we can optimize this issue by adjusting the Thredshold, but it will skew the overall performance vice versa.

Finally, we can continuously improve the model by introducing more new data to it. More data added,  better prediction outcome.The introduce of updated new data will keep our model relevant to the current status. We could collect more data for different game consoles eg switch, to enhance the ability for model to classify more than two subreddits.  We could also collect the data from other language groups to develop a similar model to serve different market territories.


```python

```
