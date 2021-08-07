---
layout: post
title: CO<sub>2</sub> emissions information visualization
description: A data information visualization project
date: 2021-02-17 23:57:00
img: /img/portfolio/info-viz/thumbnail.png
---

An information visualization project that seeks to help users visually answer a few questions regarding the data trends in a CO<sub>2</sub> emissions dataset of academic laboratory work travels with all identifying information anonymized using Game of Thrones character and location names.

I worked with Moncif Toubouh on this project, each producing a visualzation using [D3.js](https://d3js.org) giving a separate insight.

<br>
<h3 class="thick">moncif's visualization</h3>
This visualization provides a global insight on how the CO<sub>2</sub> emissions are distributed across continent destinations over the years as well as a comparative one between different continent destinations. This visualization consists of a graph line per continent destination where years are depicted over the x axis, as it is commonly the case, and the CO<sub>2</sub> emissions in tons are depicted on the y axis. Each of the graphs is drawn with a carefully chosen color so that each one can easily stand out to the eye from the others. The user can also show/hide specific graphs for each continent destination. Having all graphs of all continent destinations in one plot depicted in different colors helps understand the general trend of emissions over the years per continent destination in a glimpse. In particular, the ability to individually show/hide specific graphs makes it possible to easily scan trends for select continent destinations of interest to the user and compare trends between them. 

<div class="img_row">
	<img class="col three" src="{{site.baseurl}}/img/portfolio/info-viz/moncif.png" alt="Graph visualization">
</div>
<div class="col three caption">
	Home page of the old website. 
</div>

<br>
<h3 class="thick">my visualization</h3>
<div class="img_row">
	<img class="col one" src="{{site.baseurl}}/img/portfolio/info-viz/iskander1.png" alt="Institution Bar Chart" title="Institution Bar Chart"/>
	<img class="col one" src="{{site.baseurl}}/img/portfolio/info-viz/iskander2.png" alt="Region Bar Chart" title="Region Bar Chart"/>
	<img class="col one" src="{{site.baseurl}}/img/portfolio/info-viz/iskander3.png" alt="House Bar Chart" title="House Bar Chart"/>
</div>
<div class="col three caption">
	From left to right: Bar Chart categorization by institution, by region, and by house.
</div>
This grouped bar chart provides explains how different decompositions of travelling researchers (i.e by region, house, title, rank, and institution) impact CO<sub>2</sub> emissions. Given a decomposition of travelers, the x axis depicts categories in that decomposition. The left and right y axes depict the total and average emissions value in tons and kilograms, respectively, for each category. Each point on the x axis has two bars: one represents the total emissions for the category and the other represents emissions per user for that category. The user can change the decomposition from a drop down menu and the chart bars and axes will be dynamically updated.
Having the ability to change the chart bar decompositions allows the user to explore visualize the CO<sub>2</sub> emissions impact of each category in a glimpse. Finally, a category could have the largest amount of total pollution due to having the largest number of travelers and not due to inefficiency in travel plans and the average pollutions bar is here to capture that. 


<div class="img_row">
	<img class="col three" src="{{site.baseurl}}/img/portfolio/info-viz/iskander3.png" alt="Old website home page">
</div>
<div class="col three caption">
	House Bar Chart
</div>

<h3 class="thick">go take a look!</h3>
<br/>
<span class="contacticon center">
	<a href="https://iskandergaba.github.io/mosig2-info-viz-project/" target="_blank"><i class="fas fa-external-link-alt"></i></a>
	<a href="https://github.com/iskandergaba/mosig2-info-viz-project" target="_blank"><i class="fab fa-github"></i></a>
</span>
