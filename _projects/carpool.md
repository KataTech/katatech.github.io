---
layout: page
title: Rice Carpool
description: 
img: assets/img/carpool/flyer-no-QR.png
importance: 1
category: work
---

*Ever needed a buddy to split Uber to the airport with?*

I know I certainly have. And so has most Rice students. 

[Rice Carpool](https://carpool.riceapps.org) is a mobile website for Rice students to schedule Uber Rides with one another. It is a long-standing project of [Rice Apps](https://riceapps.org), which is our student software development club that is focused on software solutions for the good of Rice and the Greater Houston community.

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/carpool-V2.png" title="Carpool V2" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/carpool-flyer.png" title="Carpool V3" class="img-fluid rounded z-depth-1" %}
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
        {% include figure.html path="assets/img/carpool/landing.png" title="Landing Page" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/ride-search.png" title="Ride Search" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/ride-creation.png" title="Ride Create" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Navigate from the landing page to the search page... oops! No ride has been made! Let us make one.
</div>

The idea here is pretty simple, the two core features are ride search and ride creation. In particular, ride creation functionality encompassed building the interface (form) for user to input their credentials, saving that information, and sending a GraphQL query to mutate our MongoDB database where the ride informations are collectively stored. For implementation details, check out the [source code](https://github.com/rice-apps/Carpool-V3/tree/master/client/src/Pages/CreateRide). Inspired heavily by the react-task-tracker [tutorial](https://www.youtube.com/watch?v=w7ejDZ8SWv8) hehe. 

The second feature that I have worked on was **User Onboarding**. We wanted to restrict assess to the site to Rice students and also be able to store new user information for future rides. The workflow basically consisted of: 

Verifying user as Rice student via Rice SSO Authentification. If the user is registered within our backend MongoDB database, then they are redirected to the Ride Creation. Otherwise, they are prompted with the onboarding page to store their information. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/sso-pop-up.png" title="SSO Pop-Up" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/authentication.png" title="Authentication" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/onboarding.png" title="Onboarding" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

A big challenge with implementing this feature was determining the flow of the verification process. In particular, interacting with Rice University's SSO verificaiton is slightly troublesome since it inherently has suboptimal error handling and the user could possibly be exited from this workflow in the midst of their onboarding process. My (potential naive) resolution was to leverage `localStorage` tokens to track the user's state within onboarding cycle. 

{% raw %}
```javascript
    const updateUserInfo = async (formData) => {
        await updateUser({ variables: formData });
        const nextPage = localStorage.getItem("nextPage");
        if (nextPage) {
        localStorage.removeItem("nextPage");
        localStorage.setItem("lastPage", "onboarding");
        window.open(nextPage, "_self");
        } else {
        history.push("/search");
        }
    };

    const cancelOnboarding = () => {
        localStorage.clear();
        if (previous && previous !== "onboarding") {
        window.open(previous, "_self");
        }
        // default behavior is to route to home page
        history.push("/search");
    };
```
{% endraw %}



#### **Results**

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/snapshot.png" title="Carpool Final" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Our product launched on March 1st, 2022 to the Rice University student body. We placed flyers all over campus and made mass announcements during lunch period at all of the student dining halls on campus. It was a scary moment to wait and see whether students were willing to use this project that we have worked on for over a year. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/carpool/stats.png" title="Statistics" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Luckily, the app was a massive success! Within 30 minutes of our mass announcments... we had over 64 visitors. And by the end-of-semester Rice Apps project demo day, Rice Carpool had been visited by 2.3K users (unsure if this is distinct, but still pretty good!) Our MongoDB database showed that there were over 450 registered users and around 280 distinct created rides within the 3-month period between spring break and the start of summer. For context, there are only a total of around 4000 students on Rice campus and around 40% are Texas residents.

Today, Rice Carpool is still in use by various venue and has been expanded to include locations beyond airports. There was an [article](https://www.ricethresher.org/article/2022/03/rice-apps-relaunches-carpool-mobile-site) written about it by the Rice student newspaper and it is a go-to scheduling app for Rice's successful [ice skating club](https://news.rice.edu/news/2021/owls-ice-wildly-popular-skating-event-draws-hundreds-students-holiday-blowout) led by one of our developers, Anya Gu.

#### **Acknowledgements**

The success of this project would not have been possible without: 

* the mentorship of our product manager and tech leads 
    * [Shreya Nidadavolu](https://www.linkedin.com/in/shreya-nidadavolu/)
    * [William Yao](https://www.linkedin.com/in/william-yao-0a80b6153/)
    * [Henry Qin](https://www.linkedin.com/in/henryqin5/)
* my fellow developers 
    * [AJ Kim](https://www.linkedin.com/in/audrey-aj-kim/)
    * [Alexis Nicolas](https://www.linkedin.com/in/alexis-nic01as/)
    * [Anya Gu](https://anyagu.com/)
    * [Mitchell Osborn](https://www.linkedin.com/in/mitchell-osborn/)
    * [Shreyas Minocha](https://shreyasminocha.me/)
* our awesome designers 
    * [Katherine Chui](https://www.kchuiart.com/)
    * [Jessica Huang](https://read.cv/jshuang)
* previous Carpool teams and the Rice Apps community!

For more on the codebase, feel free to checkout our repo. 

{% if site.data.repositories.github_repos %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.carpool_repo %}
    {% include repository/repo.html repository=repo %}
  {% endfor %}
</div>
{% endif %}
