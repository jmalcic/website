---
title: Control interface for IoT cooperative art experience and psychology experiment
---

Rebuild of pilot web app for controlling experiment involving fleet of Raspberry Pis, using Flask and Hotwire, with emphasis on future extensibility and ergonomics. New concurrency design decoupling server and video stream control to avoid server restarts, dynamic discovery and display of other experiment participants using mDNS, ability to run and display live output of Ansible provisioning operations across fleet, and other UX and UI improvements.
