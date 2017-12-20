# Loan-Repayment-Predictor
Loan Repayment predictions using gradient boosted deicison trees. Model code is in the kaggle.ipynb file. 

The model was tree ensembles used from the XGBoost API, with all of the features being my xi and the status being my yi. 

I specified the max depth of each tree to be 4, the learning rate to 
be .3, and specified the number of classes as well in the parameters. It is sensible that the
decision trees were short, because gradient boosting is based on the fact that the decision trees
are weak learners. 

Tree constraints are important in keeping the learner weak. The learning rate
specifies the weightage because when each tree is added, the contribution of each tree to the 
sum should be weighted.

The way tree boosting works is we have an objective function and the goal is to optimize it. The
way gradient boosting works is that we add the trees one at a time to the model. After
calculating the loss of one weak learner, we follow the gradient descent and add another tree to
the model that reduces the loss. Addition of trees/training stops once the algorithm reaches the
specified number of iterations (since the score isn’t increasing, also, we can specify this). I used
the softmax loss function.

The scores are derived very closely to how we obtain the impurity scores when we evaluate
decision trees. We sum up the gradient and second order gradient statistics on each leaf, then
apply the scoring formula to get the quality score. The smaller scores show the better structures
of trees.
