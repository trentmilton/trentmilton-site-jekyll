---
layout: post
title: Optimising Sprite Image Loading In Cocos2d
date: 2014-01-28 08:22:13.000000000 +10:00
tags:
  - cocos2d
  - objective-c
---
CCSpriteBatchNode is the best way to draw multiple sprites with the one texture. The docs state the following;

*"A CCSpriteBatchNode offers improved rendering performance for multiple sprite rendering by utilising a single OpenGL call to render all sprites from one (and only one) texture (one image file, one texture atlas), often knows as a ‘batch draw’."*
