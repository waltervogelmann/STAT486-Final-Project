## Additional Machine Learning Method: PCA

We were curious if PCA would corroborate our results from SHAP. Given the low amount of features that we have, PCA may not be the best fit for an unsupervised learning method, but we were curious to see its results. K-means clustering is much more appropriate for our data, as will be explained below.

Before running the PCA, we standardized the features we planned to use in the model, since we do not want features with higher numbers to have an outsized influence on our results. After running it, the two most important principal components accounted for approximately 76% of the variance. If one of our features does not significantly contribute to either of these components, then we can reasonably say that it is less useful in explaining variance in the response variable.

![Scree Plot and Variance Explained](PCA_results.png)

All the features in our current model seemed to contribute significantly to the 2 most important principal components. This tells us that those features are able to explain a significant portion of the variance in the response variable, and PCA does not support removing any of them in future analyses.

### Principal Component 1
|--------| Loading | Abs Loading
|--------|---------|-------------|
| Album Tracks | 0.670 | 0.670
| Duration | 0.553 | 0.553 |
| Artist Impact | 0.496 | 0.496

### Principal Component 2
|--------| Loading | Abs Loading
|--------|---------|-------------|
| Artist Impact | 0.766 | 0.670
| Duration | -0.641 | 0.641 |
| Album Tracks | -0.037 | 0.037|


## Additional Machine Learning Method: Clustering

We applied k-means clustering to identify natural groupings of songs based on artist- and track-level characteristics. This method fits our research question because it allows us to explore structure in the data beyond just predicting popularity.

For clustering, we selected the features `artist_impact`, `track_duration_min`, and `album_total_tracks`. The `artist_impact` feature was engineered as a combination of artist popularity and follower count and was the most important predictor in our supervised models, and was a significant contributor in the most important PCs in our PCA analysis. Including it here allows us to directly examine how artist-level influence shapes groups of songs.

We did not include both `artist_popularity` and `artist_followers` separately because they are highly correlated and already captured within `artist_impact`. Using redundant features can negatively affect K-means since it relies on distance calculations.

The additional features, `track_duration_min` and `album_total_tracks`, were included to provide variation beyond artist influence. These represent track-level and album-level characteristics and help ensure that clusters are not based solely on artist strength.

All features were standardized before clustering to ensure that each variable contributed equally. We evaluated different values of k using both the elbow method and silhouette scores. The elbow plot suggested a value around 3–4, while the highest silhouette score occurred at k = 3. Based on this, we selected k = 3 as a balance between cluster quality and interpretability.

### Cluster Summary

| Cluster | Artist Impact | Duration | Album Tracks | Avg Popularity |
|--------|-------------|---------|--------------|----------------|
| 0 | 1357.34 | 3.88 | 14.12 | 59.65 |
| 1 | 655.42 | 2.89 | 8.51 | 42.41 |
| 2 | 1016.05 | 3.22 | 52.55 | 34.24 |

Cluster sizes:
- Cluster 0: 5129 songs
- Cluster 1: 3077 songs
- Cluster 2: 376 songs

The resulting clusters showed clear and interpretable patterns. One cluster consisted of songs from high-impact artists and had the highest average popularity. Another cluster contained lower-impact artists with lower popularity. A third cluster was characterized by larger albums and moderate artist impact, but had the lowest average popularity.

![Track Popularity by Cluster](track_popularity_by_cluster.png)

These results reinforce our supervised findings that artist-level influence is the dominant driver of track popularity, while also revealing additional structure related to album characteristics.


## Final Conclusions

Artist level characteristics are most important in explaining song popularity
- Popular artists with more followers tend to have much more popular
songs

Track level characteristics are less important in explaining song popularity, but
are more within the control of artists
- Longer songs tend to be a bit more popular
- Songs in larger albums tend to be a bit less popularw