# Basic Automated Music Recommender

A small educational machine learning project that predicts a music genre from a listener's age and gender using a scikit-learn decision tree.

## Project files

- `music.csv` — the sample dataset (`age`, `gender`, and `genre`).
- `Training and testing a model.ipynb` — splits the data and reports holdout accuracy.
- `Visualizing Decision trees.ipynb` — trains a tree and exports `music-recommender.dot`.
- `preview.svg` — rendered decision tree diagram.
- `Model persistence.ipynb` — trains on the full dataset and saves `music-recommender.joblib`.
- `Model executing.ipynb` — loads the saved model and predicts genres for example inputs.

## Setup

Use Python 3.10 or newer. From this folder, install the dependencies and start Jupyter:

```bash
python -m venv .venv
# Windows PowerShell: .venv\Scripts\Activate.ps1
# macOS/Linux: source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter notebook
```

## Run the notebooks

Open the notebooks in this order:

1. `Training and testing a model.ipynb` to see a train/test split and accuracy score.
2. `Visualizing Decision trees.ipynb` to regenerate `music-recommender.dot`.
3. `Model persistence.ipynb` to create or refresh `music-recommender.joblib`.
4. `Model executing.ipynb` to load the saved model and run sample predictions.

Run the persistence notebook before the execution notebook if the saved model file is missing. The gender values are encoded as `0` and `1` in the dataset; consult the dataset's original source for their intended meanings.

## Challenges and what I learned

The main challenge was getting a stable accuracy score from a very small dataset. Early train/test splits produced scores that varied substantially (roughly 20%–50%). Changing how much data is used for training can change the score, but with only 18 rows a higher score on one split does not show that the model will perform better on new listeners. This project helped me practice preparing data, splitting it for evaluation, training and persisting a decision tree, and visualizing its decisions.

## Notes

This is a learning example, not a reliable recommendation system. The included dataset has only 18 rows, so a train/test accuracy score can vary with the random split and should not be treated as evidence of real-world performance. The model can memorize this small dataset.

The dataset is included in this repository. Add the original dataset source and license here if you know them; they were not recorded in the project files.

## Dependencies

See [`requirements.txt`](requirements.txt).
