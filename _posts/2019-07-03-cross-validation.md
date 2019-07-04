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
{% gist  %}
<p>[0.96078431 0.92156863 0.95833333]</p>
<h3>Stratified K-Fold cross-validation</h3>
<p>Splitting the dataset into k-folds by starting with the first 1/k-th part of the data as described above might not always be a good idea.</p>
<pre><code>iris.target</code></pre>
array([0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
       0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0,
       0, 0, 0, 0, 0, 0, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,
       1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1,
       1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2,
       2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2,
       2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2])


{% highlight python %}
iris.target
{% endhighlight %}
<p> </p>