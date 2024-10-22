---
layout: page
title: Skincare Routine Manager
description: An interactive skincare routine website that visualizes the nuanced interactions between products
img: assets/img/skincare_project_thumbnail.jpg
importance: 2
category: personal
giscus_comments: false
---


Skincare has <a href="https://trends.google.com/trends/explore?date=all&q=skincare&hl=en">exploded in popularity</a> in recent years. People want to treat
their skin well, which is great! However, the market is extremely saturated; an unnavigable volume of brands and products cover your pharmacy shelves, your favorite
influencer just announced their very own skincare product line, and unrealistic beauty standards tie this all together by making regular people feel like they
need to splurge on the trendiest snake oil serum to get the immediate results they're hoping for.

The skincare industry is worth an estimated <a href="https://www.statista.com/forecasts/1268473/worldwide-revenue-skin-care-market#:~:text=This%20statistic%20depicts%20the%20estimated,be%20189.3%20billion%20U.S.%20dollars.">$180.3 billion</a>
globally--there is no changing the market's over-saturation. 
However, I have identified and provided a solution for the average consumer overwhelmed by choice.

### The problem:
>A single skincare product typically specializes in one component of a routine, such as moisturizing or cleansing. However, customers' skincare routines are rarely just one, standalone product.
Many customers have lengthy, multi-step skincare routines with many different products to juggle and keep straight. 
>
>Sometimes products might negatively react when used alongside another, actually worsening your skin. Or, there might be a missed opportunity for a synergy between products in a routine,
saving the customer money on unnecessary extra steps.

### The solution:
>My Skincare Routine Manager project provides users with the data-driven insights behind their routine, highlighting conflicts between known conflicting ingredients, like benzoyl peroxide and retinol, and
illustrating synergies between proven ingredient pairings, such as AHAs and BHAs.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/skincare_conflicts.png" title="Conflicts" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/skincare_synergies.png" title="Synergies" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Routine conflicts (left) and synergies (right) network visualizations using Plotly's <a href="https://github.com/plotly/dash-cytoscape">Dash Cytoscape</a>. 
</div>




This visualization highlights links between active ingredients within products that either contradict (or pair well, if the synergy option is selected) with other ingredients in the routine.
Each node is a product within the user's routine, and the color of that node gets more intense the more links to other nodes it has. The edges between the nodes are directional, pointing outwards 
from the product that specific ingredient came from. That's why there are two links connecting products; one for each ingredient of the conflict (or synergy) pairing.

<br/>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/skincare_cytoscape_zoom.png" title="Conflict" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Nodes are products and directional edges are ingredients, each stemming from one of the products in the pairing.
</div>


This project was (and continues to be) an incredibly valuable learning experience for me. It's built on Flask, iterating on the Flask techniques I've implemented
in prior projects. It has a more sophisticated account creation, sign in, and session-management functionality than I've previously worked with, powered by the Python SQLite library.
Developing the routine manager tool had the steepest learning curve of this whole project. I taught myself basic Javascript to create the dynamic routine manager, fully organizable by the user,
and equipped with product name autofill capabilities. I'm particularly proud of how the routine manager feature turned out.

<br/>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/skincare_edit_routine.png" title="Editing Routine" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Draggable and customizable sections and products using JavaScript library <a href="https://jqueryui.com">jQuery</a>.
</div>