---
layout: modified
title: FHS-News API Docs
---
Welcome to the documentation for the FHS-News API! Here you can find information about how to interact with the FHS-News server and how to have your app make sense of what it sends back. Please let me know if you have any questions!

{: .note}
The FHS-News API is still super WIP so **things may change at any time.** If your app's interaction with the API suddenly starts breaking, check here first to see if things are different!

### Objects
  - [Articles]({{ site.baseurl }}/obj/article)
  - [Clubs]({{ site.baseurl }}/obj/club)
  - [Alerts]({{ site.baseurl }}/obj/alert)
  - [Weather Data]({{ site.baseurl }}/obj/weather_data)
  - [Lunch Menu Data]({{ site.baseurl }}/obj/lunch)

### Actions
  - [Loading the home feed]({{ site.baseurl }}/act/loading_the_home_feed)
  - [Loading the clubs feed]({{ site.baseurl }}/act/loading_the_clubs_feed)
  - [Loading a specific article]({{ site.baseurl }}/act/loading_an_article)
  - [Loading a specific club]({{ site.baseurl }}/act/loading_a_club)
  - [Loading the current weather data]({{ site.baseurl }}/act/loading_the_weather_data)
  - [Loading the current lunch menu]({{ site.baseurl }}/act/loading_the_lunch_menu)
  - Searching for articles or clubs (API Implementation WIP)
  - Searching for articles by date (Documentation WIP)
  - Configuring push notifications (API Implementation WIP)