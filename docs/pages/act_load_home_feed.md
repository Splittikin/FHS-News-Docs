---
layout: modified
title: Loading the home feed
permalink: /act/loading_the_home_feed
---
The home feed can be loaded by requesting the following URL:
```
{{ site.api_url }}/home?position=0&quantity=5
```

{: .note}
The current list of articles currently consists of placeholders, many of which are copies of the same article, so you may see the same article several times for the time being. 

The server will return a list of JSON objects, each one representing a card in the home feed. Each object begins with the attribute `itemType`, which indicates what type of card that this object should be. Here's an example:
```json
[
  {
    "itemType": "WeatherData",
    "time": "1675864167000",
    "current_temp": 29,
    "weather_icon_id": "c03d",
    "weather_description": "Broken clouds"
  },
  {
    "itemType": "Alert",
    "text": "We're having a Bruh moment!",
    "background_color": "#FFFF00",
    "foreground_color": "#000000",
    "links": {
      "Clever": "https://clever.com/",
      "Enriching Students": "https://student.enrichingstudents.com/dashboard"
    }
  },
  {
    "itemType": "Alert",
    "text": "im thinkin bout those beans",
    "background_color": "#00FFFF",
    "foreground_color": "#000000"
  },
  {
    "itemType": "Article",
    "articleId": 1,
    "articleThumbnail": "{{ site.cdn_url }}/articles/1/image.png",
    "postedTime": "1671469200000",
    "timeUntil": "0",
    "topperText": "Fundraiser",
    "topperIcon": "{{ site.cdn_url }}/articles/1/bruh.png",
    "author": "",
    "tags": [],
    "headline": "Holiday Gift Wrapping",
    "subtitle": "For the Leukemia and Lymphoma Society",
    "text": "On December 19th at door 19, remember to drop off 5-10 gifts to be wrapped for a donation via cash, check, or CashApp. You may bring your own wrapping paper if it is specific to your kid. All proceeds go to the Leukemia and Lymphoma Society"
  },
  {
    "itemType": "Article",
    "articleId": 2,
    "articleThumbnail": "{{ site.cdn_url }}/articles/2/image.png",
    "postedTime": "1670542200000",
    "timeUntil": "0",
    "topperText": "Band",
    "topperIcon": "{{ site.cdn_url }}/articles/2/bruh.png",
    "author": "",
    "tags": [],
    "headline": "Sounds of the Season Concert",
    "subtitle": "Intermediate Jazz Ensemble, Advanced Jazz Ensemble, Concert Band, Symphonic Band Red, Symphonic Band Gold, Wind Symphony, Wind Ensemble",
    "text": "Enjoy the Sounds of the Season as the FHS Bands play selections to get you into the holiday spirit. The Intermediate Jazz Ensemble will play in the Auditorium Lobby beginning at 6:30 p.m. as we begin seating. The concert will begin in the Auditorium at 7 p.m. and the Concert, Symphonic Band Red, Symphonic Band Gold, Wind Symphony, Wind Ensemble and Advanced Jazz Ensemble bands will perform."
  }
]
```
The server may return any number of objects. They should be displayed in order.

The two parameters at the end, `position`, and `quantity`, tell the server what place you want to load the articles from and how many of them you want to load, including the extra cards (Weather, clock, alerts, everything not an article.) 

{: .note}
If you do not specify `position` and `quantity` in your request, they will default to 0 and 5 respectively.