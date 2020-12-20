---
layout: page
title: Healthy Cereals? A Dad's Pursuit of Healthy Kid's Cereals
permalink: /portfolio/healthycereal/
nav-menu: false
category: Blog
---
<!-- Main -->
<div id="main" class="alt">

<!-- One -->
<section id="one">
	<div class="inner">
		<header class="major">
			<h1>Healthy Cereal:</h1>
      <h3>A Dad's Adventure for the Digestive Health of His Children</h3>
		</header>
<span><img src="{% link assets/images/cereal_img/adventure.jpg %}" alt=""/></span>
<!-- Content -->
<h2 id="content">Gathering the Noble Tools of Health</h2>
<p>Let us start our pursuit of health with gathering some guidelines from the the USDA, FDA, and other reputable sources.</p>
<span><img src="{% link assets/images/cereal_img/weapons.png %}" alt=""/>

<dl>
  <dt>
	<a href="https://www.fns.usda.gov/tn/choose-breakfast-cereals-are-lower-sugar" class="icon fas fa-dragon">  Sugar Content (USDA)</a>
	</dt>
	<dd>
  <li>At most .25 grams of sugar for every 4g of cereal.</li>
	</dd>
<hr />

<dt>
<a href="https://foodcorps.org/cms/assets/uploads/2018/01/Healthy-School-Program-Resource-Guide-1-11.pdf" class="icon fas fa-dungeon"> Fiber (FoodCorps)</a>
</dt>
<dd>
<li>At least 3 grams per serving.</li>
</dd>

<hr />
<dt>
<a href="https://www.fda.gov/food/nutrition-education-resources-materials/sodium-your-diet" class="icon  fas fa-tree"> Sodium (FDA)
</a>
</dt>
<dd>
  <li>Low sodium: <b>5% or less</b> per serving size.</li>
  <li>High sodium: <b>20% or more</b> per serving size.</li>
  </dd>

<i>
<br>
<p>**I do not include fat content because fat can be healthy
depending on the type which isn’t stated in the data set. Also, vitamins
are not broken into types in this data set so it is difficult to use that
as an indicator since many cereals add vitamins.
</p>
</i>
<hr />
<h2>Are There Any Out-"liars" in Our Way to Truth?</h2>

<span><img src="{% link assets/images/cereal_img/boxplot2.png %}" alt=""/></span>
<br>
<br>
<p>After interrogating the out-"liars" in this data set, I discovered they were telling the truth
about the cereals they were representing. Two such fellows, let's call them, "Nuts" and "Fruity",
appeared on the same shelf and had a lower customer rating. They also had higher calories and weight.
Surprisingly, many of them had higher sugar levels
compared to the other cereals, however, it could be due to the dried
fruits (high in sugar often) and also the nuts which would add to the heavier weight of the cereal.</p>
<hr />

<h1 class="icon fas fa-ghost"> The Variables Meet...</h1>

<span><img src="{% link assets/images/cereal_img/cereal_correlations.png %}" alt=""/></span>
<br>
<br>
<h2>Positive Relationships (Bigger Blue Dots)</h2>
<dd>
    <li>Fiber and potassium have a high correlation to one another. The reason being that wheat bran is higher in potassium.</li>
    <li>Calorie is related to weight because the higher weighted cereals have fruits and nuts. These are higher calorie and weight more.</li>
		<li>Calorie is also related to sugar. Again this is intuitive since sugar is high in calories.</li>
    <li>Cereals higher in fiber also are considered healthier and thus have a higher customer rating </li>
		</dd>
		<hr />

<h2>Negative Relationships, <i>yeah...we all have them... </i>(Bigger Red Dots)</h2>
		<dd>
		    <li> Cereals with higher calories or high sugar have low customer ratings.</li>
		    <li>Cereals with high fiber have lower serving sizes.</li>
		    <li>Cereals that appear on shelf 3 have little in common with cereals on shelves 1 and 2 at the grocery store</li>
				</dd>
				<hr />
<h2> The Fellowship of the Means</h2>

<span><img src="{% link assets/images/cereal_img/fellowship.jpg %}" alt=""/></span>

### K-means Clustering

