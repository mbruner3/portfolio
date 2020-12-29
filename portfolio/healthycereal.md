---
layout: page
title: Healthy Cereals? A Dad's Pursuit of Healthy Kid's Cereals
permalink: /portfolio/healthycereal.html
nav-menu: false
category: Page
---

<!-- Main -->
<div id="main">

<!-- One -->
<section id="one">
	<div class="inner">
		<header class="major">
			<h1>HEALTHY CEREAL:</h1>
      <h2><i>A Dad's Quest to Find Healthy Cereal for His Kids Using Data Science</i></h2>
		</header>
		<span class="image"><img src="{% link assets/images/cereal_img/adventure.jpg %}" alt="" /></span>
<p> As a dad of two kids, I didn't realize how difficult it was to keep your children <b>"regular"</b>. [<i>If you know what I mean...</i>] My wife and I have struggled to make sure the <b>"pipes are flowing freely"</b> and comfortably. [<i>Again, are you picking up what I am throwing down?</i>] On top of that, finding cereals that my kids will eat regularly is a challenge, and once you find a cereal they like a week later, they are tired of eating it. What could I do to solve this problem? As I thought about it, I realized that I could use my Data Science skills to help my children successfully <b>"drop off the kids at the pool..."</b>. [<i>I had one more euphemism for a bowel movement in me.</i>]</p>

<p> The post below will assume that you have very little understanding of Data Science. If you are interested in a more technical write-up, including my code, you will find it in a link at the end of our quest together. I created this post for those kindred hearts who are curious about this topic.</p>

<p> I will be using an unsupervised machine learning (ML) algorithm called "Hierarchical Clustering" as my primary weapon on my quest. I will discuss why and what it is later in our journey. Below I briefly describe two types of machine learning algorithms: <b>supervised and unsupervised.</b></p>
<h3><u>Supervised ML Algorithms</u></h3>

<p><span class="image left"><img src= "https://miro.medium.com/max/1280/1*589X2eXJJkatGRG-z-s_oA.png" alt="Supervised Learning"/></span> Supervised ML algorithms use a subset of the data set to model the problem to be solved. The model's predictive power is then tested on the "unseen" portion of the data set. Based on how the model performs on the unseen data, you would either improve it or decide the model is "good enough." Typically this type of algorithm would be used for making a prediction. Two practical examples are if a bank wanted to know if a person is likely to default on a loan or predicting an increase of a stock portfolio.</p>

<h3><u>Unsupervised ML Algorithms</u></h3>
<p><span class="image right"><img src= "https://miro.medium.com/max/2232/1*BKvYt1EHtzHOd_HWjm-Jrw.png"  alt="Unsupervised Learning"/></span> These algorithms do not need a smaller subset of the data to train it. The algorithm will take the data in and give you results on the other side without your supervision. Usually, the results will be in the form of groupings of the data called "clusters." The work of the Data Scientist is to analyze the algorithm groupings to draw conclusions about the clusters. A company wanting to do targeted promotions could use an unsupervised ML algorithm to help with this.</p>
<hr />

<!-- Content -->
<section id="two">
	<div class="inner">
<header class="major">
<h2 id="content">GATHERING THE NOBLE TOOLS OF HEALTH</h2>
</header>
<span class="image"><img src="{% link assets/images/cereal_img/weapons.png %}" alt="Exploratory Data Analysis"  alt="Unsupervised Learning"/></span>
Before we begin our quest, we need to make sure we have the right supplies. Below you will find the "supplies" I am bringing on our quest. These "supplies" are recommendations for healthy levels of sugar, fiber, and sodium.
<dl>
  <dt>
	<br>
	<a href="https://www.fns.usda.gov/tn/choose-breakfast-cereals-are-lower-sugar" class="icon fas fa-first-aid">  Sugar Content (USDA)</a>
	</dt>
		<dd>
  		<li>At most .25 grams of sugar for every 4g of cereal.</li>
		</dd>
			<br>
				<dt>
					<a href="https://foodcorps.org/cms/assets/uploads/2018/01/Healthy-School-Program-Resource-Guide-1-11.pdf" class="icon fas fa-toilet-paper"> Fiber (FoodCorps)</a>
				</dt>
			<dd>
		<li>At least 3 grams per serving.</li>
			</dd>
				<br>
		<dt>
			<a href="https://www.fda.gov/food/nutrition-education-resources-materials/sodium-your-diet" class="icon  fas fa-pizza-slice"> Sodium (FDA)</a>
		</dt>
		<dd>
  		<li>Low sodium: <b>5% or less</b> per serving size.</li>
  		<li>High sodium: <b>20% or more</b> per serving size.</li>
		</dd>
		<br>
		<i>
		<p><b>Note</b>: I do not include fat content because fat can be healthy
		depending on the type which isn’t stated in the data set. Also, vitamins
		are not broken into types in this data set so it is difficult to use that
		as an indicator since many cereals add vitamins.
		</p>
		</i>
</dl>
<hr />

<section id="three">
	<div class="inner">
