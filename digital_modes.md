---
layout: default
title: Digital Modes Guide
nav_order: 53
---

**Parks on the Air® Digital modes Guide**

![](/assets/images/pota-256x256.png)

Copyright 2022

Original Author: W8MSC


**Table of Contents**
1. TOC
{:toc}

# Digital modes for POTA activators

This guide contains some best practices and hints to help activators run digital modes from a park.


# Before you start

Operating digital modes during your activation adds complexity to your portable station.

To help activators prepare, here are some common hints:

* Run updates on your computer and keep them current.
* Use a GPS dongle with PPS (Pulse Per Second) for accurate time. This is especially important when using WSJT-X. [BktTimeSync](https://www.maniaradio.it/en/bkttimesync.html) can read accurate time from GPS satellites to keep your computer clock accurate.
* Have an sun shade or anti-glare screen to reduce glare on your laptop or monitor.
* Clear out and archive your old logs before starting a new activation.
* [JTSync](http://www.dxshell.com/jtsync.html) is a companion program for use with WSJT-X that can be used to set your clock to match another station on the air


# WSJT-X

## Create a new log in WSJT-X

Before going to a park, setting up a new log within WSJT-X can help simplify your activation.
By renaming the existing log file, WSJT-X will no longer consider any logged QSOs as "worked before" status. This will allow you to see if hunters or other parks are already in your log for the current UTC day.

You can store logs per park and day by renaming your log files.

* Stop WSJT-X if it is running
* Rename the existing wsjtx_log.adif to an archival name. The filename should match the naming convention per POTA log recommendations.
* Start WSJT-X. It will create a new wsjtx_log.adif once you start logging contacts.


# Use WSJTX-X configurations to manage settings per park

If you travel between multiple locations, you can use the WSJT-X configurations to set park or location-specific settings.
After you have a working configuration with rig control, etc., you can copy the default configuration to park-specific configurations.

* Configuration > Default > Clone
* Rename the new clone to your Park name or another useful shorthand name.
* Configuration > (new name) > Switch To
* Settings > General > My Call (set to correct callsign, if different from your default)
* Settings > General > My Grid (set to the correct grid square)
* Settings > Tx Macros:  Add a new macro, ex:   CQ POTA N8SL (GRID). This will be available in the "Tx 5" field of the standard messages.

Depending on the length of your callsign, you might not have enough characters for the grid square. If so, omit the grid square.

# Logging your QSOs

When you start logging hunters, you can use the comments field of the "Log QSO" window to store your park information. Select the checkbox for "Retain" so you don't have to reenter this information for each QSO.

# Other Digital Modes

Don't forget that other modes besides FT8 can be used. Each contact with a hunter can count as a unique QSO as long as each QSO's mode is unique. For example, a park activator could work one hunter repeatedly on the same band but using different digital modes, such as PSK31, RTTY, FT8, FT4, etc., on the same UTC day.

## Feedback

Send any suggestions you may have about this document [please send email to help@parksonthair.com.](mailto:help@parksonthair.com)

## Acknowledgments

Thanks to all the activators and hunters that participate in the program.