K-means clustering algorithm is based on the number of clusters you
choose. For example, let’s say that you want 3 clusters. K-means
randomly chooses 3 starting points each representing a cluster, then
each of those starting points chooses the closest data point based on a
distance calculation (see above code). Those two points for each cluster
forms the 3 new clusters and form a centroid (the average of the two
points). The algorithm then starts again for choosing a third point to
add to each cluster and then continues that pattern until all points are
in each of the 3 clusters.

### Hierarchical Clustering

Hierarchical Clustering can begin with the entire data set, then splits
into two clusters, and continues splitting into smaller and smaller
clusters, until all data points are paired with another point or by
itself. The end of the hierarchical clustering is called leaves and the
partitions above the leaves are called branches. This method is called
Diversive Analysis Clustering or DIANA.

The other approach is to reverse this process by starting with the
leaves and reversing the above process until all points are a single
cluster. This method is called Agglomerative Nesting or AGNES.

### Hierarchical Clustering is Better

The best method for this problem would be Hierarchical clustering.
K-Means tends to favor more globular clusters and it only has one method
on how the clusters are formed. Hierarchical clusters have many more
methods to control how we can link the data to form the clusters. This
will be more helpful since I already am very familiar with the types of
cereals in this data set and inspecting the different methods for
clustering in the dendrogram will allow me to choose the best way to
cluster the cereals. I am favoring more control on the clusters that are
formed.

Hierarchical Analysis of Cereals
================================

Single Linkage: The Worst Linkage
---------------------------------

![](/assets/images/cereal_img/unnamed-chunk-17-1.png)


![](/assets/images/cereal_img/unnamed-chunk-17-2.png)

Cluster 2 contains about 85% of all the cereals. The cereals in that
cluster are of different types like Trix and Great Grains Pecans. This
method did not do a good job clustering the cereals to help me recommend
healthy types of cereals.

Average Linkage: Better than Single
-----------------------------------

![](/assets/images/cereal_img/unnamed-chunk-18-1.png)![](/assets/images/cereal_img/unnamed-chunk-18-2.png)

This linkage method looks very similar to single with the exception of
the larger cluster having a few small clusters inside of it. It does
seem to be an improvement over single linkage as there is more cluster
separation and clusters are more compact, comparatively.

Complete Linkage: Second Best Linkage Method
--------------------------------------------

![](/assets/images/cereal_img/unnamed-chunk-19-1.png)![](/assets/images/cereal_img/unnamed-chunk-19-2.png)

The clusters look fairly separated and fairly uniformly distributed.
Cluster 5 overlaps more significantly with 4 and 2. However, looking
closer at the dendrogram it does seem that it did a good job grouping
the cereals into like categories.

Ward’s Method: The Best Method
------------------------------

![](/assets/images/cereal_img/unnamed-chunk-20-1.png)![](/assets/images/cereal_img/unnamed-chunk-20-2.png)

I think Ward’s is the best method for the cereal recommendations as the
clusters are more separate and compact (except cluster 3 which overlaps
5). For only having 73 cereals, I think the above dendrogram does a good
job of classifying the clusters. For example, All Bran brand cereals are
in their own cluster and on the same branch as Grape Nuts, Quaker Oat
Squares, etc… While Corn Pops is with Trix and Fruity Pebbles on it’s
own branch.

AC Confirms My Analysis
=======================

**AC Values**
-------------

    ##   average    single  complete      ward
    ## 0.7775099 0.5767978 0.8426844 0.9002626

I am going with the Ward method due to the visualizations and with the
strength of the structure being the highest at .90 and due to my
analysis aligning with these results as well.

Test Partitioning: Clusters have Very Good Stability
====================================================

### Preparation for Cluster Comparison and Classification

I have to see if the cereals that the algorithm grouped together would still be put together if I took a smaller subset of that data set. If the algorithm still puts the cereals together then the helps give me more confidence that the attributes of the cereals are being grouped together and not random chance.

 Ward’s Method on Smaller Subset of Data Set
--------------------------------------------

![](/assets/images/cereal_img/unnamed-chunk-25-1.png)![](/assets/images/cereal_img/unnamed-chunk-25-2.png)

Cluster Stability Comparison
-----------------------------

