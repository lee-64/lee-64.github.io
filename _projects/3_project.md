---
layout: page
title: DJ Recommendation Engine
description: Connect your Spotify library to find which KXSC DJ is most statistically similar to your music taste
img: assets/img/kxsc_logo_project_thumbnail.jpg
importance: 1
category: personal
---

> Update:
> At the end of 2024, <a href="https://developer.spotify.com/blog/2024-11-27-changes-to-the-web-api">Spotify suddenly revoked access for many of their API endpoints</a> (much to the <a href="https://community.spotify.com/t5/Spotify-for-Developers/Changes-to-Web-API/td-p/6540414">frustration</a> of the developer community). Endpoints like `GET /audio-features/{id}` which were heavily leveraged in this application are now completely inaccessible.
> I have pivoted to a (similarly effective) solution utilizing music metadata from <a href="https://acousticbrainz.org">AcousticBrainz</a> and <a href="https://musicbrainz.org">MusicBrainz</a>. I have also significantly improved the UI/UX, website accessibility, hosting services (<a href="https://vercel.com/">Vercel</a> front-end and <a href="https://render.com">Render</a> back-end), and added more personalization features across the matching process.
> A demo of the newest iteration of KXSC DJ Match is viewable <a href="https://kxsc-dj-match.vercel.app/results">here</a>. Please check it out! Additionally, here is the <a href="https://github.com/lee-64/kxsc_dj_match">GitHub repository</a>.


I joined KXSC Radio, the student-run radio station of the University of Southern California, as a DJ intern in January 2024. I have always loved listening to music and talking
about music, so I was very pleased to meet so many likeminded peers. I also had big ideas for reworking and modernizing KXSC's services using my data science skills. The first project 
I have released since beginning at the station is the DJ Recommendation Engine.

The DJ Recommendation Engine is a web app that calculates a user's **most similar**, active KXSC DJ based off of key audio features from tracks in your Spotify library and the number
of tracks/artists from your playlists and Liked Songs you have in common. You can view a demo of the web app <a href="https://kxsc.pythonanywhere.com/demo">here</a>, at <a href="https://kxsc.pythonanywhere.com/demo">kxsc.pythonanywhere.com/demo</a>,
or the in the video below.

<br/>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/video_demo.mp4" class="img-fluid rounded z-depth-1" controls=true %}
    </div>
</div>
<div class="caption">
    A video demo of the DJ Recommendation Engine, as would be used by a user.
</div>


There are three primary goals of this app:
>1. Grow KXSC's reach by acquiring new listeners
>2. Increase listener retention
>3. Expedite the intern pairing process for KXSC's Intern Program

Once the app is approved by Spotify for a user extension request, the DJ Recommendation Engine will be advertised as a starting point for new listeners. This will draw in new users
who wish to see how their music taste stacks up against those in the radio station. Additionally, a system that matches by music taste is a novel practice--there are no other university
radio stations that have a feature like this.

Users of this app are also more likely to stick around and for longer. I suspect a demonstrable increase in listener retention, for this service gives users an immediate starting point
for which DJ, out of our ~70 DJs, they are most likely to enjoy. As a once first-time KXSC listener, I found the number and variety of DJs overwhelming and unnavigable. With over
70 hours of programming each week, it is unrealistic and unlikely a user finds the DJ that will get them to come back each week. I believe my program solves a first-time listener's
desire for a quick and easy starting point, increasing the chances that they come back for their matched-DJ's set each and every week.

<br/>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/kxsc_sem1_schedule.png" title="KXSC Schedule" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The weekly DJ schedule, consisting of approximately 70 DJs. It can be overwhelming for a first-time listener to know where to start. Side note: Check out my set at 12pm every Monday!
</div>

I recognize that a matching system can lead to recommendations that are *too similar* to the user. For example, a user might have most of a DJ's catalog already in their library, thus
rendering a match with them unhelpful/without anything new to present to the user. However, I argue that a 'too similar' match is not a downside in this case; DJs play new songs every
week, so fresh tunes are inevitable. Also, a DJ providing a new perspective on tracks you already know might not be a bad thing. There are still features in place to combat "too similar"
matches, though: the song recommendation returns a song from the DJ's catalog that is most similar to the user's average audio features AND is not in the user's library, and the Top 5 DJ
matches offers other options for the user to browse.

