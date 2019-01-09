---
layout: post
title: "Vision Processing with the Nvidia Jetson for FRC"
categories: frc
tags: [frc, cv]

---

This post will cover how to set up vision processing for the [First Robotics
Competition](https://www.firstinspires.org/). It's eventually intended to be for
general use, but currently is specific to the team I mentor, team 6662, and is
updated for the 2019 season. Before I start, a thank you to team 900, the many
resources (linked at the bottom) they released on the Jetson as a FRC vision
platform have been invaluable.

## Introduction to FRC Vision

In modern FRC games, vision targets are specifically placed around scoring or
other game elements. Therefore, the goal of vision processing in FRC is not 

There are four major parts of using vision processing:
1. Acquiring images from the camera
2. Processing the images (using for example, the roboRIO or the Jetson)
3. Communicating data from the processed images to the robot control code
4. Acting upon the vision data

It's possible to accomplish all of these steps using the roboRIO alone. However,
it's become standard practice in FRC to use a coprocessor (another computer
that works alongside the roboRIO). There are a few reasons for this:
- The roboRIO is too slow to complicated vision processing operations.
- Building on the first reason, running vision code on the roboRIO means you
have to implement code to manage when the main robot code runs and when the
vision code runs. This can potentially lead to problems.

Building on the second reason, it's important to remember that in FRC, vision
only augments existing robot capabilities; it's hardly ever key to the proper
functioning of the robot. As in displayed in the crude representation below, if
your vision code is useless without working, well-programmed mechanisms, and
your mechanisms are useless without a working drivetrain.

![The Pyramid of FRC](/assets/images/pyramid_of_frc.png)

More info on
[screensteps](
https://wpilib.screenstepslive.com/s/currentCS/m/vision/l/682117-strategies-for-vision-programming).

## Acquiring images from camera

There are many different options when it comes to cameras. 6662 has the commonly
used [Microsoft Lifecam HD](
https://www.microsoft.com/accessories/en-us/products/webcams/lifecam-hd-3000/t3h-00011)
I'm sure other similar options work as well. The Kinect used to be an
interesting option, because it provided depth data, but unfortunately it is no
longer sold, so falls afoul of the FRC rules. I recall that Team 900 used the 
[Zed 3D camera](https://www.stereolabs.com/zed/) which provided similar
advantages. However, depending on the application, lack of depth data could
potentially not be a problem, because vision targets and game elements have
fixed size.

The easiest to do is to plug the 


TODO: add Team 900 links
