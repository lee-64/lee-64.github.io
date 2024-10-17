---
layout: page
title: Interactive Music Analytics
description: with background image
img: assets/img/1.jpg
importance: 1
category: university
related_publications: false
---

I created the **_Spotify Insights Hub_** for my final project of the ITP-216 **Applied Python** course. Creating this interactive data
dashboard marked my first stab at web development. I thoroughly enjoyed the development process and quickly made it as feature-rich
and deployment-ready as I could using the material I had learned thus far in the course.

To begin, I created a _simple_ (or, at the time, what I thought would be simple) Flask framework of throwing every application function and route in one Python file.
I quickly abandoned this project structure after 300+ lines of routes pointing every which way in the long, vertical column that was my codespace.
Rather, I explored the <a href="https://flask.palletsprojects.com/en/3.0.x/">Flask documentation</a> and taught myself about the common practice of building your Flask app
around an _application factory_. The most valuable Flask webdev technique I learned here was that of <a href="https://flask.palletsprojects.com/en/3.0.x/blueprints/">Blueprints</a>.
Modular application design helped me continue beefing up my project by staying organized (and I'm sure helped my professor grade it). Here is how my
project structure changed:


testing

<div class="container">
  <div class="row">
    <div class="col-sm">
      <pre>
      <code>
├── interactive_music_analytics/
│   ├── <strong>app.py</strong>
│   ├── csv_to_db.py
│   ├── templates/
│   │   ├── ...
      </code>
      </pre>
    </div>
    <div class="col-sm">
      <pre>
      <code>
├── interactive_music_analytics/
│   ├── <strong>__init__.py</strong>
│   ├── <strong>artist_metrics.py</strong>
│   ├── config.py
│   ├── <strong>dbhelper.py</strong>
│   ├── blog.py
│   ├── templates/
│   │   ├── ...
      </code>
      </pre>
    </div>
  </div>
</div>

At a glance, one app.py file with everything made the project structure seem simple, but approaching the project after leaving it for the night became increasingly difficult.
I chose to structure my application as a Python package with `__init__.py` to ensure better organization and scalability if the application was to grow. Currently, the project is
simple enough that I could do without this approach, but it is a good technique I wished to practice for future applications. One of the key benefits I've learned is how this structure
makes use of relative `import` statements, reducing potential naming conflicts and improving clarity. 

The organizational programming skills I have learned from this project are, in a way, so foundational that they have shaped and will continue to shape how I approach problems as an
engineer.


The project features 







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

You can also put regular text between your rows of images, even citations {% cite einstein1950meaning %}.
Say you wanted to write a bit about your project before you posted the rest of the images.
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
