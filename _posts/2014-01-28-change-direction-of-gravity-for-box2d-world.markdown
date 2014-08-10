---
title: Change Direction of Gravity for box2d world
date: 2014-01-28 08:15:47.000000000 +10:00
---
A while ago I dabbled in implementing gravity for an iPhone game using [box2d](http://box2d.org/). The following will help shed some light on how the gravity works and how to code for it.

A few things beforehand about my specs and notes:

- Xcode 4.01
- cocos2d-iphone v1.0.0-rc
- box2d (not sure which version but it shipped with cocos2d-iphone mentioned above)
- I’ve gone and created a box-2d cocos2d-iphone project
- This tutorial is only really useful if you want to change the direction of gravity for a fixed orientation
image

First things first… the basics. box2d in a nutshell will take a whole lot of object you place onto the world and apply physics to those objects, that’s it. It is your physics engine. It creates the objects, give them physical qualities (density, bounciness, mass, etc).

You define your screen orientation within AppDelegate.mm file. This has a HUGE (note the capital letter, this means it is important!) impact on how gravity works in your app.

The following line is where it all begins

```
[director setDeviceOrientation:kCCDeviceOrientationPortraitUpsideDown];
```

Let’s set a baseline for a box2d world. Hold the device so the home button (the circle one) is at the bottom and front camera are at the top. This is called ‘kCCDeviceOrientationPortrait’.

We have four different orienations we concern ourselves with (I will refer to these as orientation 1 - 4 from now on)

1. kCCDeviceOrientationPortrait
2. kCCDeviceOrientationPortraitUpsideDown
3. kCCDeviceOrientationLandscapeLeft
4. kCCDeviceOrientationLandscapeRight

I’m going to come back to this shortly, the next thing we need to cover is how to apply gravity to a world.

Look at the accelerometer method (see below)

```
- (void) accelerometer:(UIAccelerometer *)accelerometer didAccelerate:(UIAcceleration *)acceleration {
	float accelX =  (float)acceleration.x * 10.0f;
	float accelY =  (float)acceleration.y * 10.0f;
	b2Vec2 gravity(accelX, accelY);
	world->SetGravity(gravity);
}
```

The accelerometer's **acceleration** object will give us our **x** and **y** acceleration in a range from -1 to 1. box2d needs them to be from -10 to 10 (it can be more but for this example let’s just stick to a relativly close value for our actual gravity of 9.8).

For **orientation 1** we will be using **positive values** for **both x and y**. Below are the different values you need to use for each orientation mentioned above.

1. x, y
2. -x, -y
3. -y, x
4. y, -x

You would want to write a switch statement and test against the current device orientation. As this tutorial is only for a fixed orientation I haven't gone into any further detail.

Hopefully with this tutorial you will be able to change the direction of gravity based on a fixed orientation. If there is anything you think should be added please leave a comment.
