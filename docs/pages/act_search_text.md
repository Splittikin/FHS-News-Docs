---
layout: modified
title: Searching for text
permalink: /act/searching_by_text
---
You can search for a specific string in articles by requesting the following URL, with `query` being the string you want to search for:
```
{{ site.api_url }}/search?query=the&quantity=5&position=0
```
The server will return a list of objects, each one representing a card in the search results.
```json
[
    {
      "itemType": "Article",
      "articleId": 2,
      "articleThumbnail": "image.png",
      "postedTime": "1670542200",
      "timeUntil": "0",
      "topperText": "Band",
      "topperIcon": "bruh.png",
      "author": "",
      "tags": [],
      "headline": "Sounds of the Season Concert",
      "subtitle": "Intermediate Jazz Ensemble, Advanced Jazz Ensemble, Concert Band, Symphonic Band Red, Symphonic Band Gold, Wind Symphony, Wind Ensemble",
      "text": "Enjoy the Sounds of the Season as the FHS Bands play selections to get you into the holiday spirit. The Intermediate Jazz Ensemble will play in the Auditorium Lobby beginning at 6:30 p.m. as we begin seating. The concert will begin in the Auditorium at 7 p.m. and the Concert, Symphonic Band Red, Symphonic Band Gold, Wind Symphony, Wind Ensemble and Advanced Jazz Ensemble bands will perform."
    }
]
```

If there are no search results, an empty list will be returned instead.

The position and quantity arguments tell the server how many results you want, and where in the list you are. If you do not define these arguments, they will default to 0 and 5 respectively.  

{: .note}
Currently searching by text only returns Articles. In the near future, it will return both Articles and Clubs. An additional argument will be added to only return Articles, or only return Clubs.