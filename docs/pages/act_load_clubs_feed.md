---
layout: modified
title: Loading the clubs feed
permalink: /act/loading_the_clubs_feed
---
The clubs feed can be loaded by requesting the following URL:
```
{{ site.api_url }}/feedClubs?position=0&quantity=5
```
Like when requesting the [home feed]({{ site.baseurl }}/act/loading_the_home_feed), the server will return a list of JSON objects, each one representing a Club in the clubs feed. Here's an example:
```json
[
  {
    "clubThumbnail": "{{ site.cdn_url }}/clubs/1/ahhhhhhhhhhhhhhh.jpg",
    "tags": [],
    "clubName": "3D PRINTING CLUB",
    "clubSubtitle": "Sponsor(s): Renee Isom",
    "clubText": "We will meet to plan and execute 3D printing projects using the equipment in the media center. We will also fundraise to afford more printing materials. Open to everyone, regardless of experience!",
    "clubId": 1,
    "itemType": "Club"
  },
  {
    "clubThumbnail": "{{ site.cdn_url }}/clubs/2/ahhhhhhhhhhhhhhh.jpg",
    "tags": [],
    "clubName": "2000s FUN",
    "clubSubtitle": "Sponsor(s): Erin Knapp",
    "clubText": "This is a throwback to childhood - with little-to-no technology. We're going to play board games, do crafts, make bracelets, work on puzzles, and use sidewalk chalk to create a stress-free environment for students to gather and socialize for fun! The goal is social interaction and creating a sense of belonging at FHS",
    "clubId": 2,
    "itemType": "Club"
  },
  {
    "clubThumbnail": "{{ site.cdn_url }}/clubs/3/ahhhhhhhhhhhhhhh.jpg",
    "tags": [],
    "clubName": "ACADEMIC AMBUSH TEAM",
    "clubSubtitle": "Sponsor(s): Alex Smith, Katie Hagerty",
    "clubText": "The Academic Ambush is comprised of three teams: Quiz Bowl, Spell Bowl, and Academic Super Bowl. Quiz Bowl is a team-based, Jeopardy-like trivia competition. Spell Bowl is a team-based spelling bee. Academic Super Bowl is a multidisciplinary team competition unified by them. See Mr. Smith or Ms. Hagerty for information on all three! ",
    "clubId": 3,
    "itemType": "Club"
  },
  {
    "clubThumbnail": "{{ site.cdn_url }}/clubs/4/ahhhhhhhhhhhhhhh.jpg",
    "tags": [],
    "clubName": "ANIMATION CLUB",
    "clubSubtitle": "Sponsor(s): Glenn Seland",
    "clubText": " The Animation Club will allow students to explore different animation mediums and learn about the different aspects of animation production. We will initially start with learning how to animate, but in the end, we hope to create a 3-5 minute animated short film to submit to the All-American High School Film Festival in early March 2023.",
    "clubId": 4,
    "itemType": "Club"
  },
  {
    "clubThumbnail": "{{ site.cdn_url }}/clubs/5/ahhhhhhhhhhhhhhh.jpg",
    "tags": [],
    "clubName": "ARAB ASSOCIATION",
    "clubSubtitle": "Sponsor(s): Chris Edwards",
    "clubText": "This club is open to anyone with an interest in Arab culture or connecting with Arab people. Our hope is to create a sense of belonging for all students and create an opportunity for new friendships.",
    "clubId": 5,
    "itemType": "Club"
  }
]
```
The server may return any number of clubs in any order. The order of clubs will periodically be randomized, so that one club doesn't get prioritized over another.

The two parameters at the end, `position`, and `quantity`, tell the server what place you want to load the clubs from and how many of them you want to load.

{: .note}
If you do not specify `position` and `quantity` in your request, they will default to 0 and 5 respectively.