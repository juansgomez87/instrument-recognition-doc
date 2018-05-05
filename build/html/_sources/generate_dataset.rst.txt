Generate data set
=================

Usage
-----
To extract the features for a data set and save the resulting tensors, make sure that the 
ground truth metadata has been previously created by using the *create_encoding.py* script.

Given the amount of processing, this class uses the *multiprocessing* package and it is 
recommended to run on a GPU, using the following command::

	python3 generate_dataset.py

Documentation
-------------

.. toctree::
   :maxdepth: 2

.. automodule:: generate_dataset
   :members: 