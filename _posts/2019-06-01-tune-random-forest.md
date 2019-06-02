---
layout: post
cover: 'assets/images/cover6.jpg'
navigation: True
title: How to tune Random Forest model
date: 2019-06-01 12:00:00
tags: MachineLearning
subclass: 'post tag-content'
logo: 'assets/images/ghost.png'
author: Celia
categories: MachineLearning
mathjax: false
---

<h3>Random Forest</h3>
<p>Random forest is an ensemble tool which takes a subset of observations and a subset of variation to build a decision tree.It builds multiple such decision tree and amalgamate them together to get a more accurate and stable prediction.This is a direct consequence of the fact that by the maximum voting from a panel of independent judges, we get the final decision better than the best judge.</p>
<p><img src="https://user-images.githubusercontent.com/38856953/58762593-e6bf0880-8583-11e9-9d2b-fe397c0337e3.png" alt="Small Test Image" /></p>

<p>We general think of random forest as a black box which takes in input and gives out prediction, without worrying too much what calculations are going on the back end.This black box itself have a few levers we can play with.Each of these levers have some effect on either the performance of the model or the resource - time balance. </p>

<h3>Parameters/levers to tune Random Forest</h3>
<p>Parameters in random forest are either to increase the predictive power of the model or make it easier to train the model.</p>
<ol><b><li>Feature which make predictions of the model better</li></b>
<p><img src="https://user-images.githubusercontent.com/38856953/58762652-8bd9e100-8584-11e9-9fbb-55546e7cc349.png"/></p>
<p>These are primarily 3 features which can be tuned to improve the predictive model:</p>
<p><b>a.max_features :</b></p>
<p>These are the maximum number of features Random Forest is allowed to try in individual tree.There are multiple options available in Python to assign maximum features.Here are a few of them:</p>
<ol><li>Auto/None: This will simply take all features which make sense in every tree.Here we simply do not put any restrictions on the individual tree.</li>
<li>sqrt: This option will take square root of the total number of features in individual run.For instance, if the total number variables are 100, we can take 10 of them in individual tree."log2" is another similar type of option for max features.</li>
</ol>
<br>
<p><b>How does "max_features" impact performance and speed?</b></p>
<p>Increasing max_features generally improves the performance of the model as at each node now we have a higher number of options to be considered. However, this is not necessarily true as this decreases the diversity of individual tree. But, for sure, you decrease the speed of the algorithm by increasing the max_features. Hence, you need to strike the right balance and choose the optimal max_features.</p>

<p><b>b.n_estimators :</b></p>
<p>This is the number of trees you want to build before taking the maximum voting or average of predictions. Higher number of trees give you better performance but make you code slower. You should choose as high value as your processor can handle because this make your predictions stronger and more stable. </p>
<p><b>c.min_sample_leaf :</b></p>
<p>If you have built a decision tree before, you can appreciate the importance of the minimum sample leaf size. Leaf is the end node of a decision tree. A smaller leaf makes the model more prone to catching noise in train data.  Generally, I would prefer a minimum leaf size of more than 50. However, you should try multiple leaf size to find the most optimum for your user case.</p>
<b><li>Features which will make the model trailing easier</li></b>
<p>There are a few attributes which have a direct impact on model training speed.Following are the key parameters which help you tune for model speed:</p>

<p><b>a.n_jobs :</b></p>
<p>This parameters tell the engine how many processor.A value of "-1" means there is no restrictions whereas a value of "1" means it can only use one processor.Here is a simple experiment you can do with Python to check this metric:</p>
<pre><code>%timeit</code></pre>
<pre><code>model = RandomForestRegressor(n_estimator = 100, oob_score = TRUE,n_jobs = 1,random_state =1)</code></pre>
<pre><code>model.fit(X,y)</code></pre>
<p>Output ---1 loop best of 3 : 1.7 sec per loop</p>
<pre><code>%timeit</code></pre>
<pre><code>model = RandomForestRegressor(n_estimator = 100, oob_score = TRUE,n_jobs = -1,random_state =1)</code></pre>
<pre><code>model.fit(X,y)</code></pre>
<p>Output ---1 loop best of 3 : 1.1 sec per loop</p>
<p>"%timeit" is an awsum function which runs a function multiple times and gives the fastest loop run time.This comes out very handy while scaling up a particular function from prototype to final dataset. </p>
<p><b>b.random_state :</b></p>
<p>This parameter makes a solution easy to replicate. A definite value of random_state will always produce same results if given with same parameter and training data.</p>
<p><b>c.oob_score :</b></p>
<p>This is a random forest cross validation method.It is very similar to leave out validation technique, however, this is so much faster. This method simply tags every observation used in different trees. And then it finds out a maximum vote score for every observation based on only tree which did not use this particular observation to train itself. </p>

<p>Here is a single example of using these parameters in one single function :</p>
<pre><code>model = RandomForestRegressor(n_estimator = 100, oob_score = TRUE, n_jobs = -1,random_state =50,max_features = "auto", min_samples_leaf = 50)
</code></pre>
<pre><code>model.fit(X,y)</code></pre>
</ol>
