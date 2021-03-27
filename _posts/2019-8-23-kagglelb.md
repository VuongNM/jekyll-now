---
layout: post
title: On Kaggle Public - Private Leaderboard
---

One of the goals of building machine learning model is to accurately predict the future. 

Since the future is unknown, we machine learning practitioner try to simulate task in an environment, collecting data that is as informative as possible, building the model that we think is best.



**The purpose of train and test set**

The trainset should represent everything that the model and the practitioner should know about the data, the features types, its observable distribution. Depend on the task and how much of the generalization property, the size and wholeness of the data distribution should be considered. 


The testset, as in the name, is a test of the models abilities. 

Do we need to test the ability to extrapolate from the partial distributed trainset into the unknown ? In Kaggle context, most probably yes. 


Do we need to test the performance of the model, how fast it should run, how easy to deploy ? For Kaggle, usually no. In real world, yes.


Since the testset represent the unknown, evaluating the model multiple time against it reduce its usefulness as a test set.


The construction of the model validation set should be considered thoroughly. Pursposefully make the validation set look like testset undermine the testset itself, and undermine the task of building the model (How do you make thing looks like something you dont know? In this case, you suppose to not know the test set)



**Kaggle Public leaderboard is not that useful**


In the general sense, trainset and testset is randomly split, or is sampled based on some index (time, or space or whatever).


If the public testset is akin to trainset,then it's redundant. And if the public testset reveals something about the private one, then it's leakage, in the sense that it undermines the true purpose of the (unseen data) testset. 

It's up to the organizer to decided that the leakage is desirable or not. 

Also that when the public leaderboard testset does not look like train or test set, then the discrepancy creates shakeups and huge disappointment at the end of the day.

This free-to-probe leaderboard data also encourage trial-and-error kind of approach. I agree that it works. But it also discourages the development of rigorous and well thought out approaches. 



**Solutions**

Get rid of the public leaderboard altogether. All you got there folks is the trainset. That place a big responsibility on the organizer shoulder to construct a train and test set that makes sense. 

Also, doing so reduce the thrill, the feel of competing and self gratification you reward yourself on beating other teams. 

A suggestion would be doing round-based evaluation, says, each week of the competition. That would reduce the probing effect, force the competitor to be more scientifically constructive in their solution. When evaluation is expensive, the competitor will spend them more wisely.

