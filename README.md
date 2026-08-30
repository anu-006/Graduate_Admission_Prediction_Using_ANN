# Graduate Admission Prediction

A machine learning project that predicts a student's **Chance of Admit** using academic and application-related features.

## Project Overview

This project uses a feed-forward Artificial Neural Network (ANN) built with Keras/TensorFlow to predict the probability of graduate admission.

The notebook works with the `Admission_Predict_Ver1.1.csv` dataset. The dataset contains **500 records and 9 columns**. The `Serial No.` column is removed because it is only an identifier.

### Input Features

- **GRE Score** – GRE examination score
- **TOEFL Score** – TOEFL examination score
- **University Rating** – University rating from 1 to 5
- **SOP** – Strength of Statement of Purpose
- **LOR** – Letter of Recommendation strength
- **CGPA** – Undergraduate CGPA
- **Research** – Whether the applicant has research experience (0/1)

### Target

- **Chance of Admit** – predicted admission probability

## Workflow

The notebook follows these steps:

1. Import Python libraries.
2. Load `Admission_Predict_Ver1.1.csv`.
3. Inspect the dataset using shape, information, missing-value and duplicate checks.
4. Remove `Serial No.`.
5. Strip whitespace from column names.
6. Separate features (`X`) and target (`y`).
7. Perform correlation analysis and exploratory visualizations.
8. Split the data into training and testing sets using an 80/20 split with `random_state=42`.
9. Scale the input features using `MinMaxScaler`.
10. Build a feed-forward ANN using Keras.
11. Train the model for 100 epochs with a validation split of 20%.
12. Predict admission chances on the test set.
13. Evaluate the model using **R² score**.
14. Plot training and validation loss.

## Neural Network Architecture

The ANN in the notebook contains:

- Input layer: 7 features
- Hidden layer: 7 neurons, ReLU
- Hidden layer: 7 neurons, ReLU
- Hidden layer: 7 neurons, ReLU
- Hidden layer: 7 neurons, ReLU
- Hidden layer: 7 neurons, ReLU
- Output layer: 1 neuron, linear activation

The model is compiled with:

- **Loss:** Mean Squared Error (MSE)
- **Optimizer:** Adam
- **Metric:** Accuracy
- **Epochs:** 100

> Note: Since `Chance of Admit` is a continuous regression target, R² is the main evaluation metric used in the notebook. The notebook also specifies `accuracy` during model compilation, although accuracy is generally not an appropriate primary metric for a regression problem.

## Dataset Checks

The notebook reports:

- 500 rows
- 9 original columns
- No missing values
- No duplicate rows
- 7 input features after removing the identifier and target

## Project Structure

```text
Graduate-Admission-Prediction/
│
├── Graduate_Admission_Prediction.ipynb
├── Admission_Predict_Ver1.1.csv
├── requirements.txt
└── README.md
```

## Installation

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd Graduate-Admission-Prediction
```

### 2. Create a virtual environment (recommended)

Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

macOS/Linux:

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

## Run the Project

Open the notebook:

```bash
jupyter notebook Graduate_Admission_Prediction.ipynb
```

Or open it using JupyterLab:

```bash
jupyter lab
```

Make sure `Admission_Predict_Ver1.1.csv` is in the same directory as the notebook before running the cells.

## Model Evaluation

The notebook calculates the **R² score** using:

```python
r2_score(y_test, y_pred)
```

It also visualizes the training and validation loss to observe how the ANN learns over the 100 training epochs.

## Important Note

This is an educational machine learning project based on a relatively small dataset. The predicted admission chance should **not** be treated as an actual university admission decision.

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- TensorFlow / Keras
- Jupyter Notebook

## Author

Add your name and GitHub/LinkedIn profile here.

## License

This project is intended for educational and learning purposes.
