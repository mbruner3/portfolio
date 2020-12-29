---
layout: home
title: Home
landing-title: 'Mark Bruner'
description: null
image: null
author: null
show_tile: false
---

<!-- Main -->
<div id="main">

<!-- Banner -->
<section id="banner" class="major">
  <div class="inner">
      <header class="major">
          <h1>Mark Bruner</h1>
      </header>
      <div class="content">
          <ul class="actions">
              <li><a href="#one" class="button scrolly">My Projects</a></li>
          </ul>
      </div>
  </div>
</section>
      <!-- One -->
      <section id="one">
      	<div class="inner">
      		<header class="major">
      			<h2>About Me</h2>
      		</header>
      		<p>My journey began one warm summer evening as my mom headed to the delivery room... just kidding, I won't go that far back. Who am I?
            I am an analytical creative who sees data exploration as a mystery waiting to be solved, and I am the key to unlocking the answers. Those answers can bring change.
            Change that will impact individuals, companies, governments, nations, and possibly even the world.
            I believe we should use our talents to make the world a better place for all. My contribution will be through data science. </p>
            <p>   Discover more about me through my portfolio, blog, LinkedIn profile, and resume.
              Please don't hesitate to reach out to me with any questions or comments. Enjoy your time here!
          </p>
      	</div>
          <div class="inner">
            <ul class="icons">
              {% if site.twitter_url %}
              <li><a href="{{ site.twitter_url }}" class="icon alt fa-twitter" target="_blank"><span class="label">Twitter</span></a></li>
              {% endif %}
              {% if site.googleplus_url %}
              <li><a href="{{ site.googleplus_url }}" class="icon alt fa-google-plus" target="_blank"><span class="label">Google+</span></a></li>
              {% endif %}
              {% if site.facebook_url %}
              <li><a href="{{ site.facebook_url }}" class="icon alt fa-facebook" target="_blank"><span class="label">Facebook</span></a></li>
              {% endif %}
              {% if site.instagram_url %}
              <li><a href="{{ site.instagram_url }}" class="icon alt fa-instagram" target="_blank"><span class="label">Instagram</span></a></li>
              {% endif %}
              {% if site.pinterest_url %}
              <li><a href="{{ site.pinterest_url }}" class="icon alt fa-pinterest" target="_blank"><span class="label">Pinterest</span></a></li>
              {% endif %}
              {% if site.gitlab_url %}
              <li><a href="{{ site.gitlab_url }}" class="icon alt fa-gitlab" target="_blank"><span class="label">GitLab</span></a></li>
              {% endif %}
              {% if site.github_url %}
              <li><a href="/assets/images/MarkBrunerResume.pdf" class="icon alt fa-file-text fa-2x" target="_blank"><span class="label">Resume</span></a><p>Resume</p></li>
              {% endif %}
              {% if site.slack_url %}
              <li><a href="{{ site.slack_url }}" class="icon alt fa-slack" target="_blank"><span class="label">Slack</span></a></li>
              {% endif %}
              {% if site.linkedin_url %}
              <li><a href="{{ site.linkedin_url }}" class="icon alt fa-linkedin fa-2x" target="_blank"><span class="label">LinkedIn</span></a><p>LinkedIn</p></li>
              {% endif %}

      <!-- Two -->

      <section id="two" class="spotlights">
      <section>
      		<a href="/portfolio/" class="image">
      			<img src="{% link assets/images/fallhome.png%}" alt="portfolio" data-position="top center" />
      		</a>
      		<div class="content">
      			<div>
      				<header class="major">
      					<h3>My Portfolio</h3>
      				</header>
      				<p>Explore the world of data science through my passions.
                My projects will focus mainly on solving practical problems, wrestling with injustice, and environmental issues.
              The lens through which to view my portfolio is a glimpse into what makes me, me. </p>
      				<ul class="actions">
      					<li><a href="/portfolio/" class="button">Portfolio</a></li>
      				</ul>
      			</div>
      		</div>
      	</section>
      	<section>
      		<a href="/blog/" class="image">
      			<img src="{% link assets/images/zion.png%}" alt="blog" data-position="top center" />
      		</a>
      		<div class="content">
      			<div>
      				<header class="major">
      					<h3>My Blog</h3>
      				</header>
      				<p>Learn about data science as I learn about data science. I am taking all of the knowledge that I have learned and recording it here.
                As a teacher, I realized that if you want to master a topic, then teach it to others.
                I might include the occasional blog about personal interests. You never know!</p>
      				<ul class="actions">
      					<li><a href="/blog/" class="button">Blog</a></li>
      				</ul>
      			</div>
      		</div>