![](/assets/images/cereal_img/unnamed-chunk-26-1.png)

### Very Good Cluster Stability

Besides looking like a really sweet image...14 of the 37 cereals were classified to the **same cluster
number** as the original data set. However this is misleading, the
dendrogram visualization above shows that only 1 cereal was not grouped with the same cereals. This means that
actually, 32 out of the 36 cereals were clustered the same as the
original data set. I would say that is pretty good!

Test Partitioning Trial \#2
---------------------------


![](/assets/images/cereal_img/unnamed-chunk-29-1.png)![](/assets/images/cereal_img/unnamed-chunk-29-2.png)

![](/assets/images/cereal_img/unnamed-chunk-30-1.png)

18 of the 37 or 49% of the cereals were classified to the **same cluster
number** as the original data set. However this is misleading again (these graphs try to get you), the
dendrogram visualization above shows all the cereals were grouped
with the same cereals as the larger data set. Again that is really good!

AGNES meets DIANA
-----------------

One last test of cluster stability is using Diversive Hierarchical
Clustering and see how it compares to Agglomerative Hierarchical
Clustering. Again, I am repeating the same process as above so I will
only show the output.

DIANA Comparison
----------------

![](/assets/images/cereal_img/unnamed-chunk-31-1.png)![](/assets/images/cereal_img/unnamed-chunk-31-2.png)

### Very Good Cluster Stability, Again!

Performed the DIANA hierarchical clustering and compared it with the
AGNES hierarchical clustering to see if the clusters are similar for
both methods which also gives evidence that the clusters are stable.
Looking above you can see about 51 of the 73 or about 80% cereals were grouped
the same as AGNES. I believe this gives great evidence of good
clustering stability as two different clustering algorithms formed
mostly the same cluster groupings. What this means is that we can
trust our cluster groupings.

Clustering Stability Conclusion
-------------------------------

I believe that I can high confidence that the clusters are stable based
on the two trial partition results being very high. Also, DIANA having
80% cluster similarity, I believe gives even greater confidence due to
it being a different method for hierarchical clustering but still having
the majority of clusters groups the same as our original clustering from
the Ward’s Method using Agnes.

Cereal Cluster Analysis
=======================

Clusters 1 & 2
--------------
![](/assets/images/cereal_img/unnamed-chunk-34-1.png)

