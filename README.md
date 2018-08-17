# hypermax-results
This is a public repository of containing a dataset of hyperparameter optimization searches.

The searches within this dataset are done with almost entirely with random search, and not with an optimization algorithm.
This makes them an unbiased dataset from which we can simulate hyper-parameter searches done with an optimization
algorithm.

We welcome submissions to this dataset. To crack hyperparameter optimization, we really need as much data as possible.
To contribute, simply perform a large, largely random hyperparameter search on some sort of machine learning or other type
of algorithm. The search must be random and thorough - 10x more thorough and extensive then you would normally do
in a hyperparameter search. This is because the data will be used to simulate that exact same hyperparameter search.

Ideally, we want hyperparameter search results that were constructed in the following fashion:

  - Start by searching over your full hyper-parameter search space for 1,000 to 5,000 trials.
  - Next, contrain your search space to the ranges for each hyperparameters representing the best 10% of results. This
    focuses your search in on the best part of the hyperparameter space, but in a way that is as unbiased as possible.
    Run this stage for another 1,000 to 5,000 trials, giving a lot more definition to the best performing area of the
    hyperparameter space.
  - Again, constrain hyperparameter space once again to the best 10% of results from the second stage. Run another 1,000
    to 5,000 trials.
  - Lastly, to ensure that you include the global minima of the hyper-parameter space in your dataset, do a final stage
    of hyper-parameter searching, but this time with an optimizer like TPE or Hypermax's ATPE. With all of the data 
    accumulated, it will quickly home in on high-performing areas of your search space. So just include another 100
    to 200 runs with your optimizer to put the "cherry" on your dataset.
    
You should result in a dataset that contains between 3,000 and 15,000 results for your hyperparameter search space.
Naturally, if your hyperparameter search space is very small (only 2 or 3 parameters), we might need significantly
less data-points to accurately recreate the results. Apply judgement. Its expensive to do such thorough searches,
and it seems like a wasted effort to explore some much of the crappy area of the hyperparameter space by not using an
optimizer. But having thorough data on what real hyperparameter searches look like is critical if we are to make 
progress on this highly difficult problem.

If you have done an excessively thorough hyperparameter search, but using a tool other then Hypermax, we will accept
those to! Results preferably in CSV format.

Make a pull request on Github or reach out at brad@electricbrain.io if you want to contribute.
