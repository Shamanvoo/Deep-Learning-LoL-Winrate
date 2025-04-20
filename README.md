# Deep-Learning-LoL-Winrate

# League of Legends Worlds 2024 Player Win Prediction

## Project Overview

This project analyzes individual player statistics from the 2024 League of Legends World Championship to predict a player's probability of winning a game. The core aim is to determine whether specific early-game performance metrics can reliably indicate a player's likelihood of victory. By leveraging machine learning—specifically, a fully connected feedforward neural network—the project explores how a player's in-game advantages translate to match outcomes.

## Key Features

- **Dataset:** Player-level statistics from the 2024 League of Legends World Championship.
- **Target:** Predicting the probability that a player wins a game.
- **Features Used:**
  - **Gold Difference at 15 minutes (GD@15):** Measures how much more (or less) gold a player has compared to their direct opponent at 15 minutes.
  - **Creep Score Difference at 15 minutes (CSD@15):** Difference in minions killed at 15 minutes relative to the lane opponent.
  - **Experience Difference at 15 minutes (XPD@15):** Difference in experience points at 15 minutes compared to the opponent.
- **Model:** Feedforward neural network with two hidden layers.
- **Evaluation:** Cross-validation for robust performance measurement.

## Motivation

Early-game advantages are often seen as predictors of match success in competitive League of Legends. This project investigates whether quantitative differences in gold, creep score, and experience at the 15-minute mark can serve as strong predictors for individual player victory. The findings can provide insights for analysts, coaches, and players aiming to optimize early-game strategies.

## Methodology

**Data Preparation**
- The dataset is preprocessed to extract the relevant features (GD@15, CSD@15, XPD@15) and the win/loss outcome for each player.
- Data is split using `train_test_split`, with an initial test set set aside to evaluate the model before training[1].

**Model Architecture**
- The model is a sequential neural network with the following structure:
  - Input layer: 3 features (GD@15, CSD@15, XPD@15)
  - Hidden layer 1: 18 neurons, activation function (not specified, but typically ReLU)
  - Hidden layer 2: 14 neurons
  - Output layer: 1 neuron (probability of win), likely with sigmoid activation[1]
- Total parameters: 353 (all trainable)[1]

**Training and Evaluation**
- The model's initial performance is evaluated using the untrained weights to establish a baseline.
- Cross-validation (5-fold) is implemented:
  - For each fold, the model is re-initialized and trained for 50 epochs.
  - Accuracy is measured on the validation fold and averaged across all folds for a robust estimate[1].

## Usage

1. **Clone the repository and install dependencies.**
2. **Prepare the dataset** in the required format (see the notebook for details).
3. **Run the Jupyter notebook** to train and evaluate the model.
4. **Interpret the results** to understand how early-game metrics affect win probability.

## Results

- The model provides a probability score for each player, indicating their likelihood of winning based on their early-game performance.
- Cross-validation ensures the reported accuracy is a reliable estimate of real-world performance.
- Baseline (untrained) model performance is also reported to contextualize improvements after training.

## Contributing

Contributions and suggestions are welcome! Please open an issue or submit a pull request.