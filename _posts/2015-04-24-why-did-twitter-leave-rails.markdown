---
layout: post
title:  "Why Did Twitter Move From Rails"
date:   2014-04-23 14:34:25
categories: misc
tags: misc
image: http://cdn1.sbnation.com/assets/3554691/twitter4.jpg
---
It is hard to discuss Rails and its scalability without someone bringing up Twitter and their decision to part away from Rails. Their move certainly created a lot of misunderstandings about Rails and I will clear up some reasons for their big decision.

When the two founders of Twitter was starting out they built the first version of the site in the matter of few days. Rails allows you to develop quickly and Scala at the time was still an immature technology  to be used as an option. 

As Twitter matured over the years and becoming more of a real time messaging application on a large scale, they started decoupling and encapsulating their code more. Scala was used for the back end and Javascript frameworks are taking over the front end slowly. The move may have been more of a language issue than a framework. Live data in interpreted languages like Ruby takes more CPU and memory. 

All in all, issues with Twitter does not have much to do with scalability of Rails. Finding a tool that is most appropriate for specific job, was what Twitter had to do as they got bigger quickly. Scaleability should not have to do with languages or frameworks but someone who is designing the software. Giant companies like Airbnb, Groupon, and Shopify have successfully scaled Rails showing that it is not an impossible task. 