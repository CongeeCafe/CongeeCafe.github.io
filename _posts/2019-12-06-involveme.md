---
layout: post
title: Building InvolveMe
---

This project, including this writeup, was a combined effort between Celine Lee, Bruce Zhang, Stanley Ren, and myself.

> Whether you’re moving to a new city or trying to change up your daily routine, volunteering is a great way to meet new people, build new skills, and engage with the community around you. However, trying to find the right place to volunteer is tough, and all the scattered information across the internet and bulletin boards can be overwhelming. To solve this, InvolveMe is an app that effortlessly connects you to organizations and other fellow volunteers, making volunteering more fun and social.''
<small>&mdash;from the InvolveMe promo video</small>

As described in the video, InvolveMe fills the communication gap between aspiring volunteers (possibly like yourself!), other fellow volunteers, and organizations. We felt that younger demographics, such as students in high school or post-secondary, enjoy being social and engaging in activities that broaden their experiences and skills. Volunteering is a prime example of these kinds of activities, but the difficulty in finding a volunteering role of interest is a big barrier to overcome. Having a platform that consolidates these opportunities while providing useful discovery features will reduce the friction to start volunteering, ultimately encouraging more youth to get involved. Our end goal is to make volunteering more social, connecting like minded people to make a bigger impact for the greater good.

#### Anticipated Users

We identified three main user groups for our app, and created personas to associate each of them.

##### Persona A: University Student

Being university students ourselves helps us understand the needs of others in this category; having moved to Waterloo for university from somewhere else, we all sought a sense of community, and felt that volunteering and getting involved was one of the best ways to do so.

##### Persona B: High School Student

We chose to include this persona since in Ontario, high school students are required to fulfill 40 hours of volunteer work in order to earn their secondary school diploma. This app will be very helpful to them for finding a volunteering position in order to get certified or some other kind of acknowledgement.

##### Persona C: Outreach Coordinator for a local food bank

Organizations seeking volunteers often have employees working several duties; in this case, the outreach coordinator is responsible for not only recruiting volunteers, but may also be occupied with finding sponsors, marketing the food bank to donors, collaborating with supermarkets and schools, and so on. This persona embodies the non-technical user; that is, whereas an HR professional may be familiar with job board sites such as Indeed, a persona like this one probably would not.

#### User Interviews

To get a good sample of data, we aimed to interview an equal number of potential volunteers and organization members who are familiar with the recruiting process. With this in mind, we ended up interviewing 4 people:

1. 4th year Health Studies student
2. 4th year Computer Science student
3. President and Personnel Manager at Waterloo Chamber Orchestra
4. Director for Canadian Glass and Clay Gallery

For the students, we decided to ask a series of questions focused on the following three topics:

1. Their interest with getting involved with the community
2. Prior experiences with searching for volunteering roles
3. Relation of volunteering work to their everyday life

For the coordinators, our questions focused on:

1. Their role in the organization
2. Value of volunteers
3. Experience with their process of recruiting volunteers

Each one of these interviews provided very insightful findings. From interviews with students, there was a general consensus that volunteering grows both professional and soft skills. In addition, if the volunteering role is relevant enough, it can also serve as a great practical supplement to their area of study. For example, the Health Studies student said that her volunteering experience gave her a better view into the world of social health, an area she is very interested in. Another common theme was that current methods of finding volunteer jobs make the task difficult. Each student had a different source of information they sought from, but all said that the variety of jobs were lacking.

For volunteer coordinators, social media can be a good way to reach potential volunteers, as it is cheap and can reach a wide audience. However, it is difficult to target any particular audience for more specialized roles. Coordinators also said that their volunteers contribute to the organization’s image, so it is important to find people with matching values. In addition, social media is only a tool for outreach and not a comprehensive solution for recruiting volunteers, so another solution is needed to facilitate registration, making the process fairly complex.

##### Affinity Diagrams, Storyboarding, and Crazy 8s

{% include image.html url="/assets/blog/img/affinity_diagram.jpg" caption="Affinity diagram from user interviews" %}

We used affinity diagrams to find out key issues that summarize multiple users’ needs. In the end, we found problems that exist in the process of people finding places to get involved in the community and organizations searching for volunteers.

Later on, the process of storyboarding and helped us brainstorm the different scenarios where people use our app. Some of our storyboards can be seen below.

{% include image.html url="/assets/blog/img/storyboard1.jpg" caption="Storyboard 1" %}

{% include image.html url="/assets/blog/img/storyboard2.jpg" caption="Storyboard 2" %}

{% include image.html url="/assets/blog/img/storyboard3.jpg" caption="Storyboard 3" %}

Even though we imagined each of these scenarios, we still found things we can do to improve the volunteer process and let people be more involved.

1. Provide features to organizations that would let them recruit volunteers efficiently
2. Help volunteers find jobs they are interested in, possibly to fulfill their volunteer hours.
3. Provide more social features to connect users

#### Initial Design Ideas

Based on the information we gathered from the user interviews we were able to gain a general understanding of what the users were looking for and their expectations for an engaging app. We then developed some initial sketches and wireframes of the application.  

{% include image.html url="/assets/blog/img/organization_profile_flow.jpg" caption="User flow &mdash; Organization profile" %}

The organization profile page shows the organization’s name and logo. There is a follow button that the user can click to subscribe to updates (such as new events). The user can also scroll down to see a schedule of upcoming events that the organization is hosting, and other status updates. At the bottom, there is a map that shows the organization's address and contact information.

{% include image.html url="/assets/blog/img/user_profile_flow.png" caption="User flow &mdash; User profile" %}

The user profile page similar to that of LinkedIn's, where volunteer recruiters are able to see a user's skills, bio, past experiences, accolades, and more. However, since volunteering is meant to be fun, we also added a button that would take you to your badges and accomplishments where you can keep track of how much you’ve contributed to your community.

{% include image.html url="/assets/blog/img/role_search_flow.jpg" caption="User flow &mdash; Role search" %}

The volunteer role search page differs from the event search page, since here, users would be able to find a recurring volunteering role (rather than a one-off event). Designed for scannability, the list in the main view lists the role/job title, organization, level of commitment and distance, so that users are able to quickly see what kinds of volunteering roles are available. If a user is interested in a role, they could tap on the role to see more details about the position.

{% include image.html url="/assets/blog/img/social_feed_flow.png" caption="User flow &mdash; Social feed" %}

The social feed mirrors the homepage feed of websites like Linkedin or Facebook. It gives an overview of everything that is going on, from both organizations, friends, and people you follow. It keeps users engaged and keeps friends connected to each other by showing updates on what they’re up to. For example, it shows when people register to attend an event in order to encourage their friends to join in as well.