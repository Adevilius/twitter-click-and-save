# [Twitter Click'n'Save](https://github.com/AlttiRi/twitter-click-and-save#twitter-clicknsave)

This userscript allows you to save media content (images, videos) from Twitter's tweets by just a click on a button which appears over the media in tweets.

The content saves (downloads) with the most appropriate filename. The userscript also keeps the download history, so you will not download some media twice if you do not want it. 


## Additional enhancements
- Makes links direct in tweets and in the browser title
- Highlight visited links
- Automatically expands spoilers
- Hides: sign up bar, sign up section; trends; topics to follow

## Installation

_An installed userscript manager browser extension is required._
_(Tampermonkey
[![Chrome image by Google](https://camo.githubusercontent.com/bae47ea3643e2620e4cb40abcb8a9889d4f8c2719232de1e0bd185da0d55a466/68747470733a2f2f69636f6e732e69636f6e617263686976652e636f6d2f69636f6e732f676f6f676c652f6368726f6d652f32342f476f6f676c652d4368726f6d652d69636f6e2e706e67 "Download Tampermonkey for a Chromium based browser")](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo)
[![Firefox image by Mozilla Foundation](https://camo.githubusercontent.com/4bd792755387276114a3bb4c063c99c0efa29fdca0da7be0638ca9fc9fb0ec59/68747470733a2f2f69636f6e732e69636f6e617263686976652e636f6d2f69636f6e732f6361726c6f736a6a2f6d6f7a696c6c612f32342f46697265666f782d69636f6e2e706e67 "Download Tampermonkey for Firefox")](https://addons.mozilla.org/firefox/addon/tampermonkey/),
Violentmonkey
[![Chrome image by Google](https://camo.githubusercontent.com/bae47ea3643e2620e4cb40abcb8a9889d4f8c2719232de1e0bd185da0d55a466/68747470733a2f2f69636f6e732e69636f6e617263686976652e636f6d2f69636f6e732f676f6f676c652f6368726f6d652f32342f476f6f676c652d4368726f6d652d69636f6e2e706e67 "Download Violentmonkey for a Chromium based browser")](https://chrome.google.com/webstore/detail/violentmonkey/jinjaccalgkegednnccohejagnlnfdag)
[![Firefox image by Mozilla Foundation](https://camo.githubusercontent.com/4bd792755387276114a3bb4c063c99c0efa29fdca0da7be0638ca9fc9fb0ec59/68747470733a2f2f69636f6e732e69636f6e617263686976652e636f6d2f69636f6e732f6361726c6f736a6a2f6d6f7a696c6c612f32342f46697265666f782d69636f6e2e706e67 "Download Violentmonkey for Firefox")](https://addons.mozilla.org/firefox/addon/violentmonkey/), 
Greasemonkey
[![Firefox image by Mozilla Foundation](https://camo.githubusercontent.com/4bd792755387276114a3bb4c063c99c0efa29fdca0da7be0638ca9fc9fb0ec59/68747470733a2f2f69636f6e732e69636f6e617263686976652e636f6d2f69636f6e732f6361726c6f736a6a2f6d6f7a696c6c612f32342f46697265666f782d69636f6e2e706e67 "Download Greasemonkey for Firefox")](https://addons.mozilla.org/firefox/addon/greasemonkey/))_

To install just do two clicks:

1. **[Click on this link](https://github.com/AlttiRi/twitter-click-and-save/raw/master/twitter-click-and-save.user.js)**
2. Confirm the installation in your usersript manager.

## Let's look

![https://twitter.com/SpaceX/status/1418667693016711170](https://user-images.githubusercontent.com/16310547/126852065-519d3cb5-77eb-4af0-a0c0-58a9934c5fdd.png "https://twitter.com/SpaceX/status/1418667693016711170")

It adds a colored download button to the left upper corner of a media. It appears only when you hover mouse pointer over the tweet.
The red button means you did not save this image (or video), green — you have downloaded it right now, blue — the media is already saved.

_Note: the green button does not disapper after the mouse leave the tweet in order to easier counting that you have downloaded right now._

## Filename format

I sure this userscript saves files with the best filename.

The filename format looks so: `[twitter] {author}—{YYYY.MM.DD}—{id}—{filename}.{extension}`.

The examples:
- [twitter] SpaceX—2020.05.04—1257328055816601600—EXLtL49UYAA7vCG.jpg
- [twitter] SpaceX—2021.03.30—1376902938635870209—Exu93-nU8AAMAiC.jpg
- [twitter] SpaceX—2021.07.20—1417288642662338564—E6s4ZjGUUAEInfM.jpg
- [twitter] SpaceX—2021.07.23—1418667693016711170—E7AdwdkUYAAqxy3.jpg

## Addition enhancements (more details)

While the main purpose of the userscript is to be **Twitter image and video downloader** it also does some useful things:

### Direct links: in tweets, in title and `a:visited` 

![image](https://user-images.githubusercontent.com/16310547/126907767-49141217-7c43-470e-b5ea-ad0cdc6979fe.png)

Twitter replaces all outer links in tweets with redirect links like it: https://t.co/0MLMmDhZRx?amp=1 (https://example.com).

The userscript transforms redirect links to the original links.

While [Twitter says that it's used for protection](https://developer.twitter.com/en/docs/tco), but it's mostly used for the analytic purpose. 

With the direct link you immitiatly see where it to goes (in the browser bottom corner), also you can copy exactly it with a context menu.

In addtional to it the userscript enables highlight of `:visited` links with `darkorange` color. So you can see did you visit the link before or not. (Note: it's based on the browser history which keeps visits within 3 months).

The more useful feature is that it also adds to `t.co` links in the title the original links.

For example, the default title: 

`Username on Twitter: "A test tweet. https://t.co/0MLMmDhZRx" / Twitter` 

transforms to

`Username: "A test tweet. https://example.com/ (https://t.co/0MLMmDhZRx)"`

It's very useful if you bookmark tweets. You can find the bookmarked tweet by searching of the site's name that was posted in the tweet, since the title is used as a bookmark's description.

_And yes, I did not forget to add `rel="nofollow noopener noreferrer"` to the direct links (If you know what it is)._


### Automatic spoiler expanding

![Profile and Media Spoiler](https://user-images.githubusercontent.com/16310547/126909041-ad6cb522-a44f-49b6-992d-873bbd77ae8e.png)


If you have no Twitter account and you visit a profile or watch tweets with media that were marked as "may include potentially sensitive content" it's starting to be a pain to expand spoilers by a click on "View" button each damning time.

This userscript does it automatically, instantly.

---

## Gallery-dl config
This userscript is suited for single media downloading. If you want to download a balk of media, use [gallery-dl](https://github.com/mikf/gallery-dl).

To have the same filenames use the follow config:
```json
"twitter": {
    "directory": ["[gallery-dl]", "[{category}] {author[name]}"],
    "filename": "[{category}] {author[name]}—{date:%Y.%m.%d}—{retweet_id|tweet_id}—{filename}.{extension}",
    "retweets": "original",
    "videos": true
}
```

Add this to `gallery-dl.conf` config file, so it will look so:
<details>
  <summary>Click to expand</summary>
  
```json
{
  "extractor": {    
    "reddit": {
      "...": "..."
    },
    
    "twitter": {
      "directory": ["[gallery-dl]", "[{category}] {author[name]}"],
      "filename": "[{category}] {author[name]}—{date:%Y.%m.%d}—{retweet_id|tweet_id}—{filename}.{extension}",
      "retweets": "original",
      "videos": true
    },
    
    "tumblr": {
      "...": "...",
      "...": "..."
    }
  }
}
```
_Do not forget to add a comma (`,`) if you put this in the middle of the json file._

</details>
