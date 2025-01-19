# Refactoring Analysis for Model and Feature Prioritization

## Introduction

This document presents a refactoring analysis to perform in the nature of the models and features being prioritized at this juncture. The goal is to enhance the prediction capabilities of the reinforcement learning project by integrating advanced codec tooling and optimizing the existing models and features.

## Current Situation

- The project includes various reinforcement learning algorithms like DQN, PPO, and Dueling DQN in `code/libs/agents.py`.
- The `train` class in `code/candle_trader.py` initializes the model with specific input shapes and features.
- The project includes baseline models in `code/libs/baseline.py`.
- The project lacks integration of advanced codec tools for prediction.
- The project does not implement varying length streams of time series data for capturing different temporal patterns.

## Proposed Changes

### 1. Integration of LSTM/RNN Layers

- **Files Affected**: `code/libs/models.py`
- **Description**: Add LSTM or RNN layers to `DQNNet` and `DuelingNet` classes for better context understanding. Modify the `forward` method in the model classes to include both CNN and LSTM/RNN layers.

### 2. Semantic and Sentiment Data Processing

- **Files Affected**: `code/libs/models.py`
- **Description**: Add a new module to process semantic and sentiment data and integrate it with the existing model.

### 3. Optimization of Data Loading and Preprocessing

- **Files Affected**: `code/libs/data.py`, `code/libs/ohlc_data.py`
- **Description**: Optimize the data loading and preprocessing pipeline to reduce IO bottlenecks. Add support for varying length streams of time series data to capture different temporal patterns.

### 4. Hyperparameter Tuning

- **Files Affected**: `code/libs/utilities.py`
- **Description**: Add new hyperparameters for controlling the learning rate, batch size, and other parameters.

### 5. Implementation of Ensemble Methods

- **Files Affected**: `code/libs/ensemble.py`
- **Description**: Implement ensemble methods to combine multiple models for improved prediction accuracy.

### 6. Higher Frequency Data and Granular Features

- **Files Affected**: `code/candle_trader.py`
- **Description**: Initialize the model with higher frequency data and more granular features. Create a codec bracket mode which provides a buy and sell threshold for every frame of input.

### 7. Data Augmentation and Caching

- **Files Affected**: `code/main.py`
- **Description**: Add data augmentation and caching techniques to the `transform` function to improve model performance.

### 8. Updating Agent Classes

- **Files Affected**: `code/libs/agents.py`
- **Description**: Update the `DQN`, `DoubleDQN`, and `DuelingDQN` classes to use the new LSTM/RNN layers in the models.

### 9. Architectural Diagrams

- **Files Affected**: `README.md`
- **Description**: Insert a meticulous details mermaid architectural diagram of the original architecture. Add a new heading with another meticulous proposed migration architectural diagram. Add at least 3x nodes to all these mermaid graphs.

### 10. Grey Paper Outline

- **Files Affected**: `TODO.md`
- **Description**: Outline a new grey paper of this plan in research.

## Conclusion

The proposed refactoring aims to enhance the prediction capabilities of the reinforcement learning project by integrating advanced codec tooling, optimizing data processing, and leveraging ensemble methods. By implementing these changes, the project will be better equipped to handle varying temporal patterns and improve overall prediction accuracy.
