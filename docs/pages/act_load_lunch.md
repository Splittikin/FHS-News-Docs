---
layout: modified
title: Loading the current lunch menu
permalink: /act/loading_the_lunch_menu
---
The current lunch menu can be loaded by requesting the following URL.
```
{{ site.api_url }}/lunch
```
The server will return the menu as a single JSON object. Here's an example:
```json
{
  "itemType": "LunchData",
  "time": 1679662272,
  "entree1": "Gregg",
  "entree2": "Snadwich",
  "vegetable1": "Bell Pepper (x230)",
  "vegetable2": "Olive (just 1 everyone has to share)",
  "grain1": "Wheat",
  "grain2": "COern",
  "fruit1": "Apple",
  "fruit2": "The Sun"
}
```

If the current lunch menu is not available (such as on a weekend or if the lunch menu has not been properly updated) an empty JSON object will be returned instead.

For details on how Lunch Menu Data works, check out the [Lunch Menu page]({{ site.baseurl }}/obj/lunch).