# Executive Summary and Problem Statement

Stylescout.com is a website which provides advertising and appointment booking services for various hair salons in New York City. The website conducts extensive reviews on vairous salons and has several articles on their blog about the latest hair styles and trends. In this project, the primary stakeholder is stylescout.com and the secondary stakeholders are the people who use their website's services.

I have been tasked by the creators of stylescout.com to build a classifier model using Natural Language Processing (NLP) and different machine learning techniques which can accurately predict language patterns that are related to male hairstyles or female hairstyles. They then intend to use this information to conduct search engine optimization to improve web traffic to articles and advertisements on their website which target one particular gender. Therefore, I have used posts from the subreddits 'r/femalehairadvice' and 'r/malehairadvice' to construct and test the models.

4 classifier models were created which accurately predicted whether a post originates from either 'malehairadvice' or 'femalehairadvice' subreddits and each of the models' pros and cons were explored. The models were constructed using 1500 of the top posts from this year (2021) scraped from reddit.com and then evaluated using 500 new posts scraped a week later. Taking all this into consideration, the models were evaluated before 1 was recommended to stylescout.com for their search engine optimization algorithm.

