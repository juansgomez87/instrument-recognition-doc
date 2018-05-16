Installation
============
This implementation uses the *librosa* python package in order to extract the melspectrograms
that are used to train the neural network. *Pandas* is used to organize the results in 
dataframes and evaluate them. *Keras* is the neural networks API used for the implementation
of all the models. Finally, *matplotlib* is used to plot the final results of the performance
metrics obtained. Additionally, the implementation was created in Python 3.

conda
-----

To install please download the environment inst_rec_env.yml and install it::

	conda env create -f inst_rec_env.yml

To activate it, run::

	source activate deep

To visualize the packages installed run::

	conda list
