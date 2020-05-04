# threader
Easy Twitter threads with Python.

## This fork

Removes specific TwitterAPI dependency

For example, tweepy api will do

## Installation

You can install threader with `pip`:

`pip install threader`

Alternatively, clone this repository to your computer and then run either:

`python setup.py install`

or run

`pip install -e path/to/cloned/folder`

## Usage

Threader basically does one thing, illustrated by the following:

```python
import tweepy
from threader import Threader

keys = dict(consumer_key='XXX',
            consumer_secret='XXX',
            access_token_key='XXX',
            access_token_secret='XXX')

# authentication of consumer key and secret
auth = tweepy.OAuthHandler(keys.consumer_key, keys.consumer_secret)

# authentication of access token and secret 
auth.set_access_token(keys.access_token, keys.access_token_secret)
api = tweepy.API(auth)

tweets = ["@choldgraf made a nifty little tool...",
          "It's for making it easier for him to thread tweets",
          "He heard that the real twitter power users all thread their tweets like pros",
          "but he also likes python, and automating things",
          "sometimes with unnecessary complexity...",
          "and excessive dependencies...",
          "which is why I removed the TwitterAPI dependency...",
          "so let's see if this works :-D"]
th = Threader(tweets, api, wait=2)
th.send_tweets()
```

The preceding code resulted in the following twitter thread:

https://twitter.com/choldgraf/status/979755644545777664

Enjoy!
