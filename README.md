# Webring Starter Kit

A boilerplate to host your own community of sites, also known as a [webring](https://en.wikipedia.org/wiki/Webring).  
Inspired by posts from [Tatiana Mac](https://twitter.com/TatianaTMac/status/1114388079630929926) and [Charlie Owen](https://www.sonniesedge.net/posts/webrings).

Uses [Eleventy](https://www.11ty.io) and [Netlify](https://www.netlify.com/) to build a central directory for member sites. People can link to `/prev`, `/random` and `/next` and be redirected to members of the ring.

✏️ Explanatory [Blog Post](https://mxb.dev/blog/webring-kit/)

## Features

* Admins manage the ring on Github
* Members are defined in `src/data/members.json`
* Let people add their site through pull request or submit via email form
* Publish a code of conduct
* Provide an embed code that renders a banner (as a web component)
* Publish an index of all member RSS feeds
* show a SVG map of the ring and its members

## Example

See the __[Demo Site](https://ringlo.netlify.com)__ generated by this code.

## How to host a ring

1. Fork this repo
2. Edit `src/data/meta.json` and fill in your community info
3. Add an avatar image for your ring to `src/assets/images`
4. Remove the demo members in `src/data/members.json`
5. Deploy your site to Netlify
6. After you've set a domain, enter that in `meta.json` as well.

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/vhollo/webring)

## Banner Embed

Members can copy a code snippet and embed it into their sites.
It renders a web component (with the bare links as a fallback).

The index site will produce an embed code with your ring URL and title:

```html
<webring-banner>
    <p>Member of <a href="{{ your-url }}">{{ your-title }}</a></p>
    <a href="{{ your-url }}/prev">Previous</a>
    <a href="{{ your-url }}/random">Random</a>
    <a href="{{ your-url }}/next">Next</a>
</webring-banner>
<script async src="{{ your-url }}/embed.js" charset="utf-8"></script>
```

The design is up to the ring admins. It could look something like this:

![the banner widget](https://mxb.dev/assets/media/webrings/banner.png)

## Local Development

To build the site locally, run these commands:

```shell
# clone this repository
git clone git@github.com:maxboeck/webring.git

# go to the working directory
cd webring

# install dependencies
yarn

# start a local build server and the gulp pipeline
yarn start
```
