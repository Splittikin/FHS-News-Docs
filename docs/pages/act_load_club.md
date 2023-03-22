---
layout: modified
title: Loading a specific club
permalink: /act/loading_a_club
---
A specific club can be loaded by requesting the following URL. The ID parameter should be set to the ID of the club you want.
```
{{ site.api_url }}/club?id=<id of club>
```
The server will return the club as a single JSON object. Here's an example:
```json
{
  "itemType": "Club"
  "clubId": 1,
  "clubThumbnail": "{{ site.cdn_url }}/clubs/1/ahhhhhhhhhhhhhhh.jpg",
  "tags": [],
  "clubName": "3D PRINTING CLUB",
  "clubSubtitle": "Sponsor(s): Renee Isom",
  "clubText": "We will meet to plan and execute 3D printing projects using the equipment in the media center. We will also fundraise to afford more printing materials. Open to everyone, regardless of experience!",
}
```
If the club you requested for does not exist or is no longer available, you will recieve a 404 error instead.

For details on how Club objects work, check out the [Clubs page]({{ site.baseurl }}/obj/club).