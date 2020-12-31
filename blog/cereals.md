---
layout: page
title: Healthy Cereals? A Dad's Pursuit of Healthy Kid's Cereals
permalink: /blog/cereals.html
nav-menu: false
category: Page
---

<!-- Main -->
<div id="main" class="alt">

<!-- One -->
<section id="one">
	<div class="inner">
		<header class="major">
			<h1>HEALTHY CEREAL:</h1>
      <h2><i>A Dad's Quest to Find Healthy Cereal for His Kids Using Data Science</i></h2>
		</header>
		<span class="image"><img src="{% link assets/images/cereal_img/adventure.jpg %}" alt="" /></span>
<p> As a dad of two kids, I didn't realize how difficult it was to keep your children <b>"regular"</b>. [<i>If you know what I mean...</i>] My wife and I have struggled to make sure the <b>"pipes are flowing freely"</b> and comfortably. [<i>Again, are you picking up what I am throwing down?</i>] On top of that, finding cereals that my kids will eat regularly is a challenge, and once you find a cereal they like a week later, they are tired of eating it. What could I do to solve this problem? As I thought about it, I realized that I could use my Data Science skills to help my children successfully <b>"drop off the kids at the pool..."</b>. [<i>I had one more euphemism for a bowel movement in me.</i>]</p>

<!-- Content -->
<section id="two">
	<div class="inner">
<header class="major">
<h2 id="content">GATHERING THE NOBLE TOOLS OF HEALTH</h2>
</header>
<span class="image"><img src="{% link assets/images/cereal_img/weapons.png %}" alt="Exploratory Data Analysis"  alt="Unsupervised Learning"/></span>
<dl>
<dt>
<br>
Before we begin our quest, we need to make sure we have the right supplies. Below you will find the "supplies" I am bringing on our quest. These "supplies" are recommendations for healthy levels of sugar, fiber, and sodium.</dt>
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

<header class="major">
<h2><a class="icon fas fa-ghost"></a> THE CEREALS MEET <a class="icon fas fa-ghost"> ...</a></h2>
</header>
<p> I explored the different relationships that existed between different cereals in my quest. Here are my findings:</p>
<dd>
    <li>Cereals with higher fiber and potassium have a high correlation to one another. The reason being that wheat bran is higher in potassium and the cereals with high fiber had wheat bran. These cereals also were rated higher by consumers and also had a lower serving size.</li>
    <li>The heavier cereals had fruits and nuts included in them, which also meant they had higher calories.</li>
		<li>This next one will be real surprising, the high sugar cereals had high calories! (Bet you didn't see that coming...)</li>
		<li>Cereals in the grocery store that appear on the third shelf have little in common with cereals on the first and second shelf at the grocery store.</li>
				<br>
				<i>[If you picture yourself going down the cereal aisle with one or more children strapped into the shopping cart or walking beside the cart, then you can guess what kind of cereals are positioned on shelves 1 and 2...]</i>
				</dd>
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

<p>Well, my friends our journey has come to an end. If you are interested in the more technical and the less whimsical details of this quest, you can continue on here:<a href="/portfolio/healthycereals.html">The More Technical, Less Whimsical Journey</a>. Thanks for journeying with me and the quest will continue!</p>
