---
layout: page
title: Rice Carpool
description: 
img: assets/img/carpool/landing.png
importance: 1
category: work
---

*Ever needed a buddy to split Uber to the airport with?*

I know I certainly have. And so has most Rice students. 

[Rice Carpool](https://carpool.riceapps.org) is a mobile website for Rice students to schedule Uber Rides with one another. It is a long-standing project of [Rice Apps](https://riceapps.org), which is our student software development club that is focused on software solutions for the good of Rice and the Greater Houston community.

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/carpool-V2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/carpool-flyer.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Evolution from Carpool V2 to Carpool V3
</div>

I was a core developer for the 3rd edition of Rice Carpool from May 2021 to May 2022.

Over my time here, I build the front-end for some of our key app functionalities, supported other developers with their features, fixed a bunch of bugs, and ran around half of Rice's residential colleges to promote our project on 03/01/2022. It was a great time. 

#### **Features**

The first feature I worked on was **Ride Creation**, as part of Rice App's [Open Source Summer Accelerator](https://medium.com/@thewillmundy/expanding-opportunities-at-riceapps-b5873fd12a6) and with zero web development experience. I remember learning ReactJS, nodeJS, GraphQL for the first time and struggling with CSS for most of it. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/landing2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/ride-search.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/ride-creation.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Navigate from the landing page to the search page... oops! No ride has been made! Let us make one.
</div>

The idea here is pretty simple, the two core features are ride search and ride creation. In particular, ride creation functionality encompassed building the interface (form) for user to input their credentials, saving that information, and sending a GraphQL query to mutate our MongoDB database where the ride informations are collectively stored. 

The following remain one of my proudest code snippets at the time: 

{% raw %}
```javascript
    const addRide = (ride) => {
        createRide({
            variables: ride
        })
        .then((obj) => {
            addToast("Congratulations! Your ride has been successfully created.", 
                    { appearance: 'success'});
            const rideID = obj.data.rideCreateOne.record._id;
             window.open('/ridesummary/' + rideID, '_self');
        })
        .catch((error) => {
            addToast("Sorry, an error occurred processing your new ride. Please try again later.", 
                    { appearance: 'error' });
        });
    }
```
{% endraw %}

For context, check out the [source code](https://github.com/rice-apps/Carpool-V3/tree/master/client/src/Pages/CreateRide). Inspired heavily by the react-task-tracker [tutorial](https://www.youtube.com/watch?v=w7ejDZ8SWv8) hehe. 

#### **Results**

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/snapshot.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/stats.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
