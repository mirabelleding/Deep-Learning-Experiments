# Ensemble Learning for Dota 2

A match outcome prediction model for Dota 2 using a stacking ensemble that combines deep neural networks and gradient boosting.

The project explores feature engineering, neural network architecture optimization, and ensemble learning to predict match outcomes from player- and team-level gameplay statistics.

## Methodology

- **Feature Engineering:** Constructed gameplay features capturing lane dominance, gold efficiency, kill/death/assist ratios, and aggregated team statistics.
- **Feature Analysis:** Examined player positioning and gameplay characteristics associated with match outcomes.
- **Neural Network Optimization:** Applied Bayesian hyperparameter optimization using Keras Tuner to explore network depth, hidden-layer dimensions, dropout rates, and learning rates.
- **Gradient Boosting:** Implemented a LightGBM classifier to capture nonlinear relationships and feature interactions.
- **Ensemble Learning:** Combined predictions from the neural network and LightGBM using a logistic regression meta-model.

## Model Architecture

The stacking ensemble consists of three components:

| Component | Implementation |
|---|---|
| Neural Network | Deep feedforward network with Dense layers, Batch Normalization, ReLU activation, and Dropout |
| Gradient Boosting | LightGBM classifier |
| Meta-Model | Logistic Regression |
| Ensemble Strategy | Stacking of model-generated probabilities |

The neural network and LightGBM independently estimate the probability of a Radiant victory. Their predictions are then combined as inputs to the logistic regression meta-model, which produces the ensemble's final probability estimate.

## Evaluation

Model performance is assessed using classification accuracy and ROC AUC, with particular emphasis on the ability to distinguish between Radiant and Dire victories.

The notebook documents hyperparameter tuning, individual model evaluation, ensemble construction, and prediction generation.

## Notebook

[Model Development](model_development.ipynb)