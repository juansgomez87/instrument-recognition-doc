Settings
========

The file *settings.py* contains all the parameters that have been used based on the paper
by Han et al. You can edit this file to the desired parameters, data sets, and paths.

Parameters
----------
- **time_duration:** duration of spectrogram patches in seconds (default: 1).
- **test_overlap:** overlap used when extracting the melspectrograms of the testing data sets (default: 0.5).
- **num_mel_bands:** number of mel bands to use in the linear to mel frequency transformation (default: 128).
- **nb_epochs:** maximum number of epochs to perform during training (default: 400).
- **batch_size:** mini-batch size (default: 128).
- **learning_rate:** learning rate used for optimization during backpropagation (default: 0.001).
- **alpha:** alpha parameter used for leaky rectified linear units (LReLU) (default: 0.33).
- **iter_num:** number of training experiments to perform and evaluate (default: 3).
- **nb_classes:** number of classes for each data set.

- **val_split:** train-validation split (default: 0.85).

Platform
--------
By using the *platform* python package, this script automatically selects the corresponding
path for the data sets and the extracted features.

Create Metadata
---------------
To extract the metadata of the data set and create CSV files, run the command::

	python3 create_encoding.py
	
At this moment, it is necessary to select the data set to be used during training and testing
of the convolutional neural network. Since several experiments have been conducted, please refer
to the thesis in sections **5.4 - 5.7** (Proposed Experiments). The currently available data sets
are the following:

- [-2] **Jazz-Solo** - Jazz data set pre-processed with the solo-accompaniment source separation algorithm *(solo component)*.
- [-1] **JazzDB** - Jazz data set with no pre-processing.
- [0] **IRMAS Multires** - IRMAS data set with three dimensional melspectrograms as input (note: this data set must be used with the *model_multi_res* network).
- [1] **IRMAS** - IRMAS data set with no pre-processing.
- [2] **Monotimbral** - Monotimbral data set with no pre-processing.
- [3] **IRMAS Harm** - IRMAS data set pre-processed with the harmonic-percussive source separation algorithm *(harmonic component)*.
- [4] **Monotimbral Harm** - Monotimbral data set pre-processed with the harmonic-percussive source separation algorithm *(harmonic component)*.
- [5] **Monotimbral Perc** - Monotimbral data set pre-processed with the harmonic-percussive source separation algorithm *(percussive component)*.
- [6] **IRMAS Wind Solo** - IRMAS Wind data set pre-processed with the solo-accompaniment source separation algorithm *(solo component)*.
- [7] **IRMAS Wind** - IRMAS Wind data set with no pre-processing.
- [8] **IRMAS Harm-Perc** - IRMAS data set pre-processed with the harmonic-percussive source separation algorithm *(harmonic and percussive components)* (note: this data set must be used with the *model_two_branch* network).

- [9] **Monotimbral Harm-Perc** - Monotimbral data set pre-processed with the harmonic-percussive source separation algorithm *(harmonic and percussive components)* (note: this data set must be used with the *model_two_branch* network).

Please ignore the second selector at this stage.