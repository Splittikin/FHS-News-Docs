---
layout: default
title: Alert object
permalink: /obj/alert
---
Alerts are small text windows, shown in a specific color with optionally some buttons. Their main purpose is to indicate to students whether today is a RED or a SILVER day, however, the actual text and button contents are provided by the object itself. This makes it possible for the card to also display other types of days when needed, such as a SEVEN PERIOD day or an EMPLOYABILITY day, or even display that today is  a FINALS day during things like finals week or during other events that affect the schedule.

(TODO Screenshot of an Alert card)

In addition to indicating to students what type of schedule is being used today, they can also be used to display a short message at the top of the feed to all students (hence the name 'Alert'.)

Alert cards are structured like the following:
```json
{
  "itemType": "Alert",
  "text": "We're having a Bruh moment!",
  "background_color": "#FFFF00",
  "foreground_color": "#000000",
  "night_background_color": "#727200",
  "night_foreground_color": "#FFFFFF",
  "links": {
    "Clever": "https://clever.com/",
    "Enriching Students": "https://student.enrichingstudents.com/dashboard"
  }
}
```

| Field                  | Type        | Example                     | Requirement                                                                                                                                                              | Description                                                  |
|------------------------|-------------|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
| itemType               | String      | Alert                       | Required                                                                                                                                                                 | The type of the object.                                      |
| text                   | String      | We're having a Bruh moment! | Required                                                                                                                                                                 | Text contents of the Alert. Keep it short!                   |
| background_color       | String      | #FFFF00                     | Optional - If not defined, the default color scheme should be used                                                                                                       | Color of the Alert card background.                          |
| foreground_color       | String      | #000000                     | Optional - If not defined, the default color scheme should be used                                                                                                       | Color of the text on the Alert card.                         |
| night_background_color | String      | #727200                     | Optional - If not defined but background_color is, use the same value as background_color. If background_color isn't defined either, use the default night color scheme. | Alternative night theme color for the Alert card background. |
| night_foreground_color | String      | #FFFFFF                     | Optional - If not defined but foreground_color is, use the same value as foreground_color. If foreground_color isn't defined either, use the default night color scheme. | Alternative night theme color for the Alert card text.       |
| links                  | JSON object | See below                   | Optional - May be empty ({}) or not defined at all                                                                                                                       | Link buttons that should appear on the Alert card.           |

The links parameter contains another JSON object within it, that specifies buttons that should appear on the Alert card. This Alert has the following:
```json
"links": {
  "Clever": "https://clever.com/",
  "Enriching Students": "https://student.enrichingstudents.com/dashboard"
}
```
Each key ("Clever", "Enriching Students") indicates the name that should be displayed on the button. And the values (the URLs) indicate the link that should be opened when the button is clicked on. For example, this Alert would show two buttons on it. One would read "Clever", and the other would read "Enriching Students". When the Clever button is clicked, the Clever URL will open. When the Enriching Students button is clicked, the Enriching Students URL should open.

Any number of Alerts can appear at a time, whether that be 1 Alert, 10 Alerts, or none at all.