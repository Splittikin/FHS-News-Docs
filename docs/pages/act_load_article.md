---
layout: default
title: Loading a specific article
permalink: /act/loading_an_article
---
- [Back to index]({{ site.baseurl }}/)

A specific article can be loaded by requesting the following URL. The ID parameter should be set to the ID of the article you want.
```
{{ site.api_url }}/article?id=<id of article>
```
The server will return the article as a single JSON object. Here's an example:
```json
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
}
```
For details on how Article objects work, check out the [Articles page]({{ site.baseurl }}/obj/article).

---
- [Back to index]({{ site.baseurl }}/)