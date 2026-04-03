# STAT486-Final-Project

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

---

### Setup

To install required packages, run:

pip install -r requirements.txt

If you are using uv, you can alternatively run:

uv sync
