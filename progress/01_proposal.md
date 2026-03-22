# STAT 486 Final Project Proposal

## Candidate Project Ideas (AI-Generated)

### Idea 1: Song Popularity Prediction + Clustering

This project aims to predict a song’s popularity using track-level and artist-level metadata (e.g., artist popularity, followers, duration, album characteristics). A supervised regression model will be used to predict popularity, while clustering (e.g., k-means) will group songs into meaningful categories based on shared features. This allows us to both predict outcomes and uncover structure in the data.

### Idea 2: Song Success Classification

This project frames popularity as a classification problem by categorizing songs into “high” vs. “low” popularity groups. Supervised classification models (e.g., logistic regression, random forest) will be used, while dimensionality reduction (PCA) or clustering will help reveal underlying structure in the feature space.

### Idea 3: Artist vs. Track Influence on Popularity

This project investigates whether song popularity is driven more by artist-level features (e.g., followers, artist popularity) or track-level features (e.g., duration, album type). Supervised regression models will quantify predictive power, while feature importance methods and clustering will help interpret which factors matter most.

---

## AI Reflection

Using AI helped us quickly explore multiple directions within our general project area of music analytics. It was especially helpful for generating ideas that combine supervised learning with another machine learning method, which is a requirement of this project. Initially, we considered more complex ideas such as recommendation systems, but AI helped us recognize that those approaches may be difficult given data availability and time constraints. Through iteration, we refined our focus toward predicting song popularity with clustering, which is both feasible and meaningful. AI primarily helped us narrow scope and identify a project that balances technical depth with practicality.

---

## AI Interaction Excerpt

**Prompt:**
"I am working on a machine learning project using music data. Can you suggest a project idea that combines supervised learning with another method and is practical for a semester?"

**Response (excerpt):**
"A strong option would be predicting song popularity using available metadata and then applying clustering to group songs into categories. This approach allows you to use both regression and unsupervised learning while keeping the project manageable."

---

## Final Project Plan

### Research Question

How accurately can we predict a song’s popularity using artist-level and track-level metadata, and what underlying groupings of songs can be identified through clustering?

---

### Target Variable

The primary target variable will be:

- `track_popularity` (continuous variable on a 0–100 scale)

This defines the supervised learning task as a regression problem.

---

### Dataset

**Primary Dataset:**

We will use the following dataset:

[Spotify Global Music Dataset (2009–2025)](https://www.kaggle.com/datasets/wardabilal/spotify-global-music-dataset-20092025)

This dataset contains track-level and artist-level metadata, including:

- track popularity
- artist popularity
- artist followers
- track duration
- album characteristics

This dataset is already cleaned and well-structured, making it suitable for modeling.

**Backup Dataset:**

A secondary track-level dataset with similar variables (e.g., track popularity, duration, and artist features) will be used as a backup in case issues arise with the primary dataset.

**Potential Extension:**

If needed, we may incorporate additional Spotify audio features (e.g., danceability, energy, valence) from publicly available datasets to enrich the feature set.

---

### Feasibility (Time, Compute, Scope)

This project is feasible within the 4–5 week course timeline:

- The dataset is already cleaned, reducing preprocessing time.
- The models we plan to use (linear regression, regularized regression, tree-based models) are standard and computationally efficient.
- Clustering methods such as k-means are lightweight and fast.
- No large-scale compute resources or GPUs are required.

The scope is appropriate and allows us to focus on interpretation and reproducibility rather than excessive model complexity.

---

### Ethical and Legal Considerations

- The dataset is publicly available on Kaggle and is commonly used for educational purposes.
- The data does not contain personally identifiable information (PII).
- There are minimal ethical concerns associated with using this dataset.

One limitation is that Spotify popularity metrics may reflect platform-specific biases (e.g., promotion, algorithmic exposure). These biases will be acknowledged when interpreting results.

---

### Planned Machine Learning Methods

#### Supervised Learning

We plan to implement and compare multiple models:

- Linear Regression (baseline)
- Regularized Regression (Ridge and/or Lasso)
- Random Forest or Gradient Boosting

These models will be evaluated using:

- RMSE (Root Mean Squared Error)
- R² (coefficient of determination)

We will use a train/validation split or cross-validation to ensure proper evaluation.

---

#### Additional ML Method

We will implement:

- **Clustering (k-means)**

This will allow us to:

- Identify groups of similar songs
- Explore whether clusters correspond to different popularity levels
- Provide insights beyond supervised predictions

---
