---
layout: post
cover: 'assets/images/cover4.jpg'
navigation: True
title: Principal Component Analysis (PCA)
date: 2019-07-19 12:00:00
tags: MachineLearning
subclass: 'post tag-content'
logo: 'assets/images/ghost.png'
author: Celia
categories: MachineLearning

---
<br>
<h2>What is Principal Component Analysis?</h2>
<p>Principal component analysis, or PCA, is a method that rotates the dataset in a way such that the rotated features are statistically uncorrelated.This rotation is often followed by a subset of the new features, according to how important they are for explaining the data. In other word, PCA is a dimensionality-reduction method that is often used to reduce the dimensionality of large data sets, by transforming a large set of variables into a smaller one that still contains most of the information in the large set. </p>
<p>This is easiest to explain by way of example.Here are some triangles in the shape of an oval:</p>
<p><img src="https://user-images.githubusercontent.com/38856953/61458190-7c7bef00-a99c-11e9-8565-daf961181c91.png" alt="Small Test Image" /></p>
<p>Image that triangles are points of data.To find the direction where there is most variance, find the straight light where the data is most spread out when projected onto it. A vertical straight line with the points projected onto it will look like this:</p>
<p><img src="https://user-images.githubusercontent.com/38856953/61458577-70446180-a99d-11e9-871e-cb46534934b3.png" alt="Small Test Image" /></p>
<p>The data is not very spread out here, therefore it doesn't have a large variance. It is probably not the principle component.</p>
<p>A horizontal line are with points projected on will look like this:</p>
<p><img src="https://user-images.githubusercontent.com/38856953/61458848-0b3d3b80-a99e-11e9-8ee6-94c4dd14698c.png" alt="Small Test Image" /></p>
<p>On this line the data is way more spread out, it has a large variance. In fact, there is not a straight line you can draw that has a large variance than a horizontal one. A horizontal line is therefore the principle component here.</p>
<p>Luckily, we can use math to find principle component rather than drawing lines and unevenly shaped triangles.This is where eigenvectors and eigenvalues come in.</p>

<h2>Eigenvectors and Eigenvalues</h2>
<p>Eigenvectors and values exist in pairs : every eigenvector has corresponding eigenvalue. An eigenvector is a direction, in the example above the eigenvector was the direction of the line (vertical, horizontal, 45 degrees etc.) .An eigenvalue is a number, telling you how much variance there is in the data in that direction, in the example above the eigenvalue is a number telling us how spread out the data is on the line. The eigenvector with the highest eigenvalue is therefore the principle component.</p>
<p>The amount of eigenvectors/values that exist equals the number of dimensions the data set has. The reason for this is that eigenvectors put the data into a new set of dimensions, and these new dimensions have to be equal to the original amount of dimensions. This sounds complicated, but again an example should make it clear.</p>
<p>Here is the graph of the oval:</p>
<p><img src="https://user-images.githubusercontent.com/38856953/61493352-f4223c00-a9e5-11e9-8647-146d4d7bbba1.png" /></p>
<p>At the moment the oval is on x-y axis. x could be age and y hours on the internet. These are two dimensions that my data set is currently being measured in. Now remember that the principle component of the oval was a line splitting it longways.  </p>
<p><img src="https://user-images.githubusercontent.com/38856953/61494208-246ada00-a9e8-11e9-97d1-52435261d4cc.png" ></p>
<p>It turns out the other eigenvector (there are only two of them as it is a 2-D problem) is perpendicular to the principle component. As we said, the eigenvectors have to be able to span the whole x-y area, in order to do this most effectively, the two directions need to be orthogonal to one another. This is why x and y axis are orthogonal to each other in the first place.  </p>
<p><img src="https://user-images.githubusercontent.com/38856953/61494700-72341200-a9e9-11e9-909b-3917e426567b.png" ></p>
<p>The eigenvectors have given us more a much more useful axis to frame the data in. We can now frame the data in this new dimensions. It would look like this:</p>
<p><img src="https://user-images.githubusercontent.com/38856953/61506134-bcca8400-aa13-11e9-95b7-5600e4c21ca1.png" ></p>
<p>Note that nothing has been done to the data itself. We’re just looking at it from a different angle.So getting the eigenvectors gets you from one set of axes to another. These axes are much more intuitive to the shape of the data now. These directions are where there is most variation, and that is where there is more information. </p>
<p>In short ..</p>
<blockquote>
  <p>Total Sample <b>Variance</b> = Sum of <b>Eigenvalues</b><br>
<b>Eigenvector</b> with highest eigenvalue = <b>Principal Component</b></p>
</blockquote>
<br>
<h2>Important concept </h2>
<li><b>Variance :</b> measures how far the values of variables are spread out from its mean</li>
<li><b>Covariance :</b> measures how much two variables change together</li>
<li><b>Covariance Matrix :</b> a matrix that measures the relationship between multiple variables</li>
<li><b>Vectors & Matrices :</b> vector is a 1 x n array, while a matrix can be m x n array.</li>
<li><b>Matrix decomposition :</b> is a factorization of a matrix into product of matrices.</li>
<li><b>Eigen decomposition :</b> is the factorization of a matrix into standard form, where its representation is in terms of its <b>eigenvalues</b> and <b>eigenvectors</b>. </li>
<br>
<h2>Matrix Decomposition</h2>
<p>There are two ways to perform PCA :</p>

<li>Eigen Value Decomposition | Covariance matrix<br>
<br>
<p><img src="https://user-images.githubusercontent.com/38856953/61509832-07073180-aa23-11e9-942a-947e73d872c8.png" alt="Small Test Image" /></p>
<p>the steps of the eigen value decomposition are as followed :
<ol>
<li>Center the original data X </li>
<li>Calculate the covariance matrix C</li>
<li>Calculate the <b>eigenvalues</b> and <b> eigenvectors</b> of C</li>
<li>Find the transformation matrix V by selecting
<b>eigenvectors</b> with highest <b> eigenvalues </b>(variance)</li>
<li>Derive the new data set by taking Y =XV</li>
</ol>
</p>
<br>
<li>Singular Value Decomposition</li><br>
<p><img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c8/Singular_value_decomposition_visualisation.svg/2000px-Singular_value_decomposition_visualisation.svg.png"/></p>


<h2>Application in python</h2>
<p>You can find an application of PCA built in python in <a href="https://github.com/a972celia/Data-Analysis-project/blob/master/Machine%20Learning/Principle%20component%20analysis%20build%20from%20scratch.ipynb">here</a>.</p>
