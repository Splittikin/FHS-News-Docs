---
layout: modified
title: Lunch Data objects
permalink: /obj/lunch
---
The Lunch Data object displays to students what food is available to buy for lunch today. Like the [Weather]({{ site.baseurl }}/obj/weather_data) card, it appears once in the home feed. 

(TODO Screenshot of the Lunch card)

The Lunch Data object is structured like the following:
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

| Field      | Type   | Example                              | Requirement                                 | Description                             |
|------------|--------|--------------------------------------|---------------------------------------------|-----------------------------------------|
| itemType   | String | LunchData                            | Required                                    | The type of the object.                 |
| time       | Int    | 1679662272                           | Required                                    | When the current lunch menu was posted. |
| entree1    | String | Gregg                                | Required                                    | Main entree.                            |
| entree2    | String | Snadwich                             | Optional - May be empty ("") or not defined | Alternate entree.                       |
| vegetable1 | String | Bell Pepper (x230)                   | Required                                    | Main vegetable.                         |
| vegetable2 | String | Olive (just 1 everyone has to share) | Optional - May be empty ("") or not defined | Alternate vegetable.                    |
| grain1     | String | Wheat                                | Required                                    | Main grain!!!!                          |
| grain2     | String | COern                                | Optional - May be empty ("") or not defined | Alternate grain...                      |
| fruit1     | String | Apple                                | Required                                    | Main fruit.                             |
| fruit2     | String | The Sun                              | Optional - May be empty ("") or not defined | Alternate fruit.                        |
