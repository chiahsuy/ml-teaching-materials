# ml-teaching-materials
A curated repository of machine learning and data science teaching materials

## Visual Diagnostics for More Informed Machine Learning
Machine learning is ultimately a search for the best combination of features, algorithm, and hyperparameters that result in the best performing model. Oftentimes, this leads us to stay in our algorithmic comfort zones, or to resort to automated processes such as grid searches and random walks. Whether we stick to what we know or try many combinations, we are sometimes left wondering if we have actually succeeded.

By enhancing model selection with visual diagnostics, data scientists can inject human guidance to steer the search process. Visualizing feature transformations, algorithmic behavior, cross-validation methods, and model performance allows us a peek into the high dimensional realm that our models operate. As we continue to tune our models, trying to minimize both bias and variance, these glimpses allow us to be more strategic in our choices. The result is more effective modeling, speedier results, and greater understanding of underlying processes.

Visualization is an integral part of the data science workflow, but visual diagnostics are directly tied to machine learning transformers and models. The [Yellowbrick library](http://www.scikit-yb.org/en/latest/) extends the [scikit-learn](https://scikit-learn.org/stable/) API providing a Visualizer object, an estimator that learns from data and produces a visualization as a result. In this tutorial, we will explore feature visualizers, visualizers for classification, clustering, and regression, as well as model analysis visualizers. We'll work through several examples and show how visual diagnostics steer model selection, making machine learning more informed, and more effective.

## Clone this Repository & Get the Requirements

```bash
git clone git@github.com:icxmedia/ml-teaching-materials.git
cd ml-teaching-materials
pip install -r requirements.txt     
```

## Get the Yellowbrick Datasets

Yellowbrick gives easy access to several datasets that are used for the examples in the documentation and testing. These datasets are hosted in our CDN and must be downloaded for use. Typically, when a user calls one of the data loader functions, e.g. `load_bikeshare()` the data is automatically downloaded if it's not already on the user's computer. However, for development and testing, or if you know you will be working without internet access, it might be easier to simply download all the data at once.

First clone yellowbrick as follows:

```bash
git clone git@github.com:DistrictDataLabs/yellowbrick.git     
cd yellowbrick      
pip install -r requirements.txt     
pip install -e .      
```

The data downloader script can then be run as follows:

```bash
python -m yellowbrick.download
```

This will download the data to the fixtures directory inside of the Yellowbrick site packages. You can specify the location of the download either as an argument to the downloader script (use `--help` for more details) or by setting the `$YELLOWBRICK_DATA` environment variable. This is the preferred mechanism because this will also influence how data is loaded in Yellowbrick.

_Note: Developers who have downloaded data from Yellowbrick versions earlier than v1.0 may experience some problems with the older data format. If this occurs, you can clear out your data cache as follows:_

```bash 
python -m yellowbrick.download --cleanup
```

_This will remove old datasets and download the new ones. You can also use the `--no-download` flag to simply clear the cache without re-downloading data. Users who are having difficulty with datasets can also use this or they can uninstall and reinstall Yellowbrick using `pip`._