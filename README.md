# Text Classification with Keras

A hands-on notebook exploring text preprocessing and vectorization for sentiment analysis with TensorFlow/Keras. It builds a small custom text vectorizer, uses Keras's `TextVectorization` layer, compares several bag-of-words representations on the IMDb movie-review dataset, and wraps preprocessing plus prediction into a model that accepts raw text.

## Repository name

**Recommended:** `keras-text-classification`

## Repository description

> Hands-on NLP experiments with TensorFlow/Keras: text vectorization, unigram and bigram encoding, TF-IDF, and IMDb sentiment classification.

## Overview

This project explores how text is transformed into numerical features that a neural network can process, and how different feature representations affect sentiment-classification performance.

The notebook covers:

- A simple custom `Vectorizer` for standardizing, tokenizing, encoding, and decoding text.
- Keras `TextVectorization` and custom standardization/splitting functions.
- Loading the IMDb movie-review dataset into training, validation, and test datasets.
- A binary sentiment classifier using a dense neural network.
- Experiments comparing unigram multi-hot encoding, bigram multi-hot encoding, and bigram TF-IDF encoding.
- An inference model that accepts raw strings and performs vectorization as part of the model.

## Experiments and results

The test accuracies recorded in the notebook are:

| Text representation | Test accuracy |
| --- | ---: |
| Unigrams with binary/multi-hot encoding | 88.6% |
| Bigrams with binary/multi-hot encoding | 89.2% |
| Bigrams with TF-IDF encoding | 87.9% |

In these experiments, bigram multi-hot encoding performed best. The results also illustrate that a more sophisticated representation, such as TF-IDF, does not automatically improve performance on every dataset.

*These figures are the results recorded in the notebook and may vary if the notebook is rerun with different library versions, data preparation, or training conditions.*

## Tech stack

- Python
- TensorFlow
- Keras
- Jupyter Notebook / Google Colab
- IMDb movie-review dataset

## Getting started

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/keras-text-classification.git
cd keras-text-classification
```

Replace `<your-username>` with your GitHub username.

### 2. Create and activate a virtual environment

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

macOS/Linux:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
pip install tensorflow jupyter
```

For a more reproducible setup, consider adding a `requirements.txt` with the exact versions that you successfully tested.

### 4. Run the notebook

Start Jupyter:

```bash
jupyter notebook
```

Open `working_with_text_1.ipynb` and run the cells in order.

You can also upload the notebook to Google Colab. The notebook uses `/content/aclImdb` paths for the IMDb dataset, so make sure the dataset is available at the expected location or update those paths for your environment.

## Project structure

```text
keras-text-classification/
├── working_with_text_1.ipynb   # Notebook with implementation and experiments
├── README.md                   # Project overview and instructions
└── requirements.txt            # Optional: pinned dependencies for reproducibility
```

## Key learning outcomes

After working through the notebook, you should be able to:

- Explain why text must be converted into numeric representations before being passed to a neural network.
- Implement a basic vocabulary-based text vectorizer.
- Use Keras `TextVectorization` to create integer, multi-hot, and TF-IDF representations.
- Understand the difference between unigram and bigram features.
- Build and evaluate a binary sentiment classifier.
- Compare model results empirically rather than assuming a more complex representation will perform better.
- Include preprocessing inside a Keras model so inference can begin with raw text.

## Notes and limitations

- This is a learning and experimentation repository, not a production-ready sentiment-analysis service.
- The notebook expects the IMDb dataset to be present in the directory specified by its data-loading cells.
- Training time and results depend on hardware, TensorFlow/Keras versions, and data preparation.
- The notebook currently saves model checkpoints during execution. If you want to keep generated model files, document or version them intentionally; avoid committing large artifacts unintentionally.

## Possible next steps

- Add a `requirements.txt` with tested dependency versions.
- Make dataset setup reproducible instead of relying on a pre-existing local/Colab directory.
- Add a results section with training curves and evaluation metrics.
- Compare the dense bag-of-words baseline with embeddings or recurrent/convolutional text models.
- Add a small prediction script or API after the notebook experiments are stable.

## Learning reference

This notebook follows concepts from *Deep Learning with Python* and is intended for educational use.

## License

No license has been selected yet. If you want others to reuse, modify, or distribute this repository, choose and add a license file before publishing.
