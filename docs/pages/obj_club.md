---
layout: modified
title: Club objects
permalink: /obj/club
---
Clubs objects are information cards that showcase a club, as well as talk about what happens in it. They are virtually identical to Article objects, only without a few unneeded attributes. 

(TODO Screenshot of a Club card)

Club objects are structured like the following:
```json
{
  "itemType": "Club",
  "clubId": 2,
  "clubThumbnail": "{{ site.cdn_url }}/clubs/2/ahhhhhhhhhhhhhhh.jpg",
  "tags": ["2000s", "throwback", "crafts"],
  "clubName": "2000s FUN",
  "clubSubtitle": "Sponsor(s): Erin Knapp",
  "clubText": "This is a throwback to childhood - with little-to-no technology. We're going to play board games, do crafts, make bracelets, work on puzzles, and use sidewalk chalk to create a stress-free environment for students to gather and socialize for fun! The goal is social interaction and creating a sense of belonging at FHS"
}
```

| Field         | Type            | Example                                                                   | Requirement                                                                   | Description                                                                     |
|---------------|-----------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| itemType      | String          | Club                                                                      | Required                                                                      | The type of the object.                                                         |
| clubId        | Integer         | 2                                                                         | Required                                                                      | The ID of the club. No two clubs share the same ID.                             |
| clubThumbnail | String          | {{ site.cdn_url }}/clubs/2/ahhhhhhhhhhhhhhh.jpg                           | Required - If not defined by the author, the server will insert a placeholder | A picture for the club. May be a logo, or a picture of people in the club, etc. |
| tags          | List of strings | ["2000s", "throwback", "crafts"]                                          | Optional - May be empty ([]) or not defined at all                            | List of tags for the club, used when searching or filtering to specific tags.   |
| clubName      | String          | 2000s FUN                                                                 | Required                                                                      | Name of the club.                                                               |
| clubSubtitle  | String          | Sponsor(s): Erin Knapp                                                    | Optional - May be empty ("") or not defined at all                            | One-line subtitle for the club. Ellipses after one line.                        |
| clubText      | String          | This is a throwback to childhood - with little-to-no technology. We're... | Required                                                                      | Text contents of the club card.                                                 |