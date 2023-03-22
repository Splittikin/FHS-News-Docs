---
layout: modified
title: Loading the current weather data
permalink: /act/loading_the_weather_data
---
The most recent weather data can be loaded by requesting the following URL:
```
{{ site.api_url }}/weather
```
The server will return the weather as a single JSON object. Here's an example:
```json
{
  "itemType": "WeatherData",
  "time": "1675864167000",
  "current_temp": 29,
  "weather_icon_id": "c03d",
  "weather_description": "Broken clouds"
}
```

If the current weather data is not available (which may occur if the server encounters an issue fetching weather data from Weatherbit and the current weather data is too old), an empty JSON object will be returned instead.

The future or past weather cannot be requested. Only the data from the most recent weather update is available.

For details on how Weather Data works, check out the [Weather Data page]({{ site.baseurl }}/obj/weather_data).