-   <span style="color: #FF0000;">**Cluster 1: Could be Recommended
    Cereals**</span><br>
    -   **located on shelf 3** <br> <span  style="color: #FF0000;">+
    **Attributes:**
    -   lower sugar
    -   highest fiber
    -   lowest calories
    -   lowest carbs
    -   highest protein
    -   highest rating </span>

    **The big reveal: Cluster 1 cereals are...**
      - 100% Bran
      - All Bran		
      - All Bran with Extra Fiber (I didn't know it needed extra fiber...)

All of **cluster 1** cereals all have high sodium levels. Could be on
      the recommendation list due to the other benefits like protein and
      fiber. However, kids probably would not typically pick these cereals.


-   <span style="color: #17A589;">**Cluster 2: Not Recommended
    Cereals**</span><br>
    -   **located on shelf 3** <br>
    <span  style="color: #17A589;">+ **Attributes:**
    -   higher calories
    -   lower rating </span> <br>

    **The big reveal: Cluster 2 cereals are...**
      - 100% Natural Bran
      - Basic 4
      - Fruit & Fiber Dates, Walnuts, and Oats
      - Fruitful Bran
      - Just Right Fruit & Nut
      - Muesli Raisins, Dates, & Almonds
      - Muesli Raisins, Peaches, & Pecans
      - Mueslix Crispy Blend
      - Nutri-Grain Almond Raisin
      - Oatmeal Raisin Crisp
      - Post Nat. Raisin Bran
      - Raisin Bran
      - Total Raisin Bran

All except one cereal of **cluster 2** cereals have high sodium and 7
out of 13 cereals have high sugar levels. Only 9 of the cereals have
good fiber as well.


Clusters 3 & 4
--------------

![](/assets/images/cereal_img/unnamed-chunk-37-1.png)

-   <span style="color: #FF0000;">**Cluster 3: Not Recommended
    Cereals**</span><br>
    -   **located on shelves 1 & 2**<br>
        <span  style="color: #FF0000;"> + **Attributes:**
        -   highest sugar
        -   low fiber
        -   lowest protein
        -   lower carbs
        -   lowest rating </span>

        **The big reveal: Cluster 3 cereals are...**
        - Apple Cinnamon Cheerios
        - Apple Jacks
        - Cap'n'Crunch
        - Cinnamon Toast Crunch
        - Cocoa Puffs
        - Corn Pops
        - Count Chocula
        - Crispy Wheat & Raisins
        - Froot Loops
        - Frosted Flakes
        - Fruity Pebbles
        - Golden Crisp
        - Golden Grahams
        - Honey Graham Oh's
        - Honey Nut Cheerios
        - Honey-Comb
        - Lucky Charms
        - Multi-Grain Cheerios
        - Nut & Honey Crunch
        - Smacks

13 of the cereals in **cluster 3** have unhealthy sugar levels and none
of them have healthy fiber or sodium levels. Kids should not consume
these.

-   <span style="color: #17A589;">**Cluster 4: Not Recommended
    Cereal**</span><br>
    -   **located on shelves 1 & 3**<br>
        <span  style="color: #17A589;">+ **Attributes:**
        -   lower sugar
        -   lowest fiber
        -   higher protein
        -   higher rating</span>

        **The big reveal: Cluster 4 cereals are...**
        - Bran Chex
        - Bran Flakes
        - Cheerios
        - Clusters
        - Cracklin' Oat Bran
        - Grape-Nuts Flakes
        - Grape-Nuts
        - Great Grains Pecan
        - Life
        - Nutri-grain Wheat
        - Quaker Oat Squares
        - Raisin Nut Bran
        - Special K
        - Wheat Chex
        - Wheaties

13 of the cereals in **cluster 4** have healthy sugar levels. 14 cereals
**do not** have healthy fiber levels and they all have high sodium. The
only factor that cluster 3 has going for it is the sugar levels but I
don’t believe that is enough to recommend it as the other “unhealthy”
factors outweigh that benefit.

![](/assets/images/cereal_img/unnamed-chunk-40-1.png)

-   <span style="color: #FF0000;">**Cluster 5: Not Recommended
    Cereals**</span><br>
    -   **located on shelves 1 & 3**<br>
        <span  style="color: #FF0000;">+ **Attributes:**
        -   lower sugars
        -   lower fiber
        -   high sodium
        -   high carbs
        -   high vitamins</span>
-   <span style="color: #17A589;">**Cluster 6: Recommended
    Cereals**</span><br>
    -   **located on shelves 1 & 3**<br>
        <span  style="color: #17A589;"> + **Attributes:**
        -   lowest sugar
        -   lower calories
        -   lowest sodium
        -   high rating</span>

``` r
cereal %>%
  filter(cluster == 5) %>%
  select(name, cluster, healthy_sugar_lvl, healthy_fiber_lvl, high_sodium_lvl)
```

All of **cluster 5** cereals have healthy sugar levels but have high
sodium and all but one do not have enough fiber. Although they do have
high vitamins which could be a benefit but hard to determine from this
data set. Overall I don’t believe that the healthy sugar levels and high
vitamins are enough to recommend as the sodium levels are the highest
and the fiber is lower compared to the other clusters.

``` r
cereal %>%
  filter(cluster == 6) %>%
  select(name, cluster, healthy_sugar_lvl, healthy_sodium_lvl, healthy_fiber_lvl)
```

All of **cluster 6** cereals have healthy sugar levels, 7 of the cereals
have healthy sodium levels, and 5 have healthy fiber levels. Overall,
these are cereals are better for kids than the other cereals. Kids also
would eat these cereals. It also has a variety of cereals for kids to
choose from and some of them are surprising like frosted mini-wheats…who
would have guessed?!

Cereal Recommendation
---------------------

I recommend **cluster 6 cereals**\* for my children based on the reasons
listed above. However, if my kids refused those cereals then Cluster 4
would be my second recommendation due to the amount of cereals with
healthy sugar and fiber levels. Although their blood pressure might
suffer due to the sodium…parenting is not easy…<br>
