---
layout: post
title: "Agile documentation, logging and metrics"
date: 2014-09-06 23:27:09 +0100
comments: true
categories:
---

Tight, hard deadlines on critical projects are not fun to deal with but fortunately an **Agile process** is a huge help to deliver timely while giving the whole team (and all upperloards!) visibility on progresses.

But still these are the occasions when you tend to leave behind some important aspects: documentation, accurate logging and metrics to have visibility on how the system performs.

So all that happiness for having delivered your project in time (or ahead of time!) has to immediately leave space to a not so exciting week (or more that a week) spent adding [accurate logging](http://fabiocognigni.github.io/blog/2014/06/07/logging/), metrics on performances, load handled, analytics and writing documentation for all the functionalities (worst case, textual documentation; best case, swagger in case of Restful APIs).

<!--more-->

A great way not to get there was for me applying a process that can be summarized with the below points:

1. pick a new story from the team wall;
2. TDD to implement the new feature;
3. add system metrics recording (execution times, hit counters, error counters, ...);
4. add "business" metrics/analytics (e.g. total amount for an order processed, credit card type used, orders with promotions, ...);
5. add the documentation (not the in-line code doc but final-user doc) on the new feature and update parts of the existing documentation if needed to keep it consistent;
6. open a PR;
7. have it reviewed (note that having added documentation, logging and metrics makes reviewer life much easier);
8. merge to trunk (or to the long term development environment);
9. move the story to "dev complete";
10. QA work will also include check the logs and metrics added;

The advantages of this approach are the followings:
* better quality and more accurate documentation just because you write it right after you implemented a specific piece and you then have all the details fresh in mind;
* same for adding meaningful logging and recording useful metrics;
* at any point in time everything done so far is well documented and this **facilitates on-boarding of new team members** joining in the middle of the project.

The begin can be tough but then they become natural steps of the entire process leading to greater quality and much better team-working.

In case documentation is not needed because the new feature is something to be used internally in your organization, good for you, but still an accurate description of your work (in addition to in-line code documentation, when needed) is always a good practice.
