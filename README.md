Selective Attention Deocidng for Cochlear Implant Patients
==============================

This repo contains the code for the paper "CNNs Improve Decoding of Selective Attention to Speech in Cochlear Implant Users". 
The paper is currently under review.

Getting started
------------

**Setting up the environment**

I recommend using a virtual conda environment for the repository. [Here's a tutorial](https://uoa-eresearch.github.io/eresearch-cookbook/recipe/2014/11/20/conda/)

Under /conda_env you find .yml files for Linux and Linux with which you you can [create an environment](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-from-an-environment-yml-file).

As a second option there is also  requirements.txt file.

If there are issues with creating the environment from the files try to install libraries in the following order:
1. PyTorch
2. mne-base (Make sure not to install full mne - this takes for ever)
3. gitpython
4. h5py
5. pickleshare

**Installing src as module**

Run `python setup.py install` in the root directory



Workflow
------------
**1. Download hdf5 database file**

The dataset was created with the src/data/create_dataset.py file.
For that you need th raw_input data, which can be made available upon reasonable request.

We provide a dataset as hdf5 file on [zenodo](10.5281/zenodo.10980117).
It contains preprocessed data as well as raw data.
The downloaded file should be put in the data/processed folder.


**2. Model training**

The model training is done with the src/training/train_cnn.py or src/training/train_ridge.py file.

**3. Model evaluation**

Evaluating the models on different window-sized data is done with the src/evaluation/eval_cnn.py or src/evaluation/eval_ridge.py file.
Accuracies as well as reconstruction scores are saved as pickle files, which can be used for further analysis.

The effectiveness of employing an SVM for the classification of the attention state is evaluated with the src/evaluation/eval_svm.py file.

**4. TRF analysis**

Precalcute coeficients using the 'calc_trf_coefs' function from src/evluation/utils.py

**5. Plotting**

All plots were created from jupyter notebooks in the notebooks folder.




--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