Finally, this app will be used to speed up the intern pairing process for KXSC's Intern Program. With over 120 intern applicants for only 15 to 20 spots each semester, I have worked with (and 
will continue to refine with) the Intern Coordinators to assist in this process using a modified version of the DJ Recommendation Engine specifically designed for the intern pairing process.
The algorithm behind the calculations remains the same, but it creates matches from an applicant's submitted playlist (rather than their entire library) instead. Then, a list of the five most
viable DJ-intern pairings (*purely based on music taste*) are given. The intern-matching process is and always will be a very human-led process--reading applications and determining qualifications
and fit is something I will not claim my project can do. Rather, my project speeds up specifically one metric of the matching process, that being music preference similarity. My project
assists in one aspect of the Intern Program's holistic review process.

This project builds on everything I learned while coding the [Spotify Insights Hub](https://lee-64.github.io/projects/1_project/) for my Applied Python course. I also learned a lot while 
developing this project. I've learned the ins-and-outs of Spotify's API while sifting through the verbose data structures that come with its API calls. Moreover, I worked with callback
functions and managing user authorization/permissions beyond simple login/logout functionality. The Spotify OAuth process, using client credentials and access tokens, exposed me to an
entirely new space of user<-->app<-->server frameworks that grant applications protected resources. Ultimately, implementing this feature allows the user to one-click sign in with Spotify, a 
functionality that many modern websites utilize when you click buttons like "Sign in with Google". I believe that Spotify's API is a fantastic API to begin learning with because of its 
extensive documentation and the daily relevance of Spotify's services.

<br/>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/spotify_api_call.png" title="A sample Spotify API call" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A sample Spotify audio features API call and response.
</div>

I received more exposure to statistical similarity techniques via this project too. When comparing the user's feature data arrays with each DJ's arrays, I opted for calculating angular distance
instead of cosine distance as my similarity metric--very similar to the approach applied in Google's <a href="https://arxiv.org/abs/1803.11175">Universal Sentence Encoder</a> paper. I found that with cosine similarity, 
many of the greatest similarity values were all bunched together towards the upper-end (0.90<), losing precision. This is because the multi-dimensional feature vectors corresponding to DJs were nearly parallel. 
I suspect this is due to how similar some DJs' music tastes are when averaged out. Small angle differences when using cosine similarity produce nearly identical similarity values, as seen by how the cosine similarity 
line flattens out for high similarity, small angle values on the right plot below. Angular similarity, on the other hand, is much better at distinguishing nearly parallel vectors. This is visible in the left plot below, 
where small changes in cosine values near x=1 yield a greater difference in similarity values. The transformation was calculated like so:

$$ 
\begin{align}
\text{angular similarity} = 1 - \frac{\arccos(\text{cosine similarity})}{\pi} 
\end{align}
$$

<br>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/sim_curves.jpg" title="Cosine vs. Angular Distance Curves" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Seen in the graph to the right, the cosine similarity curve flattens as 𝜑 approaches bounds 0° and 180°, losing precision. The discussion is viewable <a href="https://math.stackexchange.com/questions/2874940/cosine-similarity-vs-angular-distance">here</a>.
</div>

The similarity values are then weighted with the number of song and artist matches between the user and the DJ. Average track features convey the type of music a user might like, but a recommendation is less valuable 
if the user doesn't recognize anything from the DJ's catalog. I found that some overlap makes a user much more likely to want to tune in to that DJ's set because they can expect some of their favorite songs and artists 
to be played. Musical common ground with recognizable names is much more valuable to humans who don't see songs as an array of feature values.

A demo of the DJ Recommendation Engine is viewable at <a href="https://kxsc.pythonanywhere.com/demo">kxsc.pythonanywhere.com/demo</a>.
