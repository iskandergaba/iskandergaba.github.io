---
layout: post
title: kernel methods for DNA sequences
description: predicting whether a DNA sequence region is a binding site to a specific transcription factor
date: 2021-02-17 23:57:00
img: /img/portfolio/kernel-methods/dna.jpg
---

This was a cool project from the Kernel Methods class of my master's degree where my coleague Hadi Dayekh and I worked on predicting whether a DNA sequence region is a binding site to a specific transcription factor.

The project was organized as a [Kaggle](https://www.kaggle.com/c/advanced-learning-models-2020) competition where teams of two students would submit their predictions in a specific format and compete. To keep things fair, the submissions are evaluated on a 50% subset of ground truth (public leaderboard) whereas the final evaluation (i.e. private leaderboard) includes the other half. The submissions quota was also limited to one two submissions per group per day.

And to spice things up, we were not allowed to use any of the popular libraries (e.g. `scikit-learn`). **We had to code everything ourselves, from scratch!**

Our method of choice in this porject was kernel reidge regression. We started first with basic polynomial and Guassian kernels that only yielded a maximum of accuracy of approximately **63%**. We then worked our way into more adequate string kernels like k-Spectrum and Mismatch kernels as well as weighted linear combinations of the two. it is unfortunate that we did not have time to investigate other more computationally expensive string kernels.

At the end, the best performance found out that Mismatch and linear combinations of k-Spectrum kernels produce the best performance as detailed in our [report](https://raw.githubusercontent.com/iskandergaba/mosig2-kernel-methods-project/master/report.pdf). We ranked **13th out of 32** on the public leaderboard with an accuracy of **69.266%**, and **8th out of 32** on the private leaderboard with an accuracy of **70.133%**. The performance gap with the top performers was about **2%** only, proving a comparable performance for kernel ridge regression and that our classification is consistent and well generalizable.

<h3 class="thick">try the code and check our ranking on Kaggle!</h3>
<br/>
<span class="contacticon center">
	<a href="https://github.com/iskandergaba/mosig2-kernel-methods-project" target="_blank"><i class="fab fa-github"></i></a>
	<a href="https://www.kaggle.com/c/advanced-learning-models-2020" target="_blank"><i class="fab fa-kaggle"></i></a>
	<a href="https://www.kaggle.com/c/advanced-learning-models-2020" target="_blank"><i class="fas fa-dna"></i></a>
</span>
