---
layout: post
cover: 'assets/images/cover6.jpg'
navigation: True
title: Time Series Analysis
date: 2019-05-23 12:00:00
tags: Finance
subclass: 'post tag-content'
logo: 'assets/images/ghost.png'
author: Celia
categories: Finance
---
<ul>
The analysis of time series data is an integer part of any data scientist's job, more so in the quantitive trading world. Financial data is the most perplexing of time series data and often seems erratic.However, over this article, I will explore some well established theories using for analysing such time series data.
</ul>
<h2>What is Time series ?</h2>
<ul>
<p>Examples of time series data include:</p>
<ul>
<li>Daily IBM stock prices</li>
<li>Monthly rainfall</li>
<li>Quarterly sales results for Amazon </li>
<li>Annul Google profits</li>
</ul>
<p> Anything that is observed sequentially over time is a <strong>time series</strong>.
A time series may contain information about general tendency in data, seasonal effects, occasional events, and so on. </p>
<p>Time series decomposition: </p>
<ul>
<li><b>Trend</b> - The general (long-term, non-periodic)tendency of time series.These trends will either be <cite>deterministic</cite> or <cite>stochastic</cite>.
<p><img src="https://user-images.githubusercontent.com/38856953/58217778-df536000-7d36-11e9-84ae-d69753520587.png" /></p>
<li><b>Seasonal</b> - A seasonal pattern occurs when a time series is affected by seasonal factors such as the time of the year or the day of the week. This is particularly happening in series representing business sales or climate levels.</li>
<p><img src="https://user-images.githubusercontent.com/38856953/58217816-132e8580-7d37-11e9-9409-a8cc78a9548b.png" /></p>
<li><b>Cyclic</b> - A cycle occurs when the data exhibit rises and falls that are not of a fixed frequency. These fluctuations are usually due to economic conditions, and are often related to the “business cycle”.</li>
</ul>
<p>Many people confuse about cyclic behaviour and seasonal behaviour, but they are quite different. If the fluctuations are not of a fixed frequency then they are cyclic; if the frequency is unchanging and associated with some aspect of calendar, then the pattern is seasonal.
</ul>
<h2>ARIMA Model</h2>
<ul>
The first model we are going to discuss is the ARIMA model. It stands for Auto Regressive Integrated Moving Average model. Yes it's a lot to take in. However, it essentially combines two models, the Auto Regressive model and the Moving Average model, both of which we will elaborate on below. Before that, we need to establish the concept of stationarity, as it is crucial to being able to model and forecast time series correctly.
</ul>
<h2>Stationarity</h2>
<ul>
<p>The concept of stationarity comes from stochastic processes, and sometimes the result of these stochastic process is white noise.The following is a broad definition of stationarity:</p>

<blockquote>
  <p>A stationary time series is a time series whose statistical properties such as mean and standard deviation does not depend on time.</p>
</blockquote>
<p>For those with experience with statistics and stochastic, the following will be more formal definition.</p>

<p>Let {Xt} be a stochastic process and </p>
$$
F_{X}\left(x_{t_{1}+\tau}, x_{t_{2}+\tau}, \ldots, x_{t_{k}+\tau}\right)
$$
<p>is the is the cumulative distribution function of the unconditional joint distribution of {Xt}. Then, {Xt} is strictly stationary, if and only if, </p>
$$F_{X}\left(x_{t_{1}+\tau}, x_{t_{2}+\tau}, \ldots, x_{t_{k}+\tau}\right)=F_{X}\left(x_{t_{1}}, x_{t_{2}}, \ldots, x_{t_{k}}\right)$$
<p>However, in most applications, we don't manually check for stationarity using stochastic.We use tests for such as Dicky-Fuller and Augmented Dicky-Fuller test. </p>
<p>There is also a weaker notion of stationarity</p>


</ul>
