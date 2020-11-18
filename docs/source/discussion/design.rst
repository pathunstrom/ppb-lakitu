Design Document
----------------------------------------------------------------------------

This document is an attempt to discuss the goals and design sensibilities of
lakitu.

Lakitu is a dynamic 2-d camera that uses ppb tags to determine what the most
important things are to show on screen, and adjust the position of the
camera automatically.

A very brief rundown of the goal is covered by `this talk`_, specifically
the section on framing.

Likely, this will be a very small project, just the single class and any
related utility functions.

In order to limit how much lakitu needs to interact with end user code,
there will be an enum that defines the classes of "interest" or weight. By
using the enums as tags when adding objects to ppb scenes, the camera can
look up the related objects for processing.

Using the Lakitu camera should follow the ppb model: Either used directly
by setting the ``Scene`` ``camera_class`` attribute to ``ppb_lakitu.Camera``
or by subclassing and setting class attributes to modify the behavior, then
setting that subclass on the scene.

Key parameters:

* asymptotic average weighting between current position and goal
* weights of the the various priorities tags
* zoom controls (minimum and maximum zooms, stop points for pixel artists.)
* scene boards as a nice to have.
* maximum velocities for x and y components

.. _`this talk`: https://youtu.be/tu-Qe66AvtY?t=1288