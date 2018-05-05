Evaluate the Performance
========================

Usage
-----
After creating the tensors that will be used to train and test the neural network, it is
possible to start training the neural network. Different models and optimizers can be selected
by command-line argument parsing. Additionally, the **class_weight** implementation from *Keras*
can be activated. This was implemented to take into account the uneven distribution of samples
across instrument labels. Given that this did not result in improvements with the IRMAS data
set, the use of this feature is optional in argument parsing.

Available models are: **model_baseline**, **model_leaky**, **model_two_branch**, and 
**model_multi_res**. Available optimizers are: **adam** and **sgd**

To train the network, use the following command::

	python3 evaluate.py -m <model_name> -o <optimizer_name> -O <1/2/3>

Depending on the operation mode, follow the instructions to select the split.
	
Operation Mode 1
----------------
This operation mode is used to extract confusion matrices. Since confusion matrices are only 
valid for single labeled data, there are two possibilities depending on the used data sets:

- **IRMAS and IRMAS Wind data sets:** since these data sets are multi-labeled on the testing data, a new model is trained by using 50% of the training data set and the remain for confusion matrix calculation.

- **Monotimbral and Jazz data sets:** since these data sets are single-labeled in both training and testing data sets, confusion matrices can be extracted by using the pure test data set.

To plot the confusion matrices::

	cd <MODEL_PATH>/<model_name>
	python3 plot_conf_mat.py

Operation Mode 2
----------------
This operation mode evaluates global and class-wise performance metrics while varying the 
identification threshold from 0 to 1. Following the authors, the development test data set
was used to calculate the performance metrics.

To be able to extract the final performance metrics, it is necessary to plot their behaviour
with respect to the identification threshold::

	cd <MODEL_PATH>/<model_name>
	python3 plot_perf_metrics.py

**Do not skip this step, before extracting final performance metrics.**
	
Operation Mode 3
----------------
Finally, the final performance metrics are extracted by using the optima identification thresholds
(for both global and class-wise cases) on the pure test data set.

Documentation
-------------

.. toctree::
   :maxdepth: 2

.. automodule:: evaluate
   :members: