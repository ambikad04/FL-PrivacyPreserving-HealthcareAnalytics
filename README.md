# Privacy Preserving Healthcare Analytics

This project shows how **Federated Learning (FL)** works, where multiple clients train models on their private data without sharing it with a central server. The project also adds **personalization**, allowing the global model to better adapt to the unique data of each client. This makes FL more practical for real-world applications like healthcare, finance, or mobile devices.

---

## Features

- **Federated Learning Workflow**: Simulates the entire FL process, including data creation, local training, and global model updates.
- **Personalized Global Model**: A personalization factor is used during the model update process, helping the global model to perform well on all clients’ data while keeping their unique characteristics.
- **Synthetic Data**: Simulates datasets for multiple clients, making it easier to test FL without using real-world data.
- **Model Evaluation**: Tests and reports the accuracy of the global model after each round of learning.

---

## Model Details

### Fully Connected Neural Network (FCModel)
The project uses a simple neural network for **binary classification** (e.g., predicting yes or no). The model is designed for tabular data and has the following structure:

1. **Input Layer**:  
   Takes input features (e.g., patient health metrics or user preferences).  
   Example: If there are 10 features in the dataset, the input layer has 10 neurons.

2. **Hidden Layers**:  
   - **Layer 1**: 64 neurons with ReLU activation.  
   - **Layer 2**: 32 neurons with ReLU activation.

3. **Output Layer**:  
   - 1 neuron with a sigmoid activation to produce probabilities for binary classification.

### Key Model Characteristics:
- **Lightweight**: The model is simple and fast to train, making it ideal for federated learning.
- **Binary Classification**: Designed for tasks with two possible outcomes, such as detecting fraud or predicting a disease.

---

## Installation

### Prerequisites
- Python 3.8 or higher
- Libraries: PyTorch, NumPy, scikit-learn

### Installation Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/ambikad04/FL-PrivacyPreserving-HealthcareAnalytics.git
   cd FL-PrivacyPreserving-HealthcareAnalytics
   ```

2. Install the required libraries:
   ```bash
   pip install -r requirements.txt
   ```

---

## Usage

1. Run the main script to start federated learning:
   ```bash
   python main.py
   ```

2. Customize parameters in the script:
   - **Number of Clients**: Change the number of clients to simulate more or fewer devices.  
   - **Rounds**: Adjust the number of federated learning rounds (e.g., 5 or 20).  
   - **Personalization Factor**: Modify how much the global model adapts to each client’s data.  

---

## Workflow

1. **Data Generation**:  
   Synthetic data is created with features and labels. The data is split into multiple clients to simulate decentralized learning.

2. **Local Model Training**:  
   Each client trains its own model using its local data. This ensures data privacy since no data is shared.

3. **Global Model Aggregation**:  
   After local training, all clients send their model updates (weights) to the server. The server combines them using **federated averaging**.

4. **Personalization**:  
   During aggregation, a personalization factor ensures the global model balances general knowledge and client-specific insights.

5. **Evaluation**:  
   The global model is tested on a separate dataset to measure its performance after each round.

---

## Example Output

Here’s an example of what you’ll see when running the script:

```
Round 1
Test Accuracy: 80.00%
Round 2
Test Accuracy: 82.50%
Round 3
Test Accuracy: 85.00%
...
Training complete.
```

The accuracy improves as more rounds are completed, showing the effectiveness of federated learning and personalization.

---

## Why Personalization Matters

In real-world scenarios, each client’s data can be very different. For example:
- A healthcare application might have different patient data across hospitals.
- A mobile device app might have user behavior data that varies by location.

Personalization allows the global model to work better for individual clients while still benefiting from the combined knowledge of all clients.

---

## Results

- **Improved Accuracy**: The global model becomes more accurate after multiple rounds of training.  
- **Adaptability**: The personalization factor helps the model adjust to each client’s unique data.  
- **Privacy**: Data stays local, ensuring that sensitive information is never shared.

---

## Contributing

We welcome contributions! If you have ideas for improving the code or adding new features, fork the repository, make changes, and submit a pull request.

---

## Acknowledgments

This project is inspired by the principles of **Federated Learning** and explores how personalization can make it more effective in real-world applications.

