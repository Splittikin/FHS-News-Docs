---
layout: default
title: WeatherData object
permalink: /obj/weather_data
---
- [Back to index]({{ site.baseurl }}/)

This object displays the weather from Weatherbit. Since the Weatherbit API limits us on how many calls we can make to it, it is fetched by the server every 30 minutes instead of taking up one of our calls every time the app is opened by someone. 

(TODO Screenshot of a Weather card)

The Weather Data object is structured like the following:
```json
{
  "itemType": "WeatherData",
  "time": "1675864167",
  "current_temp": 29,
  "weather_icon_id": "c03d",
  "weather_description": "Broken clouds"
}
```

| Field               | Type    | Example       | Requirement | Description                                                                                                                   |
|---------------------|---------|---------------|-------------|-------------------------------------------------------------------------------------------------------------------------------|
| itemType            | String  | WeatherData   | Required    | The type of the object.                                                                                                       |
| time                | String  | 1675864167    | Required    | [UNIX timestamp][timestamp-converter] of when the weather was last updated.                                                   |
| current_temp        | Integer | 29            | Required    | Temperature when the weather was last updated, in degrees Fahrenheit. Conversion to Celsius must be done locally in your app. |
| weather_icon_id     | String  | c03d          | Required    | ID of the Weatherbit icon for the current weather. You can see the whole list [here][weatherbit-icon-list].                   |
| weather_description | String  | Broken Clouds | Required    | A short description of the current weather, as reported by Weatherbit.                                                        |

[timestamp-converter]: https://www.unixtimestamp.com/
[weatherbit-icon-list]: https://www.weatherbit.io/api/codes

Future weather forecasts are not available since that would use another API call. Only one weather card should appear in the home feed at a time. If the server does not report the weather, the card should not appear in the home feed at all.

Do note that the server will stop reporting the weather if an issue arises and the current weather data is too old. Make sure that your app can still function without the weather card being sent.

---
- [Back to index]({{ site.baseurl }}/)