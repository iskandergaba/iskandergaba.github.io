---
layout: post
title: machine bias analysis on COMPAS
description: Analysis on COMPAS algorithm recidivism scores for machine bias.
date: 2020-05-03 23:57:00
img: /img/portfolio/compas/banner.jpg
---

COMPAS (which stands for Correctional Offender Management Profiling for Alternative Sanctions) is a case management and decision support software solution developed by Equivant (formerly Northpointe) for many of U.S. courts to assess the likelihood of a defendant to become a recidivist.

ProPublica conducted an analysis on the COMPAS recidivism scores of more than 10.000 defendants from Broward County, Florida and publised their findings in an [article](https://www.propublica.org/article/how-we-analyzed-the-compas-recidivism-algorithm). They claim to have found that black defendants were far more likely than white defendants to be falsely assigned a high risk of recidivism. By the end of 2018, Equivant made a public [response](https://www.equivant.com/response-to-propublica-demonstrating-accuracy-equity-and-predictive-parity) to ProPublica's analysis refuting all of those claims stating that, among other criticism, "ProPublica on classification statistics that did not take into account the different base rates of recidivism for blacks and whites".


<h3 class="thick">our work</h3>
As part of our work on the project of the data analytics course of the first year of my master's degree, my coleague Guillaume Kessebi and I played around with the COMPAS dataset. We:

- Tried to uncover potential sex and race unbiases in the scores.
- Investigated different fairness criteria like independence, separation, and sufficiency.
- Trained a logistic regression classifier that gives similar accuracy to what is given in the literature.
- Investigated the impact of removing sensitive attributes (i.e. sex and race) to show that such practice is not enough to achieve fairness in machine learning. Often, indicators of sensitive attributes are deeply ingrained within other features used for training.
- Used some the techniques in the literature to tackle different fairness criteria in our classifier and correct/repair our scores.
  - [Technique](https://arxiv.org/abs/1412.3756) for independence criterion.
  - [Technique](https://arxiv.org/abs/1610.02413) for separation criterion.
- Used some of the algorithms in [AI Fairness 360 (AIF360)](https://aif360.mybluemix.net) package originally developed by IBM to train fair classifiers.

<h3 class="thick">go take a look!</h3>
We made our work available in a Notebook on GitHub. So why don't you go take a look?
<br/>
<span class="contacticon center">
	<a href="https://github.com/iskandergaba/mosig1-intro-data-analytics-project/blob/master/Final%20Report.ipynb" target="_blank"><i class="fab fa-github"></i></a>
</span>
