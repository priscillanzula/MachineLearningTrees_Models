 How Each Learns (Simplified View)
✅ AdaBoost

Start with equal sample weights.

Train a weak model (tree stump).

Increase weights of misclassified samples.

Train next model using new weights.

Final prediction = weighted sum of weak learners.

➡️ Focus = sample weighting (not gradient-based).


✅ GradientBoostingRegressor

Train first model on true y.

Compute residuals (errors).

Fit new tree to predict residuals.

Add the new tree to the model with a learning rate.

Repeat until convergence.

➡️ Focus = reducing residuals via gradient descent.


✅ XGBoost

Same concept as Gradient Boosting but adds:

Gradient and second-order derivatives (Hessian) for better optimization.

Regularization (L1, L2) → controls overfitting.

Handles missing values automatically.

Parallel tree building + pruning by “gain”.

➡️ Focus = efficiency + regularization.


✅ LightGBM

Improvements over XGBoost:

Histogram-based splitting: bucket continuous features into bins → faster.

Leaf-wise tree growth: expand the leaf that reduces loss the most (not level by level).

Categorical feature support: built-in.

➡️ Focus = speed + scalability + accuracy for large datasets.


✅ CatBoost

CatBoost = “Categorical Boosting”.

Uses ordered boosting (avoids target leakage from shuffling).

Oblivious trees: all trees have the same split structure, making it faster and more regularized.

Built-in categorical encoding (no need for one-hot).

➡️ Focus = categorical handling + stability + less tuning.


##Which One to Use?

1. Small, clean dataset-	AdaBoost or GBR
2. Large dataset, numeric-heavy	- LightGBM
3. Mixed data (numeric + categorical)	- CatBoost
4. Needs very fine control / custom loss -	XGBoost
5. Limited compute resources	- LightGBM
6. Fast, high-accuracy default	- CatBoost