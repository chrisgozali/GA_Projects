# The Pawsome Classifier
## Executive Summary

### Background information
#### History of dog pedigrees
"Man's best friend" - a commonly used phrase to describe dogs. Over centuries, dogs have faithfully served as companions to humans by providing assistance to a wide range of activities including hunting, guarding, herding, sport and war. Over the course of history, dogs have been selectively bred based on useful characteristics to optimize their functionality. Therefore, modern day dog pedigrees are a product of such selective breeding, and indirectly reflect the nature of their relationship with humans in the past. Recently, ["designer dogs"](https://www.thesprucepets.com/what-is-a-designer-dog-breed-1118093), where pure-bred dogs are intentionally cross bred to produce offspring with a mixed characteristics of their parents, are becoming a trend.

#### Kennel Clubs
Kennel clubs are organizations that operate nationally to to keep track of dog pedigrees. Additionally, they organize dog shows and competitions. The various kennel clubs also categorize each breed into breed groups based on their general functionality and appearance. It is important to note that each kennel club differs in the methodology used for categorizing dog breeds.

### Problem statement
As an aspiring data scientist new to computer vision, I have planned this project out of personal motivations. Combining my own interest in dogs and machine-learning, I aim to build a model that can categorize dogs by breed. To train the model, I used the Stanford Dogs dataset contains over 20,000 images of 120 different dog breeds. For model evaluation, I included a separate dataset from kaggle with 55 different dog breeds. (The original dataset contained 70 dogs. Only breeds that were in the stanford dataset were used)

#### Summary of Datasets
| Dataset | Source | Purpose | Size | Classes |
|--|--|--|--|--|
| [Stanford Dogs](https://www.kaggle.com/jessicali9530/stanford-dogs-dataset) | Kaggle |Training|20,580|120|
|[55 Dogs](https://www.kaggle.com/gpiosenka/70-dog-breedsimage-data-set)| Kaggle | Evaluation|550|55|
|Designer Dogs|Internet|Prediction|20|10|


#### Modelling approach
The modelling process is split in two stages:
1) Firstly, to reduce the dimensionality of the problem without reducing the amount of images used to train the model, I reclassified the 120 breeds into 12 groupings based on [The Continental Kennel Club's](https://ckcusa.com/) (CKC) breed standards. I selected the CKC's groupings for this project as there is a sufficiently diverse classification system of 12 groups which are based highly on the dog's physical appearance. This should be helpful in training the machine learning model to recognize distinct physical features of various dog breeds.


2) The second stage is to use the above model as a base to train the model to recognize 120 different breeds.

#### Results and evaluation
I used transfer-learning with EfficientNet-B7 as a feature extractor to construct my model. To evaluate the performance of the model, I used a separate dataset containing images of 55 different dog breeds. Additionally, I included some "designer dogs" as a stretch goal to see if the model can accurately predict the dog's heritage. As these "designer dogs" are not recognized as "pure breeds", they are not held by Kennel Club breed standards. It could be interesting to see how the model categorizes such "designer dogs". After fine tuning, the models produced the following results:

| Model | Train Acc |Val Acc|
|--|--|--|
| Dog Group Classifier | 92.0% |82.5%|
|Dog Breed Classifier|79.1%|84.0%|

**Baseline Accuracy for Dog Groups**: 10.26%
**Accuracy on unseen data**: 92.5%

#### Conclusions

 1. Both the dog group classifier and dog breed classifier performed well
 2. Performance of dog breed classifier on designer dogs is quite limited but able to predict at least 1 parent

##### Potential Use cases

 1. Kennel Clubs can use the Group Classifier when people want to register dogs to help classify the breed into its correct grouping, streamlining the registration process.
 2. Kennel Clubs can use the Breed Classifier to assess how close of a match a specific dog is to their ideal standard. This can be an interesting use case in dog competitions/shows
 3. The Breed Classifier can also be used to identify possible parentage or origins of a dog of unknown breed or mixed breed. 

##### Future Work

 1. Include model for object detection
 2. Include more than 120 breeds
 3. Adapt model to classify breeds for a different animal eg. Cats
 4. Adapt model to classify newly discovered species into appropriate grouping