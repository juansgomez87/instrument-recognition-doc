Train the Neural Network
========================

Usage
-----
After creating the tensors that will be used to train and test the neural network, it is
possible to start training the neural network. Different models and optimizers can be selected
by command-line argument parsing. Additionally, the *class_weight* implementation from *Keras*
can be activated. This was implemented to take into account the uneven distribution of samples
across instrument labels. Given that this did not result in improvements with the IRMAS data
set, the use of this feature is optional in argument parsing. *Since the size of the neural
network and the amount of data, it is strongly recommended to use a GPU to reduce training time.*

Available model names are:

- **model_baseline** - Baseline model by Han et al. using ReLU activation functions (refer to **section 4.1**).
- **model_leaky** - Baseline model by Han et al. using Leaky ReLU activation functions (refer to **section 4.1**).
- **model_two_branch** - Model that allows for two simultaneous inputs and late fusion (refer to **section 5.6.2**).

- **model_multi_res** - Model that allows for three dimensional input (refer to **section 5.6.3**).

Available optimizer names are:

- **adam** - Adam optimizer with parameters beta_1=0.9, beta_2=0.999, epsilon=1e-08.

- **sgd** - Stochastic Gradient Descent optimizer with parameters momentum=0.9, decay=learning_rate/nb_epochs, Nesterov=True.

To train the network, use the following command::

	python3 train.py -m <model_name> -o <optimizer_name> -c <y/n>
	
Finally, the resulting files are stored in the MODEL_PATH defined in *settings.py*:

- **<model_name>.<optimizer_name><iteration>.history.npy** - Training history to evaluate training and validation loss and accuracy.
- **<model_name>.<optimizer_name><iteration>.best.hdf5** - Stored weights by using ModelCheckpoint saving the model with best validation accuracy.

- **<model_name>.<optimizer_name><iteration>.json** - Structure of the neural network.

Documentation
-------------

.. toctree::
   :maxdepth: 2

.. automodule:: train
   :members:
