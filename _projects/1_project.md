---
layout: page
title: Spotify Insights Hub
description: An interactive music analytics dashboard
img: assets/img/spotify_logo.png
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
│   ├── dbhelper.py
│   ├── static/
│   │   ├── ...
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


The project features an artist comparison tool that generates an overlapping bar chart of two artists' average audio features using Matplotlib.
When a user inputs an artist's name, the app queries the Spotify data database to retrieve relevant statistics such as danceability, energy, acousticness, instrumentalness, and valence. 
These metrics are then visualized to provide a comparison of the artists' musical style.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/artist_compare_histo.png" title="Artist Comparison" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    UI/UX was outside the scope of this project. Enjoy the data visualizations and similarity insights instead! :)
</div>

Switching gears, the project also features a "perfect song" feature (which inspired my [DJ Recommendation Engine](https://lee-64.github.io/projects/3_project/)). Login functionality and
account creation functionality involves dynamic database queries and insertions, as well as session management--the part I found I worked with the most. I utilized Flask's session management
and SQLite for user database management. After logging in, users can input their preferences for various musical attributes using interactive sliders. 
The app then employs a K-Nearest Neighbors (KNN) algorithm from scikit-learn to identify the cluster of songs from the Spotify dataset that best matches the user's specified criteria. 
A clustering algorithm such as KNN is computationally inefficient when only a single best match is needed and for such basic numerical feature vectors as inputs. In the future, I would opt for
a similarity method like cosine similarity as a more efficient approach for such problems. Regardless, KNN still correctly predicts the user's "perfect song."

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/perf_song_sliders.png" title="Perfect Song Sliders" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/user_vs_perf_song.png" title="Perfect Song Comparison" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The user's "perfect song" match is their most similar song selected out of 20,000 tracks across these five metrics.
</div>

Embarking on this project was not without its hurdles. Initially, managing all routes and functionalities within a single Python file became cumbersome as the project grew. Transitioning to a 
modular application structure using Blueprints was a game-changer, allowing me to compartmentalize different sections of the app and maintain a cleaner codebase.

Another challenge was optimizing the performance of data queries and visualizations. By leveraging Pandas for data manipulation and Matplotlib for plotting, I was able to efficiently handle 
large datasets and generate real-time visual feedback for users. Additionally, ensuring secure user authentication and session management required meticulous attention to detail, especially 
when handling sensitive information like passwords.

This project was a significant learning experience that honed my skills in web development, data analytics, and machine learning. It not only solidified my passion for data-driven applications
(Take a look at my other projects! I love making interactive dashboards.) but also equipped me with the skills and confidence to tackle more complex challenges in the realm of web development and 
data science. I'm eager to bring this blend of creativity and technical expertise to future endeavors, and I believe the Spotify Insights Hub is a testament to what I can achieve.
