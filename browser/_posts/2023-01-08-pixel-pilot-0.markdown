---
layout: default
title:  "PixelPilot Introduction"
date:   2023-01-08 11:36:40 +0100
category: asm
---

# (PixelPilot) - Introduction

Hello, World! I'm going to create my own browser engine.

# Table of Contents
1. [What is PixelPilot?](#what-is-PixelPilot?)
2. [Why PixelPilot?](#why-PixelPilot?)
3. [Browsers architecture](#browsers-architecture)
    1. [What is a browser engine](#what-is-a-browser-engine)
4. [Connection](#connection)
   1. [Request](#request)
   2. [Response](#response)

## What is PixelPilot?

PixelPilot is a simple browser engine built for fun and profit.

## Why PixelPilot?

You may be wondering why someone the earth would make a browser from scratch?
A browser is quite a complex piece of software after all.

Well, browsers are fundamental to the web. They are the gateway to the internet, and it's worth knowing how they work.
And in fact there are so many cool algorithms and data structures that are used in browsers that it's worth learning about them.

That being said, I built it because I was interested in learning more about browsers inner working.

Enough of motivation, let's get started!

## Browsers architecture

### What is a browser engine

Let's start by talking about what browser engine is and how it works.

A browser engine is a portion of web browser that "works under the hood" and is responsible for displaying web pages.
It translates HTML, CSS and JavaScript into a format that can be displayed on the screen.
Some of the most popular browser engines are: Blink, Gecko, WebKit, Trident and EdgeHTML. To not get confused the
browser's own UI,tabs, address bar, etc. is not part of the browser engine but is part of the browser itself, such as
chrome, Firefox, etc.

When you try to visit a website, there are some things that happen behind the scenes. Here are some steps that actually
happen:

```
+-----+ HTTP    +------+ PARSE   +-----+ CSS COMPUTING  +--------------+ LAYOUT    +-------------------+ RENDER   +--------+
| URL +-------> | HTML +-------> | DOM +--------------> | DOM WITH CSS +---------> | DOM WITH POSITION +--------> | BITMAP |
+-----+         +------+         +-----+                +--------------+           +-------------------+          +--------+
```

1. HTTP request and response parser: when entering a URL of a website in the browser, the browser sends an HTTP request
 to the server. The server then responds with the HTML code of the website. The browser then extract the HTML code from
 the response and parses it into a DOM tree.
2. HTML parsing and CSS computing: the browser then parses the HTML code into a DOM tree. It also parses the CSS code
 and computes the styles for each element in the DOM tree.
3. Layout and Rendering: the browser then computes the position of each element in the DOM tree. It then renders the
 DOM tree into a bitmap.

## Connection

A browser displays information identified by a URL. The URL is a string that identifies a resource on the internet.
The resource can be a web page, an image, a video, etc.

The first step is to connect to the server that hosts the resource. The browser sends an HTTP request to the server
and then downloads a copy of that information.

For testing and development I'm going to use [telnet](https://en.wikipedia.org/wiki/Telnet) or [nc](https://en.wikipedia.org/wiki/Netcat) to connect to a server.
I also will use [this web page](http://example.com/) to get started with. As for URL specification, I'm going to use
[rfc3983](https://tools.ietf.org/html/rfc3986) and [rfc1808](https://www.rfc-editor.org/rfc/rfc1808).

### Request

I don't going to explain requests in detail, there are great resources on the [internet](https://www.ibm.com/docs/en/cics-ts/5.3?topic=protocol-http-requests) 
that explain it. But as for specificaion reference, I'm going to use [rfc7230](https://tools.ietf.org/html/rfc7230) and [rfc7231](https://tools.ietf.org/html/rfc7231).

### Response

Of course, the response has its own structure as do the requests. Again you can refer on the internet to learn more about it.

