---
layout: default
title: Article objects
permalink: /obj/article
---
- [Back to index]({{ site.baseurl }}/)

Article objects are cards in the home feed that include a subject, title, image, subtitle, and content.

(TODO Screenshot of an Article card)

Article objects are structured like the following:
```json
{
  "itemType": "Article",
  "articleId": 2,
  "articleThumbnail": "http://76.139.70.221:3000/files/attachments/articles/2/image.png",
  "postedTime": "1670542200",
  "timeUntil": "0",
  "topperText": "Band",
  "topperIcon": "http://76.139.70.221:3000/files/attachments/articles/2/bruh.png",
  "author": "Jeff H. Jumblo",
  "tags": ["band", "concert", "jazz"],
  "headline": "Sounds of the Season Concert",
  "subtitle": "Watch the concert bands perform!",
  "text": "Enjoy the Sounds of the Season as the FHS Bands play selections to get you into the holiday spirit. The Intermediate Jazz Ensemble will play in the Auditorium Lobby beginning at 6:30 p.m. as we begin seating. The concert will begin in the Auditorium at 7 p.m. and the Concert, Symphonic Band Red, Symphonic Band Gold, Wind Symphony, Wind Ensemble and Advanced Jazz Ensemble bands will perform."
}
```

| Field            | Type            | Example                                                            | Requirement                                                                   | Description                                                                                                                                                                                                                                                                                                                                                                              |
|------------------|-----------------|--------------------------------------------------------------------|-------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| itemType         | String          | Article                                                            | Required                                                                      | The type of the object.                                                                                                                                                                                                                                                                                                                                                                  |
| articleId        | Integer         | 2                                                                  | Required                                                                      | The ID of the article. No two articles share the same ID.                                                                                                                                                                                                                                                                                                                                |
| articleThumbnail | String          | http://76.139.70.221:3000/files/attachments/articles/2/image.png   | Required - If not defined by the author, the server will insert a placeholder | URL to the thumbnail of the Article.                                                                                                                                                                                                                                                                                                                                                     |
| postedTime       | String          | 1670542200                                                         | Required                                                                      | [UNIX timestamp][timestamp-converter] of when the Article was posted. Required, as this decides where in the feed the Article appears.                                                                                                                                                                                                                                                   |
| timeUntil        | String          | 0                                                                  | Optional - May be empty (0) or not defined at all                             | [UNIX timestamp][timestamp-converter] in the future, replacing postedTime if defined. Shown as a countdown until the given timestamp ("in 6 days") instead of counting up from when the Article was posted ("6 days ago"). Useful for announcements of events. postedTime is still required even if this is defined, as postedTime still controls where in the feed the Article appears. |
| topperText       | String          | Band                                                               | Optional - May be empty ("") or not defined at all                            | Subject displayed above the Article. Used to indicate what subject the Article involves, such as "Band", or "Show choir", or "Freshmen football", etc.                                                                                                                                                                                                                                   |
| topperIcon       | String          | http://76.139.70.221:3000/files/attachments/articles/2/bruh.png    | Optional - May be empty ("") or not defined at all                            | URL to a small logo displayed beside the topper text. Should only be defined if topperText is defined, otherwise it can be ignored.                                                                                                                                                                                                                                                      |
| author           | String          | Jeff H. Jumblo                                                     | Optional - May be empty ("") or not defined at all                            | The name of the author of the Article.                                                                                                                                                                                                                                                                                                                                                   |
| tags             | List of strings | ["band", "concert", "jazz"]                                        | Optional - May be empty ([]) or not defined at all                            | List of tags for the Article, used when searching or filtering to specific tags.                                                                                                                                                                                                                                                                                                         |
| headline         | String          | Sounds of the Season Concert                                       | Required                                                                      | The title of the article, displayed in large text. Ellipses after one line.                                                                                                                                                                                                                                                                                                              |
| subtitle         | String          | Watch the concert bands perform!                                   | Optional - May be empty ("") or not defined at all                            | One-line subtitle for the article. Ellipses after one line.                                                                                                                                                                                                                                                                                                                              |
| text             | String          | Enjoy the Sounds of the Season as the FHS Bands play selections... | Required                                                                      | The contents of the article.                                                                                                                                                                                                                                                                                                                                                             |

[timestamp-converter]: https://www.unixtimestamp.com/

---
- [Back to index]({{ site.baseurl }}/)