# Machine Learning

### Supervised Learning

**1. Regression and Classification Problems**
- **Regression:** Predicting a continuous output (e.g., predicting house prices).
- **Classification:** Predicting a categorical output (e.g., spam detection).

**2. Simple Linear Regression**
- **Definition:** Models the relationship between a dependent variable $\ y $ and an independent variable $\ x $.
- **Equation:** $\ y = \beta_0 + \beta_1 x $
- **Implementation in Python:**
  ```python
  from sklearn.linear_model import LinearRegression
  model = LinearRegression()
  model.fit(X, y)
  ```

**3. Multiple Linear Regression**
- **Definition:** Extends simple linear regression to multiple independent variables.
- **Equation:** $\ y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + \ldots + \beta_n x_n $

**4. Ridge Regression**
- **Definition:** Linear regression with L2 regularization to prevent overfitting.
- **Equation:** $\ \min ||y - X\beta||^2_2 + \lambda||\beta||^2_2 $
- **Implementation in Python:**
  ```python
  from sklearn.linear_model import Ridge
  model = Ridge(alpha=1.0)
  model.fit(X, y)
  ```

**5. Logistic Regression**
- **Definition:** Used for binary classification problems.
- **Equation:** $\ P(y=1) = \frac{1}{1 + e^{-(\beta_0 + \beta_1 x_1 + \ldots + \beta_n x_n)}} $
- **Implementation in Python:**
  ```python
  from sklearn.linear_model import LogisticRegression
  model = LogisticRegression()
  model.fit(X, y)
  ```

**6. K-Nearest Neighbour (KNN)**
- **Definition:** Classifies a data point based on the majority class among its k-nearest neighbors.
- **Implementation in Python:**
  ```python
  from sklearn.neighbors import KNeighborsClassifier
  model = KNeighborsClassifier(n_neighbors=3)
  model.fit(X, y)
  ```

**7. Naive Bayes Classifier**
- **Definition:** Based on Bayes' theorem, assumes independence between predictors.
- **Implementation in Python:**
  ```python
  from sklearn.naive_bayes import GaussianNB
  model = GaussianNB()
  model.fit(X, y)
  ```

**8. Linear Discriminant Analysis (LDA)**
- **Definition:** Finds a linear combination of features that separates two or more classes.
- **Implementation in Python:**
  ```python
  from sklearn.discriminant_analysis import LinearDiscriminantAnalysis
  model = LinearDiscriminantAnalysis()
  model.fit(X, y)
  ```

**9. Support Vector Machine (SVM)**
- **Definition:** Finds the hyperplane that best separates the classes in the feature space.
- **Implementation in Python:**
  ```python
  from sklearn.svm import SVC
  model = SVC(kernel='linear')
  model.fit(X, y)
  ```

**10. Decision Trees**
- **Definition:** Tree-like model of decisions and their possible consequences.
- **Implementation in Python:**
  ```python
  from sklearn.tree import DecisionTreeClassifier
  model = DecisionTreeClassifier()
  model.fit(X, y)
  ```

**11. Bias-Variance Trade-off**
- **Definition:** Trade-off between the model's ability to generalize (low variance) and its ability to fit the training data (low bias).

**12. Cross-Validation Methods**
- **Leave-One-Out (LOO) Cross-Validation:** Uses a single observation from the original sample as the validation data, and the remaining observations as the training data.
  ```python
  from sklearn.model_selection import LeaveOneOut
  loo = LeaveOneOut()
  for train_index, test_index in loo.split(X):
      X_train, X_test = X[train_index], X[test_index]
      y_train, y_test = y[train_index], y[test_index]
  ```

- **K-Folds Cross-Validation:** Splits the data into k equally-sized folds, trains the model k times, each time using a different fold as the validation data.
  ```python
  from sklearn.model_selection import KFold
  kf = KFold(n_splits=5)
  for train_index, test_index in kf.split(X):
      X_train, X_test = X[train_index], X[test_index]
      y_train, y_test = y[train_index], y[test_index]
  ```

**13. Multi-Layer Perceptron (MLP)**
- **Definition:** A class of feedforward artificial neural network (ANN).
- **Implementation in Python:**
  ```python
  from sklearn.neural_network import MLPClassifier
  model = MLPClassifier(hidden_layer_sizes=(100,), max_iter=300)
  model.fit(X, y)
  ```

**14. Feed-Forward Neural Network**
- **Definition:** Type of neural network where connections between nodes do not form a cycle.
- **Structure:** Input layer, hidden layers, and output layer.

### Unsupervised Learning

**1. Clustering Algorithms**

**K-Means/K-Medoid:**
- **K-Means:** Partitions the data into k clusters by minimizing the variance within each cluster.
  ```python
  from sklearn.cluster import KMeans
  kmeans = KMeans(n_clusters=3)
  kmeans.fit(X)
  ```
  
- **K-Medoid:** Similar to K-Means but uses actual data points as cluster centers.

**2. Hierarchical Clustering**
- **Definition:** Builds a hierarchy of clusters using either a bottom-up or top-down approach.
- **Types:**
  - **Single-Linkage:** The distance between two clusters is defined as the minimum distance between any single data point in the first cluster and any single data point in the second cluster.
  - **Multiple-Linkage:** Can be complete (maximum distance between clusters) or average (average distance between clusters).

**3. Dimensionality Reduction**

**Principal Component Analysis (PCA):**
- **Definition:** Technique to reduce the number of features by transforming the original variables into a new set of variables (principal components) that are uncorrelated and capture the most variance in the data.
- **Implementation in Python:**
  ```python
  from sklearn.decomposition import PCA
  pca = PCA(n_components=2)
  X_reduced = pca.fit_transform(X)
  ```
