# Bitcoin_prediction
This project focuses on predicting Bitcoin price movements using historical time-series data collected from an online database, starting from January 2020 onward. The goal is to model complex temporal dependencies in cryptocurrency markets by combining deep learning–based sequence models with statistical time-series techniques.


Bitcoin prices exhibit strong non-linearity, volatility, and long-term dependencies. To address these challenges, this project leverages:

1-Feature-engineered financial time-series data

2-A hybrid modeling perspective combining Markov Autoregression and Advanced LSTM architectures

3-Robust training strategies for stable convergence and generalization


Modeling Approach
1. Data Handling
A custom dataset class named TimeSeriesDataset is implemented to:
Load and preprocess historical Bitcoin price data
Generate sliding time windows suitable for sequence modeling
Handle normalization and feature selection

2. Advanced LSTM Architecture
The core predictive model is an AdvancedLSTM, which extends the standard LSTM (Long Short-Term Memory) architecture to better capture complex temporal patterns.
Advanced LSTM variants incorporate several enhancements over vanilla LSTM models, including:

Peephole Connections – enabling gates to access cell state information

Forget Gate Bias Initialization – improving long-term memory retention

Coupled Input–Forget Gates and GRU-inspired mechanisms – reducing redundancy and improving efficiency

Layer Normalization – stabilizing training dynamics

Recurrent Dropout & Zoneout – mitigating overfitting while preserving temporal structure

Bidirectional and Stacked Multi-layer LSTMs – capturing both past and future context and increasing model capacity

These improvements significantly enhance performance on complex sequential prediction tasks such as financial time-series forecasting.

3. Statistical Component
In addition to deep learning, Markov Autoregression is employed to model regime-switching behavior and probabilistic state transitions, which are common in cryptocurrency markets.

Training Configuration

Epochs: 80

Optimizer: AdamW (Adam with decoupled weight decay)

Learning Rate Scheduler: ReduceLROnPlateau

Automatically reduces learning rate when validation performance stagnates

Loss Function: BCELoss


Model Abstractions

To improve modularity and scalability, additional classes are implemented:

AdvancedLSTM_Logits – Handles raw output logits for downstream processing

Wrapper – Encapsulates model inference, evaluation, and prediction pipelines

This design allows for cleaner experimentation and easier future extensions.

Results

After training, the model produces Bitcoin price predictions based on learned temporal patterns. The final outputs demonstrate the ability of advanced recurrent architectures to capture both short-term fluctuations and longer-term trends in cryptocurrency markets.
