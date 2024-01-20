In our run of of the statistics we have found that the best performing pipeline uses both word2vec and node2vec. We will be looking at only the f1-score, since this encapsulates bothe the precision and the recall, and will give us the best idea of the performance of the pipeline. In our metrics, this pipeline has an accuracy for the f1-score of 0.83, a macro avg of 0.74 and a weighted avg of 0.83. When judging the accuracy of the pipelines, we will mostly be looking at macro avg, since class 2 contains very little objects and will get lost in the weighted avg and the accuracy ratings. 
Further more when looking at the metrics we can also point to a second best, this would go to node2vec. Here are the metrics for these pipelines:

node2vec

| accuracy | 0.79 |
| ---- | ---- |
| macro avg | 0.71 |
| weighted avg | 0.79 |

word2vec
accuracy     = 0.83
macro avg    = 0.55
weighted avg = 0.82

Here, if you were to only look at the accuracy it would seem like word2vec is a lot better than node2vec. However, when we look at the macro avg, we see a different story and if we dig into it. It turns out that word2vec was not able to predict any of the class 2 objects correctly. 
The f1-score for node2vec was also not that great. However, it had a precision of 0.86 and the f1-score was 0.41 when predicting class 2 objects. And for word2vec the precision was 0.00 and the f1-score was also 0.00. 
In our opinion it is more important to be able to predict 

In our opinion it is more important to be able to predict all object reasonably well than being fairly good at being able to distinguish between 2 classes and utterly unable to classify the 3rd class. 