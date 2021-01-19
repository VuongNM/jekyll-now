---
layout: post
title: Performing Down Sampling using Feature Discretizer
excerpt: ![image](/images/output_10_2.png)
---


Feature binning is the new coolest tool in the box. Imaging you have to train a Gaussian Processes, or any other kernel method based ML models, and having to deal with a massive dataset. The kernel function is computed pairwise for samples, it means that the **time and space cost of the kernel function is O(n^2)**.

It would cause you headache.

This notebook demonstrate the use of Feature Binning as a way to uniformly subsample the dataset, apply to kernel SVM. You can apply this to other kernel based ML models as well, like GP, or even Kmeans if you fancy. 



The general idea is to put samples into buckets (bins), and use the bucket or the bucket average as the representative value for all of the samples in that bucket. Number of point falls in to that bin could be used as sample weights if the ML implementation supports.


Number of samples will be reduce drastically, from O(n^2) to worst case O(b\*k\*t) where b is the number of bins, k is the number of features, and t is the number of classes ( if it's classification problem).



However, the binned samples density will be altered for sure. But if you care more about the decision boundary more than the actual density, then this is surely helpful.
    


Here, I created a synthesis dataset consist of 100000 samples, moderate noise and 2 classes. Standard kernel SVM is fitted on the dataset and also, decision boundary is shown.



![image](/images/output_6_2.png )



**Now here come the fancy thing: FeatureDiscretizer.**

With 100 bins, the sample size reduced from 100k to roughly 5000, using ```KBinsDiscretizer``` from Sklearn. 


There any some way to obtain the bins, here i choose uniform (All buckets are in the same size, you can choose quantile, where all buckets have the same amount of points). Notice how spread out the samples are. 





![image](/images/output_10_2.png )




Checkout the notebook here.[notebook](https://github.com/VuongNM/featurebinning/blob/master/featbin.ipynb)
