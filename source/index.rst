.. instRecCnn documentation master file, created by
   sphinx-quickstart on Thu May  3 11:40:06 2018.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Automatic Instrument Recognition with Deep Convolutional Neural Networks
========================================================================
Juan Sebastián Gómez Cañón (Ilmenau, Germany - 2018)


Introduction
------------
In the context of growing digital media and new classification/indexing demands, the 
task of Automatic Instrument Recognition in the field of Music Information Retrieval
(MIR) has increasing importance. Through the use of deep learning techniques, namely
convolutional neural networks, and different automatic source separation algorithms,
developed at the Fraunhofer Institut für Digitale Medientechnologie (IDMT) [1]_ [2]_, this
Master thesis investigates this recognition task and how different pre-processing stages
can improve its classification performance. Several experiments have been conducted
in order to reproduce and improve upon the results of the reference system reported
by Han et al. [3]_ . Two systems are proposed in this research: an improved system using
harmonic/percussive separation and post-processing using class-wise thresholding,
and a combined system using solo/accompaniment separation and transfer learning
methods for the special use case of jazz solo recognition. To validate the obtained
results, diverse tests have been performed with multiple music data sets, with different
complexities and instrument selections.

Getting started
---------------

.. toctree::
   :maxdepth: 2

   installing
   settings

Data sets and Training
----------------------

.. toctree::
   :maxdepth: 2

   generate_dataset
   train

Evaluation and Results
----------------------

.. toctree::
   :maxdepth: 2

   evaluate
   results
   
References
----------
.. [1] Estefanía Cano, Mark D. Plumbley, and Christian Dittmar, *"Phase-based harmonic/percussive separation,"* in Proceedings of the Annual Conference of the International Speech Communication Association (INTERSPEECH), Singapore, 2014, pp. 1628-1632.

.. [2] Estefanía Cano, Gerald Schuller, and Christian Dittmar, *"Pitch-informed solo and accompaniment separation towards its use in music education applications,"* EURASIP Journal on Advances in Signal Processing, vol. 2014, pp. 23, 2014.

.. [3] Yoonchang Han, Jaehun Kim, and Kyogu Lee, *"Deep convolutional neural networks for predominant instrument recognition in polyphonic music,"* IEEE/ACM Transactions on Audio, Speech, and Language Processing, vol. 25, no. 1, pp. 208-221, Jan 2017.

   
Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

