---
layout: archive
lang: en
ref: ros_2
read_time: true
share: true
author_profile: false
permalink: /docs/en/platform/turtlebot3/ros2_basic_operation/
sidebar:
  title: TurtleBot3
  nav: "turtlebot3"
product_group: turtlebot3
page_number: 28
---

<div style="counter-reset: h1 16"></div>

# [Basic Operation](#basic_operation)

## [Teleoperation](#teleoperation)

1. Run teleoperation node on **remote PC**
```bash
$ export TURTLEBOT3_MODEL=${TB3_MODEL}
$ ros2 run turtlebot3_teleop teleop_keyboard
```

2. If the node is successfully run, the following instruction will be appeared to the terminal window.  
    ```bash
    Control Your TurtleBot3!
    ---------------------------
    Moving around:
            w
       a    s    d
            x

    w/x : increase/decrease linear velocity (Burger : ~ 0.22, Waffle and Waffle Pi : ~ 0.26)
    a/d : increase/decrease angular velocity (Burger : ~ 2.84, Waffle and Waffle Pi : ~ 1.82)

    space key, s : force stop

    CTRL-C to quit
    ```
