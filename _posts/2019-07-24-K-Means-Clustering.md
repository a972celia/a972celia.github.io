---
layout: post
cover: 'assets/images/cover2.jpg'
navigation: True
title: K-Means Clustering explained
date: 2019-07-24 12:00:00
tags: MachineLearning
subclass: 'post tag-content'
logo: 'assets/images/ghost.png'
author: Celia
categories: MachineLearning

---
<br>
<h3>Clustering </h3>

<p>Clustering is an unsupervised learning technique used for data classification. </p>
<p>Unsupervised learning means there is no output variables to guide the learning process(no this or that, no right or wrong) and data is explored by algorithms to find patterns.We only observe the features but have no established measurements of the outcomes since we want to find them out. </p>
<p>As opposed to the supervised learning where your existing data is already labelled and you know which behaviour you want to determine in the new data you obtain, unsupervised learning techniques don't use labelled data and algorithms are left to themselves to discover structures in the data.</p>
<h3>K-Means clustering</h3>
<p>Within the universe of clustering techniques, K-means is probably one of the most known and frequently used. K-means uses an iterative refinement method to produce its final clustering based on the number of clusters (represented by the variables K) defined by its users and its dataset. For example, if we set K equal to 3 then our dataset will be grouped into 3 clusters.</p>
<p>K-means start off with arbitrarily chosen data points as proposed means of the data groups, and iteratively recalculates new means in order to converge to final clustering of the data points. </p>
<p>But how does the algorithms decide how to group the data if you are just providing a value (K)? When you define the value of K you are actually telling the algorithms how many means or centroids you want. A centroid is a data point that represents the center of the cluster, and it might not necessarily be a member of dataset.</p>
<p>This is how the algorithm works:</p>
<ol>
<li> K centroids are created randomly (based on the predefined value of K)  </li>
<li>K-means allocates every data point in the dataset to the nearest centroid(minimizing <b>Euclidean distances</b> between them), meaning that a data point is considered to be in a particular cluster if it is closer to that cluster's centroid than any other centroid. </li>

<li> Then K-means recalculates the centroids by taking the means of all data points assigned to that centroid's cluster, hence reducing the total intra-cluster variance in relation to the previous step. The "means" in the K-means refers to averaging the data and  finding the new centroid </li>

<li>The algorithm reiterate step 2 and 3 until some criteria is met(e.g. the sum of distances between the data points and their corresponding centroid is minized, a maximum number of iterations is reached, no changes in centroids value or no data points changes clusters.)</li>



</ol>
<p><img src="https://user-images.githubusercontent.com/38856953/61853613-ea6d6c80-aeee-11e9-9e18-854f63b6c7dc.gif"/></p>

<p><b>Another critical question exists in K-means is that how do we know the correct number of K ?</b></p>
<p>There is no universal answer for this.One commonly used approach is testing different numbers of clusters and measure the resulting sum of squared errors, choosing the K value at which an increase will cause a very small decrease in the error sum , while a decrease will sharply increase the error sum. This point that defines the optimal number of clusters is known as "elbow point", and can be used as a visual measure to find the best pick of K.</p>
<p><img src="https://user-images.githubusercontent.com/38856953/61780108-78385180-ae34-11e9-912a-6ae6400d737f.png"/></p>
<p><b>But everything has a downside</b></p>
<p>One of the drawbacks of the K-means is that it relies on random initialization, which means the outcome of the algorithm depends on random seed, results may not be comparable and lack of consistency. By default, scikit-learn runs the algorithm 10 times with 10 different random initializations, and returns the best result. Further downside of K-means are the relatively restrictive assumptions made on the shape of clusters, and the requirement to specify the number of clusters you are looking for(which may not be known in a real-world application).</p>

<h3>Implementation in python</h3>

{% gist a45832d818925f8aa539e9598715b9cd%}