<header class="major">
<h2>DETECTING THE OUT-"LIARS"</h2>
</header>
<span><img src="{% link assets/images/cereal_img/boxplot2.png %}" alt=""/></span>
<br>
<br>
<p>After interrogating the out-"liars" in this data set, I discovered they were telling the truth about the cereals they were representing. Two such fellows, let's call them <b>"Nutty" and "Fruity."</b>  They both appeared on the same shelf and had a lower customer rating. These fellows <b>weighed more</b> than others and had <b>many calories</b>. Surprisingly, many of the cereals like these fellows had higher sugar levels. The reason is due to the <b>dried fruits</b> they had inside, which also <b>added more weight</b>.</p>
<hr />
<header class="major">
<h2><a class="icon fas fa-ghost"></a> THE VARIABLES MEET... <a class="icon fas fa-ghost"></a></h2>
</header>
<span><img src="{% link assets/images/cereal_img/cereal_correlations.png %}" alt=""/></span>
<br>
<br>
<h2>Positive Relationships (Bigger Blue Dots)</h2>
<dd>
    <li>Fiber and potassium have a high correlation to one another. The reason being that wheat bran is higher in potassium.</li>
    <li>Calories is related to weight because the higher weighted cereals have fruits and nuts.</li>
		<li>Calories is also related to sugar. Again this is intuitive since sugar is high in calories.</li>
    <li>Cereals higher in fiber also are considered healthier and thus have a higher customer rating. </li>
		</dd>
		<hr />

<h2>Negative Relationships, <i>yeah...we all have them... </i>(Bigger Red Dots)</h2>
		<dd>
		    <li>Cereals with higher calories or high sugar have low customer ratings.</li>
		    <li>Cereals with high fiber have lower serving sizes.</li>
		    <li>Cereals that appear on shelf 3 have little in common with cereals on shelves 1 and 2 at the grocery store.</li>
				<br>
				<i>[If you picture yourself going down the cereal aisle with a children strapped into the shopping cart, then all will become clear on what cereals are positioned on shelves 1 and 2...]</i>
				</dd>
				<hr />
				</div>
				</section>

<header class="major">
<h2>THE FELLOWSHIP OF THE CLUSTERS</h2>
</header>
<p> <span class="image left"><img src="{% link assets/images/cereal_img/fellowship.jpg %}" alt="Hierarchical Clustering" /></span>I promised to tell you about Hierarchical Clustering earlier, and now that time has come. I will describe the clustering algorithm and why I choose Hierarchical Clustering to wield on my quest.</p>

<h3>Hierarchical Clustering</h3>

<p><span class="image right"><img src="https://miro.medium.com/max/1608/1*ICdqpcL62G1q_kIlVszrrg.png"  alt="Hierarchical Clustering"/></span>The Hierarchical Clustering algorithm, using the Diversive method or DIANA, starts with the entire data set and splits it into two groups. It continues dividing the data set into smaller and smaller groups until all data points are paired with another data point or by themselves. Each division of the data set is called a "branch." The algorithm ends when each data point is paired or is by itself.

The other method reverses the above process, and it is called "Agglomerative Nesting" or AGNES.</p>

<p>The Hierarchical Clustering algorithm has many methods to control how it groups data points. More control in this problem is better because I am familiar with the types of cereals in this data set. I will inspect the groups formed in the chart or dendrogram (see the illustration above). Based on how the groupings formed, I will choose the best method for grouping the cereals.</p>
<hr />

<header class="major">
<h2> THE QUEST ENDS</h2>
</header>
<p>The quest is drawing to a close. Below you will find the conclusion of the adventure and what cereals are healthy. The recommendations will be surprising!</p>
<h3> THE WISE GRAPH</h3>
<span><img src="{% link assets/images/cereal_img/recommendationcluster.png	%}" alt=""/></span>
<br>
<br>
<p> The wise-old graph told us the following about the treasure we were seeking. It said,"The grouping of cereals that you seek has lower sugar, calories, sodium, and weight compared to the other groupings." While that description was helpful, we asked, "Can you tell us O'Wise Graph, what are the names of these cereals?" The graph replied, "I cannot say but the one you seek is The TABLE, TAble, table..." With those last words the Graph disappeared...</p>

<h3>THE TABLE</h3>

<span><img src="{% link assets/images/cereal_img/thetable.png	%}" alt=""/></span>
<p> We followed the path down to where we believed The Table to live. We entered the dwelling of The Table and with a startling shout it said, "WHO GOES THERE?!" We replied, "We are humble travelers seeking healthy cereal recommendations so our children can be free of The Evil Constipation." "A very noble quest, indeed!", the Table said with admiration in it's voice. The Table continued, "Very well I will tell you my recommendations, the cereals you seek all have healthy sugar levels, mostly healthy sodium levels, and mostly healthy fiber levels Overall, these are cereals are better for kids than the other cereals. Your children will be more likely eat these cereals too. Oh, and if they get tired of one cereal, there is a variety of options!"</p>

<p>Well, my friends our journey has come to an end. If you are interested in the more technical and the less whimsical details of this quest, you can continue on here: The More Technical, Less Whimsical Journey. I am also constantly learning so if there are improvements that you can suggest for my more technical write-up, please let me know by sending me a message below.</p>
