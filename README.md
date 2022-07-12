# Instagram Graph API

The Instagram Graph API allows Instagram Professionals — Businesses and Creators — to use your app to manage their presence on Instagram. The API can be used to get and publish their media, manage and reply to comments on their media, identify media where they have been @mentioned by other Instagram users, find hashtagged media, and get basic metadata and metrics about other Instagram Businesses and Creators.

The API is intended for Instagram Businesses and Creators who need insight into, and full control over, all of their social media interactions. If you are building an app for consumers or you only need to get an app user's basic profile information, photos, and videos, consider the Instagram Basic Display API instead.

The API is built on the Facebook Graph API. If you are unfamiliar with the Facebook Graph API, please read our Facebook Graph API documentation to learn how it works before proceeding.

# Overview

The Instagram Graph API is a collection of Facebook Graph API endpoints that allow apps to access data in Instagram Professional accounts (both Business and Creator accounts). If you are unfamiliar with the Facebook Graph API, please read our Graph API documentation before proceeding.

Base URL
All endpoints can be accessed via the graph.facebook.com host.

more info https://developers.facebook.com/docs/instagram-api/overview

# Getting Started

more info https://developers.facebook.com/docs/instagram-api/getting-started

# IG User Media

you can use this function 

```
import requests

def get_url(instagram_profile_id,instagram_token):
    url = "https://graph.facebook.com/v14.0/"+str(instagram_profile_id)+"/media?fields=id%2Ccaption%2Cis_comment_enabled%2Ccomments_count%2Clike_count%2Cmedia_type%2Cmedia_url%2Cpermalink&access_token="+str(instagram_token)
    r = requests.get(url)
    return r.json()
```

response

```
{
  'data': [
    {
      'id': '183063567070311111',
      'caption': "Hello world !!!",
      'is_comment_enabled': True,
      'comments_count': 0,
      'like_count': 5,
      'media_type': 'IMAGE',
      'media_url': 'https://scontent-lga3-1.cdninstagram.com/v/t51.2885-1511/293599886_111091456238115948_4146983023007772981_n.jpg?_nc_cat=101&ccb=1-7&_nc_sid=8ae9d6&_nc_ohc=gYq_iny7iSUAX-yyWy_&_nc_ht=scontent-lga3-1.cdninstagram.com&edm=AM6HXa8EAAAA&oh=00_AT9oG7E7a7TTH4UBqc73ihwgBc76-VYeOQ60wRDwpWqHbQ&oe=62D2648E',
      'permalink': 'https://www.instagram.com/p/Cf6-fT0I4jHsds/'
    }
    
}
```

# IG Media Insights

you can use this function 

```
import requests

def get_url(instagram_profile_id,instagram_token):
    url = ""https://graph.facebook.com/v14.0/" + str(media_id) + "/insights?metric=impressions%2Cengagement%2Creach%2Csaved%2cvideo_views&access_token=" + str(instagram_token)
    r = requests.get(url)
    return r.json()
```

response

```
{
  'data': [
    {
      'name': 'impressions',
      'period': 'lifetime',
      'values': [
        {
          'value': 13
        }
      ],
      'title': 'Impressions',
      'description': 'Total number of times the media object has been seen',
      'id': '183063567072222/insights/impressions/lifetime'
    },
    {
      'name': 'engagement',
      'period': 'lifetime',
      'values': [
        {
          'value': 5
        }
      ],
      'title': 'Engagement',
      'description': 'Total number of likes and comments on the media object',
      'id': '183063567072222/insights/engagement/lifetime'
    },
    {
      'name': 'reach',
      'period': 'lifetime',
      'values': [
        {
          'value': 12
        }
      ],
      'title': 'Reach',
      'description': 'Total number of unique accounts that have seen the media object',
      'id': '183063567072222/insights/reach/lifetime'
    },
    {
      'name': 'saved',
      'period': 'lifetime',
      'values': [
        {
          'value': 0
        }
      ],
      'title': 'Saved',
      'description': 'Total number of unique accounts that have saved the media object',
      'id': '183063567072222/insights/saved/lifetime'
    }
  ]
}
```
