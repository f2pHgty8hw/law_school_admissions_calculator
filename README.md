# Law School Admissions Calculator

## About

This app is targeted at potential law school applicants and is designed for both mobile and desktop use. The user inputs data about himself/herself into the app, and then the app employs a logit with two-way fixed effects (year and school) to estimate the user's probability of admission to a chosen law school. The model was first estimated in the file `model_estimation.ipynb`, after which it was saved as a pickle file. (You can find measures of model accuracy in that file as well; I elected not to include this information in the final product, however, because I didn't think most users would be very interested.)

The data used to train the model were self-reported admissions data from the website [LSD.Law](https://www.lsd.law/). I spent considerable effort cleaning, merging, and appending data to construct the final data set, as well as conducting validity checks against aggregated official data reported by the American Bar Association. Moreover, I tested a variety of models using *k*-fold and time-series cross-validation techniques before arriving at my model. Please see [this repository](https://github.com/noahblakesmith/law_school_admissions) for code related to model training and selection.

## Setup

Create and activate a virtual environment
```sh
conda create -n calc_env python
conda activate calc_env
```

Install package dependencies
```sh
cd ~/law_school_admissions_calculator # Navigate to the root directory
pip install -r requirements.txt
```

## Usage

Run the web app locally
```sh
python routes.py
```

Navigate to the URL using your browser of choice
```sh
http://127.0.0.1:5000/input
```

## Testing

```sh
python -m pytest -v
```
