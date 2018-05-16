Comparing Results
=================

Usage
-----
The final results obtained by the evaluation script can now be compared among all
trained models. To do this interactively, use the following commands::

	cd models
	ipython3 compare_models.py
	
Review Results
--------------
The results of performance metrics are stored to Pandas data frames. Results are stored
in the following *Pandas* dataframes:

- **global_res:** Global performance metrics.
- **class_res:** Class-wise performance metrics.

- **global_class_res:** Global performance metrics by using optima class-wise thresholds.

By accessing it interactively, it is possible to find the global performance 
metrics with respect to the data set, model, aggregation strategy and averaging 
method used.

For example::

	global_res.loc['irmas_1024'].loc['model_baseline'].loc['s2'].loc['micro']
	class_res.loc['jazz_db_1024'].loc['model_baseline'].loc['s1'].loc['voi']
	global_class_res.loc['youtube_1024'].loc['model_leaky'].loc['s1'].loc['macro']

will print the precision, recall, and f-scores of these cases.

Finally, you can uncomment sections of the script to plot the improvements by comparing
the models in between them.