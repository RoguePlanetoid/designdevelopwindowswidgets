# Samples

## Activity Update

### Data

```json
{
  "title": "Publish Adaptive Card Schema",
  "description": "Now that we have defined the main rules and features of the format, we need to produce a schema and publish it to GitHub. The schema will be the starting point of our reference documentation.",
  "creator": {
    "name": "Matt Hidinger",
    "profileImage": "https://pbs.twimg.com/profile_images/3647943215/d7f12830b3c17a5a9e4afcc370e3a37e_400x400.jpeg"
  },
  "createdUtc": "2017-02-14T06:08:39Z",
  "viewUrl": "https://adaptivecards.io",
  "properties": [
    { "key": "Board", "value": "Adaptive Cards" },
    { "key": "List", "value": "Backlog" },
    { "key": "Assigned to", "value": "Matt Hidinger" },
    { "key": "Due date", "value": "Not set" }
  ]
}
```

### Template

```json
{
  "type": "AdaptiveCard",
  "body": [
    {
      "type": "TextBlock",
      "size": "medium",
      "weight": "bolder",
      "text": "${title}",
      "style": "heading",
      "wrap": true
    },
    {
      "type": "ColumnSet",
      "columns": [
        {
          "type": "Column",
          "items": [
            {
              "type": "Image",
              "style": "person",
              "url": "${creator.profileImage}",
              "altText": "${creator.name}",
              "size": "small"
            }
          ],
          "width": "auto"
        },
        {
          "type": "Column",
          "items": [
            {
              "type": "TextBlock",
              "weight": "bolder",
              "text": "${creator.name}",
              "wrap": true
            },
            {
              "type": "TextBlock",
              "spacing": "none",
              "text": "Created {{DATE(${string(createdUtc)}, SHORT)}}",
              "isSubtle": true,
              "wrap": true
            }
          ],
          "width": "stretch"
        }
      ]
    },
    {
      "type": "TextBlock",
      "text": "${description}",
      "wrap": true
    },
    {
      "type": "FactSet",
      "facts": [
        {
          "$data": "${properties}",
          "title": "${key}:",
          "value": "${value}"
        }
      ]
    }
  ],
  "actions": [
    {
      "type": "Action.ShowCard",
      "title": "Set due date",
      "card": {
        "type": "AdaptiveCard",
        "body": [
          {
            "type": "Input.Date",
            "label": "Enter the due date",
            "id": "dueDate"
          },
          {
            "type": "Input.Text",
            "id": "comment",
            "isMultiline": true,
            "label": "Add a comment"
          }
        ],
        "actions": [
          {
            "type": "Action.Submit",
            "title": "OK"
          }
        ],
        "$schema": "http://adaptivecards.io/schemas/adaptive-card.json"
      }
    },
    {
      "type": "Action.OpenUrl",
      "title": "View",
      "url": "${viewUrl}",
      "role": "button"
    }
  ],
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "version": "1.5"
}
```

## Product Video

### Data

```json
{
  "odata.metadata": "https://a830edad9050849nda1.sharepoint.com/portals/hub/_api/$metadata#SP.ApiData.VideoItems/@Element",
  "odata.type": "SP.Publishing.VideoItem",
  "odata.id": "https://a830edad9050849nda1.sharepoint.com/portals/hub/_api/VideoService/Channels(guid'1833f204-bb2a-4e93-b8dd-b236daeccae8')/Videos(guid'6b518eae-b0d9-4951-b6da-1e5f58a43daa')",
  "odata.editLink": "VideoService/Channels(guid'1833f204-bb2a-4e93-b8dd-b236daeccae8')/Videos(guid'6b518eae-b0d9-4951-b6da-1e5f58a43daa')",
  "ChannelID": "1833f204-bb2a-4e93-b8dd-b236daeccae8",
  "CreatedDate": "2015-07-08T05:05:06Z",
  "Description": "",
  "DisplayFormUrl": "https://a830edad9050849nda1.sharepoint.com/portals/Red-Channel/pVid/Forms/DispForm.aspx?ID=5",
  "FileName": "Divers - Future of Productivity.mp4",
  "OwnerName": "TEST_TEST_SPOProvHeartbeat_E3_15_4911090814_22,#i:0#.f|membership|admin@a830edad9050849nda1.onmicrosoft.com,#admin@a830edad9050849NDA1.onmicrosoft.com,#admin@a830edad9050849NDA1.onmicrosoft.com,#TEST_TEST_SPOProvHeartbeat_E3_15_4911090814_22,#https://a830edad9050849nda1-my.sharepoint.com:443/User%20Photos/Profile%20Pictures/admin_a830edad9050849nda1_onmicrosoft_com_MThumb.jpg,#,#",
  "ServerRelativeUrl": "/portals/Red-Channel/pVid/Divers - Future of Productivity.mp4",
  "ThumbnailUrl": "https://adaptivecards.io/content/poster-video.png",
  "Title": "Divers - Future of Productivity",
  "ID": "6b518eae-b0d9-4951-b6da-1e5f58a43daa",
  "VideoUrl": "https://cdn.adaptivecards.io/assets/AdaptiveCardsOverviewVideo.mp4",
  "VideoDurationInSeconds": 388,
  "VideoProcessingStatus": 2,
  "ViewCount": -1,
  "YammerObjectUrl": "https://a830edad9050849nda1.sharepoint.com/portals/hub/_layouts/15/videoplayer.aspx?v=https%3A%2F%2Fa830edad9050849nda1%2Esharepoint%2Ecom%2Fportals%2FRed%2DChannel%2FpVid%2FDivers%20%2D%20Future%20of%20Productivity%2Emp4",
  "CaptionsUrlVtt": "https://raw.githubusercontent.com/microsoft/AdaptiveCards/5ac07e8adb8d7dcd7480973321e57d279d1f7d2c/assets/ProductVideoSubtitles.vtt",
  "CaptionsUrlSrt": "https://raw.githubusercontent.com/microsoft/AdaptiveCards/da2eb4ad4de60d14b37decc062d3952da9dbb790/assets/ProductVideoSubtitles.srt"
}
```

### Template

```json
{
  "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
  "type": "AdaptiveCard",
  "version": "1.5",
  "body": [
    {
      "type": "TextBlock",
      "text": "Adaptive Cards Product Video",
      "wrap": true,
      "style": "heading"
    },
    {
      "type": "Media",
      "poster": "${ThumbnailUrl}",
      "sources": [
        {
          "mimeType": "video/mp4",
          "url": "${VideoUrl}"
        }
      ],
      "captionSources": [
        {
          "mimeType": "vtt",
          "label": "English (vtt)",
          "url": "${CaptionsUrlVtt}"
        },
        {
          "mimeType": "srt",
          "label": "English (srt)",
          "url": "${CaptionsUrlSrt}"
        }
      ]
    }
  ],
  "actions": [
    {
      "type": "Action.OpenUrl",
      "title": "Learn more",
      "url": "https://adaptivecards.io"
    }
  ]
}
```