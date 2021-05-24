# Data analysis plans.
For **each** of the four scenarios below, answer the following questions. Please explain where your targets/rewards would come from (2) , how you would make your inputs numerical (3), and a bit of your reasoning on ethical issues (6). Other questions do not need explanation.
1. What type of machine learning problem (regression, classification, clustering, generation, reinforcement learning) do you think this is?
2. If this is a supervised problem, what will you use as your targets (aka labels)? If it is reinforcement learning, what will you use as your rewards? If it is unsupervised, just say “unsupervised”.
3. What processing do you need to do to your input data?
4. What type(s) of model(s) would you try? You may need to combine models. Remember to start with the simplest thing that might work! Types of models we’ve talked about are linear regression, decision trees, random forest, logistic regression, naive bayes, support vector machines, K-means, DBSCAN, hierarchical clustering, fully connected neural networks, convolutional neural networks, recurrent neural networks, generative adversarial networks, deep Q learning, and evolutionary methods.
5. What validation metric(s) would you use to decide how well you’re doing?
6. What ethical challenges do the data collection, creation, and/or use of this model create? If you feel there aren’t any, just say “None”.

## Scenarios:
1. You want your model to learn to play [Frogger](https://en.wikipedia.org/wiki/Frogger%22%20%5Ct%20%22_blank) .
	1. Reinforcement learning.
	2. The rewards would be the number of points (which the game calculates).
	3. The game would have to be converted into a 2D array of numbers (grid) where a number represents the element (player, obstacle, etc.) at the given position. As an example, if the first element of the first array is a 0, that could mean that a log is in the top left corner.
	4. Deep Q learning with a fully connected NN.
	5. Regret for validation.
	6. One possible ethical challenge would be the use of this model to cheat when playing Frogger competitively. 

2. You would like a model to write tweets in the style of a particular author.
	1. Generative.
	2. Unsupervised.
	3. Byte pair encoding, tokenization, and padding.
	4. GAN, RNN for the generator, RNN for the discriminator.
	5. Human evaluation would be used as validation. 
	6. People could be tricked into believing the author actually wrote the fake tweet, could be used for impersonation. 

3. A company would like to be able to predict the next months’ sales for each of its products. You have a dataset that the company has collected for many years, with data for a particular product on a particular month in each row. Each row contains the number of sales for the month, the number of sales from the previous month, the average rating (1-5) of the product in the previous month, the number of reviews in the previous month, the product type (e.g. “toaster”, “coffee maker”, “rice cooker”), its price the previous month, and its price for the current month.
	1. Regression.
	2. This is a supervised problem, the labels used would be the number of sales for a month.
	3. Nothing should be done to the # of sales (no normalization, as there is no max # of sales), nothing should be done to the average rating (because an average rating of 5 is better than 1), the product type should be OHE, nothing should be done to the price.
	4. Dense NN.
	5. R^2 for validation. 
	6. None.

4. You would like to predict the presence of a certain disease using chest x-ray data. You have a lot of x-ray images, a small amount of which have been labeled as having the disease or not having the disease. The rest of the images are unknown as to whether or not the person has the disease.
	1. Classification.
	2. Semi supervised, the labels are the already provided labels and the pseudo-labels that will be generated. 
	3. Potentially down sampling, and gray scale (if stored in RGB).
	4. CNN (+ maybe label propagation).
	5. F-score for validation. 
	6. Model explainability: if this model were to be actually used for determining if someone had the disease, people may be uncomfortable with an algorithm diagnosing them instead of a doctor. 
