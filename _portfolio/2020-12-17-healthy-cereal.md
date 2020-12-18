---
layout: page
title: Healthy Cereals? A Dad's Pursuit of Healthy Kid's Cereals
date: 2020-12-17 9:00
permalink: /portfolio/healthycereal
image: assets/images/cereal.jpg
category: Blog
---


WHAT MAKES A CEREAL HEALTHY? AN EXPLORATION
-------------------------------------------

I am using the USDA, FDA, and other reputable sources to determine the
attributes of a healthy cereal.I will state my assumptions of what is
considered healthy below and will be using those as a guide for
determining the types of clusters and to assist my recommendations.

**HEALTHY GUIDELINES**

-   **Sugar content:** .25g of sugar for every 4g of cereal.
    -   (**Reference**:
        <a href="https://www.fns.usda.gov/tn/choose-breakfast-cereals-are-lower-sugar" class="uri">https://www.fns.usda.gov/tn/choose-breakfast-cereals-are-lower-sugar</a>)
-   **Fiber at least 3 grams per serving**
    -   (**Reference**:
        <a href="https://foodcorps.org/cms/assets/uploads/2018/01/Healthy-School-Program-Resource-Guide-1-11.pdf" class="uri">https://foodcorps.org/cms/assets/uploads/2018/01/Healthy-School-Program-Resource-Guide-1-11.pdf</a>)
-   **Sodium content:**
    -   Low sodium: 5% or less per serving size
    -   High sodium: 20% or more per serving size
    -   (**Reference**:
        <a href="https://www.fda.gov/food/nutrition-education-resources-materials/sodium-your-diet" class="uri">https://www.fda.gov/food/nutrition-education-resources-materials/sodium-your-diet</a>)

**NOTE** I do not include fat content because fat can be healthy
depending on the type which isn’t stated in the data set. Also, vitamins
are not broken into types in this data set so it is difficult to use that
as an indicator since many cereals add vitamins.

Here are the **libraries** I used in this project:
``` r
library(tidyverse)
library(caret)
library(factoextra)
library(cluster)
library(fpc)
library(fastDummies)
set.seed(15)
```

Outliers are Informative in this data set
----------------------------------------

![image](/assets/images/cereal_img/chunk1.png)

After investigating the outliers in this data set, they will be
informative for clustering. For example, calories and weight outliers
are the same type of cereals. These cereals all appear on the same shelf
and have lower ratings in addition to having higher calories and weight
(see above). Surprisingly, many of them have higher sugar levels
compared to the other cereals, however, it could be due to the dried
fruits which adds to the heavier weight of the cereal as well.

Possible Relationships in the data set
-------------------------------------

![](/assets/images/cereal_img/chunk2.png)

-   **Positively Correlated**
    -   Fiber and potassium have a high correlation to one another,
    -   Calorie to weight and sugar,
    -   Fiber to protein, potassium, fiber, and rating
-   **Negatively Correlated**
    -   Rating to calories and sugars

## **Summary** <br>
Most of the significantly correlated variables intuitively
makes sense like ratings being positively correlated to fiber as those
tend to be considered “healthier” cereals and those with higher
calories/sugars had a lower rating. Also, interestingly it seems shelf 3
tends to have cereals with higher levels of potassium, fiber, and
protein. Shelf 2 seems to have cereals with higher sugar, low amounts of
protein, lower amounts of fiber. Depending on the height of the shelves
could make sense due to the height of a average child riding in a cart
or walking in the cereal aisle. I will have to explore below why
potassium is related to fiber and protein. I found studies on the
relationship between sodium and potassium but nothing explicitly
relating it to protein and fiber.

Determining a value for K.
--------------------------

![](/assets/images/cereal_img/unnamed-chunk-15-1.png)


![](/assets/images/cereal_img/unnamed-chunk-15-2.png)

I am going to use the WSS and Silhouette methods to give me a starting
point for finding optimal k. Often times there is not a “best” approach
to always optimizing k. I will start analyzing k=6 and see how the
cereals are grouped and make adjustments if needed from there.

Why I am using Hierachical Clustering
-------------------------------------

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
