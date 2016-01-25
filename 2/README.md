Dependencies
:
This Implementation builds heavily upon the [GPstuff toolbox](http://becs.aalto.fi/en/research/bayes/gpstuff/) for Mathworks **Matlab** (or Octave). It is our in-house-developed software package for Gaussian process modeling. All codes were tested in Matlab 8.2.0.701 (R2013b), and GPstuff version 4.5 (release 2014-07-22, available online, and distributed under the GNU General Public License) in Ubuntu Linux.


Code description
:
All files are written in Mathworks Matlab, and running the scripts require installation of the \gpstuff\ toolbox. The following files are provided:

* `settings.m` (Matlab)
  1. Specifies the path to the training data (`TRAIN_DATA_PATH`), test data (`TEST_DATA_PATH`), model (`MODEL_PATH`), and submission output directories (`SUBMISSION_PATH`). This is the only place that specifies the paths to these directories.
  2. The GPstuff toolbox is added to the Matlab path with appropriate initializations.
* `train.m` (Matlab)
  1. Read training data from `TRAIN_DATA_PATH` (specified in `settings.m`).
  2. Do the normalization steps.
  3. Set up and train the GP classifier (Note that the random number generator seed is not specified).
  4. Save the model under `MODEL_PATH` (specified in `settings.m`).
* `predict.m` (Matlab)
  1. Read the training and test data from `TRAIN_DATA_PATH` and `TEST_DATA_PATH`, and do the normalization steps.
  2. Load the model from `MODEL_PATH`.
  3. Use the model to make predictions on new samples.
  4. Save the predictions to `SUBMISSION_PATH`.


Follow these steps :

* Download and unpack the [GPstuff toolbox](http://becs.aalto.fi/en/research/bayes/gpstuff/). Additional speedup can be gained by mexing (see the toolbox documentation, or just run `matlab_install.m`).
* Modify (to set the paths) and run `setup.m` in Matlab.
* Run `train.m` in Matlab to train the GP classifier.The model is saved under the path specified in `setup.m`.
* Run `predict.m` in Matlab to predict using the GP classifier. The model output is stored under the path specified in `setup.m`.


