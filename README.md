# # CryptoClustering: README

## Overview
This project applies the K-means clustering algorithm and Principal Component Analysis (PCA) to classify cryptocurrencies based on their price fluctuations across different timeframes. By leveraging Python and data analysis techniques, the project aims to uncover patterns in cryptocurrency market data to better understand trends and clusters.

---

## Installation
### Prerequisites
Ensure you have Python 3.7+ and the following libraries installed:
- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `sklearn`
- `jupyter`

### Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/CryptoClustering.git
   cd CryptoClustering
   ```
2. Create a virtual environment and activate it:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

---

## Project Structure
- **Crypto_Clustering.ipynb**: Main Jupyter Notebook containing the analysis and clustering steps.
- **crypto_market_data.csv**: The dataset with cryptocurrency price fluctuation data.
- **README.md**: Project documentation.

---

## Data Preparation
1. **Load Data**: The dataset `crypto_market_data.csv` is loaded into a Pandas DataFrame and indexed by the `coin_id` column.
2. **Normalization**: The data is normalized using `StandardScaler` from `scikit-learn` to ensure all features have a mean of 0 and a standard deviation of 1.

---

## Analysis Steps
### 1. Find the Best Value for k (Elbow Method)
- A range of k-values (1 to 11) is evaluated using the elbow method.
- The inertia values are computed for each k and plotted to identify the optimal number of clusters.

### 2. Cluster Cryptocurrencies with K-means
- Using the optimal k-value, cryptocurrencies are clustered using the K-means algorithm on the normalized data.
- Results are visualized using a scatterplot of `price_change_percentage_24h` vs. `price_change_percentage_7d`.

### 3. Optimize Clusters with PCA
- PCA is applied to reduce the feature dimensions to three principal components.
- The explained variance of the components is evaluated.
- The elbow method is applied again to the PCA data to determine the best k-value.
- A new K-means model is fitted using the PCA data.
- Results are visualized in a scatterplot of `PC1` vs. `PC2`.

### 4. Determine Feature Weights
- A DataFrame showing the weights of each feature for each principal component is created.
- Insights about the most influential features are documented.

---

## Results
### Key Findings
1. **Optimal k-value**:
   - Original Data: Best k-value found using the elbow method.
   - PCA Data: Best k-value found using reduced dimensions.
2. **Explained Variance**:
   - Total explained variance of the three principal components.
3. **Impact of Dimensionality Reduction**:
   - Effects of using fewer features for clustering.
4. **Feature Weights**:
   - Features with the strongest positive or negative influence on each principal component.

### Visualizations
- Elbow plots for both original and PCA data.
- Scatterplots of clusters using both original and PCA-transformed data.

---

## Deployment
- Push the project to GitHub:
  ```bash
  git add .
  git commit -m "Initial commit"
  git push origin main
  ```

- Provide the GitHub repository link during submission.

---

## Contributing
If you would like to contribute to this project, feel free to fork the repository, create a branch, and submit a pull request.

---

## License
This project is licensed under the MIT License. See the LICENSE file for details.

---

## Acknowledgments
This project is part of the Module 11 Challenge in [Your Bootcamp Name]. The starter code and instructions were provided as part of the course curriculum.

CryptoClustering