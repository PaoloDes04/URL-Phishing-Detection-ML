# URL-Phishing-Detection-ML
Machine Learning project for URL Phishing Detection using a Random Forest classifier and an interactive Gradio dashboard.

# 🛡️ URL Phishing Detection using Machine Learning

## 📝 Project Description
This project aims to identify fraudulent URLs (phishing) using Artificial Intelligence techniques, overcoming the limitations of traditional security systems based on blacklists or heuristics. 
Phishing is constantly evolving, with "Zero-Day" attacks and domains that remain active for only a few hours, evading traditional controls. This project proposes a proactive approach based on Machine Learning, capable of analyzing the structural features of URLs and blocking previously unseen threats, thereby reducing the impact of the "human factor".

## ✨ Key Features
* **Robust Predictive Model**: Utilization of a *Random Forest* (Ensemble) algorithm to ensure high precision, reduce variance, and mitigate the risk of overfitting.
* **Data Pre-processing**: Data cleaning (removal of irrelevant identifiers) and rigorous splitting into training (80%) and test (20%) sets.
* **Minimizing False Negatives**: Special focus on the Confusion Matrix to minimize instances where a phishing site is mistakenly classified as safe (a critical error in cybersecurity).
* **Interactive Dashboard**: A Web App developed with Gradio that simulates a Firewall/Proxy system. It allows users to visualize the analysis of a URL, displaying the mathematical "feature vector", the AI's prediction, and the threat probability percentage.

## 📊 The Dataset
The model was trained on a comprehensive dataset comprising **10,000 labeled samples** (legitimate and phishing sites).

🔗 **Dataset Source:** [Phishing Dataset for Machine Learning on Kaggle](https://www.kaggle.com/datasets/shashwatwork/phishing-dataset-for-machine-learning)

For privacy and computational speed reasons, the dataset does not contain clear-text URLs, but rather a vector of 48 pre-extracted numerical features that describe the logical structure of the link (e.g., domain length, presence of IP addresses, subdomain levels, etc.).

## 🧠 Machine Learning Model
The chosen algorithm is the **Random Forest Classifier**:
* It consists of a "forest" of **50 decision trees** (`n_estimators=50`).
* Each tree analyzes a random subset of the URL's features, and the final verdict is reached by majority vote.
* **Performance**: The model achieved an overall accuracy of over **96%** on isolated test data, demonstrating excellent generalization capabilities and a minimal rate of false negatives.

## 💻 Graphical Interface (Firewall Simulation)
The project includes a user interface that translates the algorithm's invisible predictions into a practical application. 
*Technical note*: Since the AI evaluates numerical structural data, the interface uses a list of realistic textual URLs (mocks) to visually simulate intercepted traffic. The underlying predictive engine, however, evaluates real mathematical samples extracted from the Test Set, ensuring that the risk percentages shown are real and calculated on the fly using the `predict_proba` function.

## 🛠️ Technologies and Libraries Used
* **Language**: Python
* **Environment**: Google Colab / Jupyter Notebook
* **Data Manipulation & Calculation**: `pandas`, `numpy`
* **Machine Learning**: `scikit-learn` (`RandomForestClassifier`, `train_test_split`, `accuracy_score`, `confusion_matrix`)
* **Data Visualization**: `matplotlib`
* **Web Interface**: `gradio`

## 🚀 How to Run the Project
1. Clone this repository to your local machine: 
    git clone [https://github.com/PaoloDes04/URL-Phishing-Detection-ML.git](https://github.com/PaoloDes04/URL-Phishing-Detection-ML.git)
2.
    Download the dataset Phishing_Legitimate_full.csv from the Kaggle link provided above and ensure it is available in your working directory.
3.
    Open the "esame_phishing.ipynb" file using Google Colab (recommended) or a local Jupyter Notebook environment.
4.
   Upload the .csv file to the execution environment (if using Colab).
5.
  Run the cells sequentially. The final cell will download the Gradio library and launch the graphical interface, providing a public link to test the application directly from your browser.
  Project developed by Paolo Desiderio.
