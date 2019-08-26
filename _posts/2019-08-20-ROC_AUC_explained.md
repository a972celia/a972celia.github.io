---
layout: post
cover: 'assets/images/cover3.jpg'
navigation: True
title: ROC AUC explained
date: 2019-08-20 12:00:00
tags: MachineLearning
subclass: 'post tag-content'
logo: 'assets/images/ghost.png'
author: Celia
categories: MachineLearning
---
<br>
<h3>Evaluating classification models</h3>
<p>It is common in predictive modeling to try out a number of different models, apply each to a holdout sample (also called a test or validation sample), and assess their performance.Fundamentally, this amounts to seeing which produces the most accurate predictions. </p>
<h3>Important concept for evaluating classification models </h3>
<li><b> Accuracy :</b> The percent (or proportion) of cases classified correctly.</li>
<li><b>Confusion matrix :</b> A tabular display (2*2 in the binary case) of the record counts by their predict and actual classification status. </li>
<li><b>Sensitivity (Recall) :</b> The percent (or proportion) of 1s correctly</li>
<li><b>Specificity :</b> The percent (or proportion) of 0s correctly</li>
<li><b>Precision :</b> The percent (or proportion) of predicted 1s that are actually 1s. </li>
<li><b>ROC curve :</b> A plot of sensitivity versus specificity.</li>
<br>
<h3>What is Confusion Matrix and Why you need it ?</h3>
<p>A simple way to measure classification performance is to count the proportion of predictions that are correct. At the heart of classification metrics is <i>confusion matrix</i>. It is a performance measurement for machine learning classification problem where output can be two or more classes. It is a table with 4 different combinations of predicted and actual values.</p>
<p><img src="https://user-images.githubusercontent.com/38856953/63646997-d5823400-c74d-11e9-94cf-956a96a6aa4e.png"  width="700" height="500" /></p>
<p>It is extremely useful for measuring Recall, Precision, Specificity, Accuracy, and most importantly AUC-ROC curve. </p>
<p>Let’s understand TP, FP, FN, TN:</p>

<p><b>True Positive:</b> </p>
<p>You predicted positive and it’s true.</p>
<p><b>True Negative:</b> </p>
<p>You predicted negative and it’s true.</p>
<p><b>False Positive (Type 1 Error): </b> </p>
<p> You predicted positive and it’s false.</p>
<p><b>False Negative (Type 2 Error): </b> </p>
<p> You predicted negative and it’s false.</p>
<br>
<h3>What is AUC - ROC Curve?</h3>
<p>In the MachineLearning, performance measurement is an essential task.So when it comes to a classification problem, we can count on AUC-ROC curve.</p>
<p>The receiver operating characteristic curve, or ROC curve for short, is used to analyze the behaviour of classifiers at different threshold. Similar to the precision-recall curve, the ROC curve considers all possible thresholds for a given classifier, but instead of reporting precision and recall, it shows the <i>false positive rate</i> (FPR) against the <i> true positive rate</i> (TPR). Recall that true positive rate is simply another name for recall, while the false positive rate is the fraction of false positive out of all negative samples.<br>
To put it briefly, ROC is a probability curve and AUC represents the degree or measure of separability. It tells how much model is capable of distinguishing between classes. Higher the AUC, better the model is at predicting 0s as 0s and 1s as 1s.</p>
<p>The ROC curve is plotted with TPR against the FPR where  TPR is on y-axis and FPR is on the x-axis.</p>
<p><img src="https://user-images.githubusercontent.com/38856953/63646933-e2525800-c74c-11e9-9616-57295ad9ffbe.png"/></p>
<h3>How to speculate the performance of the model?</h3>
<p>A good model had AUC near to 1 which means it has good measure of separability. A poor model has AUC near to the 0 which means it has worst measure of separability.In fact in means it reciprocating the result. It is predicting 0s as 1s and 1s as 0s. And when AUC is 0.5, it means model has no class separation capacity whatsoever.</p>
<p>Note: Red distribution curve is of the positive class (patients with disease) and green distribution curve is of negative class(patients with no disease).
</p>
<p><img src="https://user-images.githubusercontent.com/38856953/63650951-e5683b00-c782-11e9-802b-051b3dd29ada.png"  width="700" /></p>
<p>This is an ideal situation. When two curves don't overlap at all means model has an ideal measure of separation.</p>
<p><img src="https://user-images.githubusercontent.com/38856953/63651113-2ca2fb80-c784-11e9-8fc8-0c3d3dfd5281.png"  width="700" /></p>
<p>When two distribution overlap, we introduce type 1 and type 2 error. Depending upon the threshold, we can minimize or maximize then. When AUC is 0.7, it means there is 70 % chance that model will be able to distinguish between positive class and negative class.</p>
<p><img src="https://user-images.githubusercontent.com/38856953/63651190-d97d7880-c784-11e9-84be-514e62ef8ea2.png"  width="700" /></p>
<p>This is the worst case. When AUC is approaching 0.5, model has no discrimination capacity to distinguish between positive class and negative class.</p>
<p><img src="https://user-images.githubusercontent.com/38856953/63651247-57da1a80-c785-11e9-94c0-52076790da7e.png"  width="700" /></p>
<p>When AUC is approximately 0, model is actually reciprocating the class. It means model is predicting negative class as positive class and vice versa. </p>
