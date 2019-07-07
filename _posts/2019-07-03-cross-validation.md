---
layout: post
cover: 'assets/images/cover2.jpg'
navigation: True
title: What Is Cross Validation ?
date: 2019-07-03 12:00:00
tags: MachineLearning
subclass: 'post tag-content'
logo: 'assets/images/ghost.png'
author: Celia
categories: MachineLearning

---
<br>
<h3>Cross-validation</h3>
<p>There is always a need to validate the stability of machine learning model, how well our model generalises to new, unseen data. </p>
<p>Cross-validation is statistical method to evaluate the generalisation performance in a more stable and thorough way than spilt into training and test set. It's a model validation technique for assessing how the results of a statistical analysis will generalise to an independent data set. It's mainly used in settings where the goal is prediction, and one wants to estimate how accurately a predictive model perform in real world.</p>
<p>The goal of cross-validation is to define a data set to test the model in the training phase in order to limit the problem like overfitting and underfitting.</p>
<blockquote>
  <p>What is overfitting and underfitting?</p>
</blockquote>

<ul>
<li><b>Underfitting</b> refers to not capture enough patterns in the data. The model performs poorly both in the training and test set.</li>
<li><b>Overfitting</b> refers: a) capturing noise and b) capturing patterns which do not generalise well to unseen data. The model performs extremely well in the training set but poorly on test set.</li>
<br>
<p>The optimal model should perform well both in train and test set.</p>
<p><img src="https://user-images.githubusercontent.com/38856953/60629365-07e77300-9e28-11e9-8b2d-c540de1763c0.png" ></p>
</ul>
<p>In cross-validation, instead of splitting into a training set and a test set, the data is splitting repeatedly and multiple data are trained.</p>
<h3>K-Fold cross-validation</h3>
<p>The most commonly used version of cross-validation is k-fold cross-validation, where k is a user specified number, <b>usually five or ten</b>. When performing five-fold cross-validation, the data is first partitioned into five parts of equal size, called folds. </p>
<p>Next, a sequence of models is trained. The first model is trained using the first fold as the test set, the remaining folds 2-5 as the training set. The model is build using the data in the folds 2-5, and then the accuracy is evaluated on fold 1.</p>
<p>Then, another model is build, this time using fold 2 as the test set, and the data in folds 1,3,4 and 5 as the training set.</p>
<p>This process is repeated using the folds 3, 4, and 5 as test sets.For each of these five spilts of the data into training and test set, we computed the accuracy. In the end, we have calculated five accuracy values.</p>
<p><img src="https://user-images.githubusercontent.com/38856953/60639319-bbfef300-9e54-11e9-94e7-6885f0f475a5.png" ></p>
{% gist ee3375d7ed2186c0831ef2add7afe739%}

<h3>Stratified K-Fold cross-validation</h3>
<p>Splitting the dataset into k-folds by starting with the first 1/k-th part of the data as described above might not always be a good idea.Let’s have a look at the iris dataset for example:</p>
<pre><code>iris.target</code></pre>
<p>array([0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,0, 0, 0, 0, 0, 0, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2,2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2])</p>

<p>As you can see above, the first third of the data is class 0, the second third is the class 1, and the last third is class 2. Image doing three-fold cross-validation on this dataset. The first fold would be only class 0, so in the first split of the data, the test set would be only class zero, and the training set would be only class 1 and 2.</p>
<p>As the classes in the training and test set would be different for all three splits, the three-fold cross-validation accuracy would be zero in this dataset.</p>
<p>For such problems, a slight variation in k-fold cross-validation is made, such that each fold contains approximately the same percentage of samples of each target as the complete set.This method is known as <b>stratified k-fold </b>. </p>
<p><img src="https://user-images.githubusercontent.com/38856953/60647553-8e27a780-9e70-11e9-9f4f-1064ca101aab.png" ></p>
<h3>Leave-One-Out cross-validation</h3>
<p>Another frequently used cross-validation method is leave-one-out. You can think of leave-one-out cross-validation as k-fold cross-validation where each fold is a single sample. For each split, you pick a single data point to be the test set. This can be very time-consuming, in particular for a large datasets, but sometimes provide better estimates on small datasets. </p>
<p><img src="https://user-images.githubusercontent.com/38856953/60649126-ff1c8e80-9e73-11e9-8297-4ccb053b789d.png" ></p>
