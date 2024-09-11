---
layout: page
title: Skincare Routine Manager
description: a project with a background image and giscus comments
img: assets/img/3.jpg
importance: 2
category: personal
giscus_comments: true
---


Skincare has [exploded in popularity](https://trends.google.com/trends/explore?date=all&q=skincare&hl=en) in recent years. People want to treat
their skin well, which is great! However, the market is extremely saturated; an unnavigable volume of brands and products cover your pharmacy shelves, your favorite
influencer just announced their very own skincare product line, and unrealistic beauty standards tie this all together by making regular people feel like they
need to splurge on the trendiest snake oil serum to get the immediate results they're hoping for.

The skincare industry is worth an estimated [$180.3 billion](https://www.statista.com/forecasts/1268473/worldwide-revenue-skin-care-market#:~:text=This%20statistic%20depicts%20the%20estimated,be%20189.3%20billion%20U.S.%20dollars.) globally--there is no changing the market's over-saturation. 
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
        {% include figure.liquid loading="eager" path="assets/img/skincare_conflicts.png" title="conflicts" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/skincare_synergies.png" title="synergies" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Routine conflicts (left) and synergies (right) network visualizations using Plotly's <a href="https://github.com/plotly/dash-cytoscape">Dash Cytoscape</a>. 
</div>


I any, differentiated 

Many skincare products are 


However, the frustration stemming from the sheer volume of skincare brands and products, many of which market themselves as the "cure-all" for
your skin problems, led me to identify following problems:
1. It is impossibl
2. Treatments are very often used alongside other products. It is very difficult for customers to recognize


The skincare industry is worth an estimated 

With a monumental rise in demand comes an unnavigable sea of products and brands claiming to be your skin's magic solution.
this highlights two major points: there are countless snake oil salesmen 


I was tired of not knowing what face lotion to get at the store. I was tired of
purchasing expensive 





Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
