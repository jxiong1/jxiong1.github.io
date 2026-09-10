---
layout: project
type: project
image: img/rose/rose-square.png
title: "VIP Team RoSE"
date: 2025
published: true
labels:
  - ROS 2
  - Arduino
  - Robotics
  - C++
  - Embedded Systems
summary: "A multidisciplinary robotics project at UH Mānoa focused on developing a Mars rover for the University Rover Challenge."
---

<img class="img-fluid" src="../img/rose/rose-header.png">

Team Robotic Space Exploration (RoSE) is a multidisciplinary undergraduate robotics
team at the University of Hawaiʻi at Mānoa. As part of the Vertically Integrated
Projects (VIP) program, the team designs and builds robotic systems for the
University Rover Challenge (URC).

At the 2025 URC competition, Team RoSE placed 24th out of 114 international teams.
The competition consists of four major missions: Science, Delivery, Equipment
Servicing, and Autonomous Navigation. Each mission requires the rover to perform
different tasks such as collecting scientific samples, navigating difficult
terrain, manipulating objects with a robotic arm, and autonomously reaching
specified locations.

<hr>

### My Contribution

My primary contribution to Team RoSE was developing the teleoperation system for
the rover's 5-degree-of-freedom robotic arm.

I developed a custom ROS 2 node that handled communication between the operator's
controller and the rover. The node converted joystick inputs into byte-encoded
commands and transmitted those commands over a serial connection to an Arduino
microcontroller.

The Arduino decoded the incoming commands and sent the appropriate signals to
the motor controllers. This allowed the operator to precisely control each joint
of the robotic arm, enabling the rover to pick up, manipulate, and place objects
during competition tasks.

The overall communication pipeline was:

<pre>
Operator Controller
        |
        v
     ROS 2 Node
        |
        | Serial Communication
        v
      Arduino
        |
        v
  Motor Controllers
        |
        v
  5-DOF Robotic Arm
</pre>

<hr>

### What I Learned

Working on RoSE gave me experience connecting high-level robotics software with
low-level embedded hardware. In particular, I learned how ROS 2 nodes can
communicate with microcontrollers and how to design a communication protocol
that can reliably translate user input into motor commands.

I also gained experience debugging serial communication and testing the complete
control pipeline under real operating conditions. Small communication or timing
issues could affect the responsiveness of the robotic arm, making systematic
testing and debugging important.

Beyond the technical aspects, working on a large multidisciplinary team taught
me the importance of modular design and clear documentation. The arm control
system had to integrate with other rover subsystems, including the drive system
and science payload, so maintaining clear interfaces between components was
essential.

<hr>

Source: <a href="https://lawrencezheng5.github.io/projects/rose.html">
<i class="large github icon "></i>VIP Team RoSE
</a>
