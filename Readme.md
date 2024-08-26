NASA CMAPSS FD001 Dataset
Overview
The NASA CMAPSS FD001 dataset is widely used for Remaining Useful Life (RUL) prediction of turbofan engines. It contains simulated time-series data representing sensor readings from multiple engines under varying operational conditions. The dataset includes:

Training Data: Time-series data for 100 engines, each running until failure. The data includes 24 sensor measurements and 3 operational settings recorded at each time step.
Test Data: Time-series data for 100 engines where the RUL needs to be predicted. The engines in the test set do not run until failure, making it necessary to predict their RUL based on the provided sensor readings.
Prediction Mechanism
Three neural network models were implemented to predict the RUL of engines in the test dataset:

Vanilla RNN: This model processes the sequential data by maintaining a hidden state that is updated at each time step. However, due to the vanishing gradient problem, it struggled with long sequences.

LSTM (Long Short-Term Memory): LSTM improves on RNN by incorporating mechanisms to retain long-term dependencies via forget, input, and output gates, resulting in better handling of long sequences.

GRU (Gated Recurrent Unit): GRU simplifies the LSTM architecture by combining the forget and input gates into a single update gate, leading to faster training and slightly better performance.

Results
The performance of the models on the FD001 dataset indicated the following hierarchy in terms of prediction accuracy: GRU > LSTM > Vanilla RNN. The GRU model's superior ability to capture long-term dependencies and its efficient training process made it the most effective for this task.
