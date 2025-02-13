---
layout: page
title: DJ Recommendation Engine
description: Match with the KXSC DJ most statistically similar to your music taste
img: assets/img/kxsc_logo_project_thumbnail.jpg
importance: 1
category: personal
---

### [KXSC DJ Match](https://kxsc-dj-match.vercel.app) <svg style="position: relative; top: 2px;" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg>

> Update:
> At the end of 2024, <a href="https://developer.spotify.com/blog/2024-11-27-changes-to-the-web-api">Spotify revoked access for many of their API endpoints</a>. Endpoints like `GET /audio-features/{id}` which were heavily leveraged in this application are now inaccessible.
>
> <br>
>
> No worries at all! I have pivoted to a (similarly effective) solution that combines open-source music metadata from <a href="https://acousticbrainz.org">AcousticBrainz</a> and <a href="https://musicbrainz.org">MusicBrainz</a> with Spotify's API for track searches, popularity metrics, and artists' top songs. I have also significantly improved the UI/UX, website accessibility, hosting services (<a href="https://vercel.com/">Vercel</a> front-end and <a href="https://render.com">Render</a> back-end), and added more personalization features across the matching process.
> A demo of the newest iteration of KXSC DJ Match is viewable <a href="https://kxsc-dj-match.vercel.app">here</a>. Please check it out! Additionally, here is the <a href="https://github.com/lee-64/kxsc_dj_match">GitHub repository</a>.


I joined [KXSC Radio](https://kxsc.org/), the student-run radio station of the University of Southern California, as a DJ intern in January 2024. I have always loved listening to music and talking
about music, so I was very pleased to meet so many likeminded peers. I also had big ideas for reworking and modernizing KXSC's services using my data science skills. The first project 
I have released since beginning at the station is the DJ Recommendation Engine, also dubbed KXSC DJ Match, which I'm proud to showcase here.

The DJ Recommendation Engine is a web app that calculates a user's **most similar**, active KXSC DJ based off of key audio features from the user's favorite artists, desired music mood, and the frequency of artists you have in common. 
You can view a demo of the web app <a href="https://kxsc-dj-match.vercel.app">here</a> or in the video below.

<br/>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/djmatch_demo.mp4" class="img-fluid rounded z-depth-1" controls=true %}
    </div>
</div>
<div class="caption">
    A video demo of the DJ Recommendation Engine.
</div>

<br/>

***

## Tech Stack

### Back-end:
- **Python** drives the core recommendation engine and statistical calculations, handling complex feature extraction and similarity computations
  - Pandas, Sklearn, Numpy, Flask
- **Spotipy** & **Spotify's Web API** enabled secure OAuth authentication (v1.0) and extensive music metadata access
- **MongoDB** stores DJ profiles and matching data with flexible document schemas
- **AcousticBrainz** & **MusicBrainz APIs** (current version) provide rich, open-source music metadata for audio feature analysis

### Front-end:
- **React** powers the responsive interface with efficient component-based development
- **Next.js** delivers optimized performance through server and client-side rendering
- **Vercel** and **Render** provide reliable hosting for the frontend and backend respectively

***


## The Three Goals of this app
>1. Grow KXSC's reach by acquiring new listeners
>2. Increase listener retention
>3. Expedite the intern pairing process for KXSC's Intern Program

[KXSC DJ Match](https://kxsc-dj-match.vercel.app) is the perfect starting point for new listeners. As the first tab on [kxsc.org](https://kxsc.org/), this app draws in new users who wish to see how their music taste stacks up against those in the radio station. 
Additionally, a system that matches by music taste is a novel practice--there are no other university radio stations that have a feature like this.

Users of this app are also more likely to stick around and for longer. Across its first semester since deployment, I suspect a demonstrable increase in listener retention because this service gives users an immediate starting point
for which DJ, out of our ~70 DJs, they are most likely to enjoy. As a once first-time KXSC listener, I found the number and variety of DJs overwhelming and unnavigable. With over
70 hours of programming each week, it is unrealistic and unlikely a user finds the DJ that will get them to come back each week. I believe my program solves a first-time listener's
desire for a quick and easy starting point, increasing the chances that they come back for their matched DJ's set each and every week.

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
rendering a match with them unhelpful/without anything new to present to the user. However, I argue that a "too similar" match is not a downside in this case; DJs play new songs every
week, so fresh tunes are inevitable. Also, a DJ providing a new perspective on tracks you already know might not be a bad thing. There are still features in place to combat "too similar"
matches, though: for example, providing the top 5 DJ matches alongside the main match offers other options for the user to browse.

Finally, this app will be used to speed up the intern pairing process for KXSC's Intern Program. With over 120 intern applicants for only 15 to 20 spots each semester, I have worked with (and 
will continue to refine with) the Intern Coordinators to assist in this process using a modified version of the DJ Recommendation Engine specifically designed for the intern pairing process.
The algorithm behind the calculations remains the same, but it creates matches from an applicant's submitted playlist (rather than their entire library) instead. Then, a list of the five most
viable DJ-intern pairings (*purely based on music taste*) are given. The intern-matching process is and always will be a very human-led process--reading applications and determining qualifications
and fit is something I will not claim my project can do. Rather, my project speeds up specifically one metric of the matching process, that being music preference similarity. My project
assists in one aspect of the Intern Program's holistic review process.

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

***

#### v1.0 - Deprecated

The newest iteration of the DJ Recommendation Engine is a significant improvement from the original iteration (v1.0) in all regards. However, v1.0 did fully integrate with Spotify: users could connect their Spotify accounts to have their libraries and playlists automatically parsed and factored into the matching calculation.
While this feature is no longer available, a demo of v1.0 (for proof-of-functionality) can be seen here:

<br/>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="assets/video/v1_demo.mp4" class="img-fluid rounded z-depth-1" controls=true %}
    </div>
</div>
<div class="caption">
    A video demo of v1.0 of the DJ Recommendation Engine, highlighting the integration with Spotify.
</div>

v1.0 built on everything I learned while coding the [Spotify Insights Hub](https://lee-64.github.io/projects/1_project/) for my Applied Python course. I also learned the ins-and-outs of Spotify's API while sifting through the verbose data structures that come with its API calls. Moreover, I worked with callback
functions and managing user authorization/permissions beyond simple login/logout functionality. The Spotify OAuth process, using client credentials and access tokens, exposed me to an
entirely new space of user<-->app<-->server frameworks that grant applications access to protected resources. Ultimately, implementing this feature allowed the user to one-click sign in with Spotify, a 
functionality that many modern websites utilize when you click buttons like "Sign in with Google". This gave v1.0 a seamless and familiar UX, all the while emphasizing data privacy.  
And, as a note to the reader: Spotify's API is a fantastic API to begin learning with because of its extensive documentation and the daily relevance of Spotify's services. You can build something genuinely applicable to your (and a consumer's) daily life, and very easily too--get started [here](https://developer.spotify.com/documentation/web-api).