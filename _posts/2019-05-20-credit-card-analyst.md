---
layout: post
cover: 'assets/images/cover6.jpg'
navigation: True
title: Credit Card Fraud and Detection technique
date: 2019-05-20 12:00:00
tags: Finance
subclass: 'post tag-content'
logo: 'assets/images/ghost.png'
author: Celia
categories: Finance
---
<h2>Overview</h2>

<ul>
<p>Fraud is one of the major ethical issues in the credit card industry. For years, fraudsters would simply takes numbers from <strong>credit</strong> or <strong>debit cards</strong> and print them onto blank plastic cards and use at brick-and-mortar stores.
Nevertheless, <span style="text-decoration:underline;">[expert predict online credit card soar to](https://nilsonreport.com/upload/content_promo/The_Nilson_Report_10-17-2016.pdf)</span> whopping <strong>$32 billion</strong> in 2025.</p>
<p>As a result, companies have been investing massive amounts in other technologies for detecting fraudulent transaction.</p>
<p>Below will present some detection technique.</p>

</ul>

<h3>Classification Problems </h3>
<ul>
![Classification](https://user-images.githubusercontent.com/38856953/58000828-87d1ac00-7b0c-11e9-9900-be74ecf301bc.png)

<p>In <strong>Machine Learning</strong>, problems like fraud detection are usually framed as <strong>classification problems</strong> -- predicting a discrete class label output given a data observation. Example of classification problems that can be thought of are <strong>Spam Detectors</strong>,<strong>Recommender Systems</strong> and <strong>Loan Default Prediction</strong>.
</p>
<p>
Taking about the credit card payment fraud detection, the classification problems involves creating models that have enough intelligent in order to properly classify transaction as either <strong>legit</strong> or <strong>fraudulent</strong>,based on transaction details such as amount, merchant, location, time.</p>
<p>
Financial fraud still amounts for considerable amounts of money.Hackers and crooks around the world are always looking for the new ways of committing fraud.Relying exclusively on rule-based, conventionally programmed systems would not provide the appropriate time-to-market.This is where <strong>Machine Learning</strong> shines as a unique solution for this type of problem.
</p>
<p>The main challenge when it comes to dealing fraud detection come from the fact that in the real world data, the majority of the transaction is not fraudulent.And this brings us a problem:<strong> imbalanced data </strong>.
</p>
</ul>
<h3>Imbalanced Data</h3>
<ul>
<p>Data imbalance usually reflects an unequal distribution of classes within a dataset.For example, in a credit card detection dataset, most of the transaction are not fraud and very few classes are fraud transactions.This leaves us with something like 50:1 ration between the fraud and non-fraud classes.</p>
<p>When you are supposed to predict the fraudulent rate based on data from previous years, what would you do?</p>
<p>The most straightforward way to proceed in this case would be predicting that <strong> 100% of transactions is non-fraud</strong>.<strong>Accuracy</strong> in this case would be 98% when simulating past years. Sounds great, right?</p>

<p>Would this model be correct? </p>
<p>Certainly not! We'll take a look at a practical case study and learn how to overcome the issue of imbalanced data.</p>

</ul>

<h3>Case Study</h3>

<ul>
<p>The case study is aimed to demonstrate how I dealt with an imbalanced data for credit card fraudulent dataset and obtained a forecast with 94% accuracy rate using python.</p>

<p>And the code can be found [here](https://github.com/a972celia/Data-Analysis-project/blob/master/Credit_card_fraud_detection/Credit%20card%20fraud%20detection.ipynb).</p>

</ul>
