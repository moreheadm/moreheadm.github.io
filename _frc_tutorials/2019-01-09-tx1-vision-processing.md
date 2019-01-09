---
layout: post
title: "Vision Processing with the Nvidia Jetson for FRC"
categories: frc
tags: [frc, cv]

---

This post will cover how to set up vision processing for the [First Robotics
Competition](https://www.firstinspires.org/). It's eventually intended to be for
general use, but currently is specific to the team I mentor, Team 6662, and is
updated for the 2019 season. Before I start, a thank you to Team 900, the many
resources (linked at the bottom) they released on the Jetson as a FRC vision
platform have been invaluable.

## Introduction to FRC Vision

In modern FRC games, vision targets are specifically placed around scoring or
other game elements. Therefore, the goal of vision processing in FRC is not
general navigation, but specific improvements to scoring abilities.

There are four major parts of using vision processing:
1. Acquiring images from the camera
2. Processing the images (using for example, the roboRIO or the Jetson)
3. Communicating data from the processed images to the robot control code
4. Acting upon the vision data

It's possible to accomplish all of these steps using the roboRIO alone. However,
it's become standard practice in FRC to use a coprocessor (another computer
that works alongside the roboRIO). There are a few reasons for this:
- The roboRIO is too slow to do complicated vision processing operations.
- Building on the first reason, running vision code on the roboRIO means you
have to implement code to manage when the main robot code runs and when the
vision code runs. This can potentially lead to problems.

Building on the second reason, it's important to remember that in FRC, vision
only augments existing robot capabilities; it's hardly ever key to the proper
functioning of the robot. As in displayed in the crude representation below,
your vision code is useless without working, well-programmed mechanisms, and
your mechanisms are useless without a working drivetrain.

![The Pyramid of FRC](/assets/images/pyramid_of_frc.png)

More info on
[screensteps](
https://wpilib.screenstepslive.com/s/currentCS/m/vision/l/682117-strategies-for-vision-programming).

## Acquiring images from the camera

There are many different options when it comes to cameras. 6662 has the commonly
used [Microsoft Lifecam HD](
https://www.microsoft.com/accessories/en-us/products/webcams/lifecam-hd-3000/t3h-00011),
but I'm sure other similar options work as well. The Kinect used to be an
interesting option, because it provided depth data, but unfortunately it is no
longer sold, so falls afoul of the FRC rules. I recall that Team 900 used the 
[Zed 3D camera](https://www.stereolabs.com/zed/) which provided similar
advantages. However, depending on the application, lack of depth data could
potentially not be a problem, because vision targets and game elements have
fixed size.

The easiest thing to do is to plug the cameras directly into the Jetson. However,
WPILib has a one line function to transmit video from the roboRIO to the driver
station. It shouldn't be too hard to do this from the Jetson, but requires
some figuring out (TODO: actually figure this out). So just plug the USB camera
into the Jetson USB port (obvious, right?).

## Processing the images

Now that we've gotten the image to the Jetson, we need to process it. What does
"process" mean? The image starts as just a collection of pixel values. What we
want to tell the robot is useful information about the robot's state, maybe
estimated distance to the vision target or angle with respect to the target.
Image processing involves turning the image into this type of information.

To facilitate image processing, we use a well-known library called OpenCV (CV
stands for computer vision). On the [Nvidia website](
https://developer.nvidia.com/embedded/learn/tutorials), in the OpenCV section,
they have some videos on OpenCV for Jetson. However, a much easier way to get
started with computer vision is GRIP. GRIP is a graphical program created by the
same people who made WPILib for quickly prototyping vision processing
alogorithms. There is a screensteps on GRIP [here](
https://wpilib.screenstepslive.com/s/currentCS/m/vision/l/463566-introduction-to-grip)
and you can install it on your local computer from [here](
https://github.com/WPIRoboticsProjects/GRIP/releases). 








TODO: add Team 900 links
