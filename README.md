# Song Similarity Analysis

**Our junior year project** on music similarity and clustering using Music Information Retrieval (MIR) and classic ML. The pipeline extracts audio features, reduces dimensionality with t-SNE and clusters songs with Fuzzy C Means to explore how different genres relate in feature space.

---

## Overview

The project analyzes **song similarity** across five music genres by:

1. **Feature extraction** — Using the jAudio MIR toolkit to get a large set of audio descriptors (spectral, MFCCs, rhythm, etc.).
2. **Feature selection** — Pearson correlation to drop highly redundant features (>0.9 correlation).
3. **Dimensionality reduction** — t-SNE to map high-dimensional features to 2D for visualization and to ease the curse of dimensionality.
4. **Clustering** — Fuzzy C-Means to group songs with soft memberships (songs can partly belong to multiple clusters).

**Why Fuzzy C-Means?** It assigns membership degrees to each song per cluster instead of hard labels, so we can see how much a track “belongs” to each genre-like group useful for boundary cases and overlapping styles.

---

## Dataset

- **~250 songs**, 30-second clips.
- **5 genres:** Hip-Hop, Pop, Rock, Carnatic, Jazz (~50 tracks per genre).
- **Features:** ~2256 from jAudio (e.g. spectral centroid, MFCCs, zerocrossing rate, beat histogram, tempo).

Place `ALL_Features.xlsx` in the project root or in the `data/` folder and point the notebook to the correct path (e.g. `data/ALL_Features.xlsx`).

---

## Project Structure

```
Song-Similarity-Analysis-using-ML/
├── README.md
├── requirements.txt
├── Song_Similarity.ipynb    # Main analysis notebook
└── data/
    └── README.md           # Data folder (put ALL_Features.xlsx here)
```

---

## Setup & Run

1. **Clone the repo** (or download and unzip).
2. **Create a virtual environment** (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate   # Windows: venv\Scripts\activate
   ```
3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
4. **Add the dataset:** Place `ALL_Features.xlsx` in the project root or in `data/` and adjust the path in the notebook if needed.
5. **Open and run** `Song_Similarity.ipynb` in Jupyter or VS Code.

The notebook was developed in Google Colab; local paths may need to be updated (e.g. `/content/ALL_Features.xlsx` → `ALL_Features.xlsx` or `data/ALL_Features.xlsx`).

---

## Tech Stack

| Role              | Tool / Library                     |
| ----------------- | ---------------------------------- |
| MIR / features    | jAudio (external)                  |
| Data & stats      | pandas, numpy                      |
| Feature selection | Pearson correlation (pandas)       |
| Dimensionality    | scikit-learn (t-SNE, MinMaxScaler) |
| Clustering        | scikit-fuzzy (Fuzzy C-Means)       |
| Visualization     | matplotlib                         |

---

## Impact: From Junior Year to Final Year & Beyond

This project was my first serious encounter with **machine learning in audio**. It taught me:

- How **MIR features** (spectral, cepstral, rhythmic) represent music in a way algorithms can use.
- The **curse of dimensionality** and why reduction (e.g. t-SNE) and feature selection matter before clustering.
- **Soft clustering** (Fuzzy C-Means) and how it fits music, where genres often overlap.

That foundation directly supported my **final year work** on **machine learning for audio** and eventually led to **publishing a paper** in the same area. 

---

## License

**Feel free to use and adapt for learning; attribution is appreciated.**
