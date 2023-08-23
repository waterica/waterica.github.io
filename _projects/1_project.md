---
layout: page
title: pick and place challenge
description: final project for meam 5200 at the university of pennsylvania
img: assets/img/Lab_Place.jpg
importance: 1
category: school
related_publications:
---

*Project final report available by request.*

## introduction

I completed the MEAM 5200 Pick and Place Challenge with three other students (Gary Lin, Anh Nguyen, and Francis Sowande). For this project, we programmed the Franka Emika Panda Arm (“Panda”) to pick up both dynamic and static objects, orient them with the z-axis facing up, and stack them. Our entire code had to run autonomously using only the initial poses of the blocks with no updated position information. Note that our design approach for this project was highly iterative. While the high level functionality of our code remained the same, we made several changes over the course of the project to improve performance.

## high level overview

From a high level, our code functioned as a finite state machine that utilized a simplistic setup involving predefined configurations and some inverse kinematics to minimize the computational complexity. In general, our finite state machine followed the path shown in figure 1a. Figure 1b shows the general set up of the pick and place challenge as well as some key point. 

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/State_Diagram.png" title="state diagram for pick and place challenge" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/positions.png" title="key points" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1: (a) Finite state machine design, (b) Diagram of important points in the pick and place set up.
</div>

### static pick and place

For our static block strategy, the Panda arm began in the true neutral position and moved to the static block area’s neutral pose. This static neutral pose was then used as the "seed" for our gradient descent, optimization-based inverse kinematics function to find and grab blocks in specific orientations in this area. After moving back to the static and then stack neutral poses, conditional statements were used to determine whether or not the block needed to be reoriented and the block is stacked accordingly. This cycle from the stack neutral pose, through the static block grabbing and finally stacking was performed until all blocks were stacked. Figure 2 shows the Panda arm in various positions needed to grab and stack static blocks. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/4poses.png" title="panda poses" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 2: The poses of the robot arm: (a) static neutral position, (b) "grab" position, (c) stack neutral position, (d) stack position.
</div>

We were succesful at picking and placing static blocks. Figure 3 shows the arm placing a block and a stack of 4 static blocks that we were able to achieve during the competition.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Lab_Place.PNG z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Dynamic_Grab_Location.PNG" title="key points" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 3: (a) Panda arm placing a static block, (b) Stack of 4 static blocks.
</div>

### dynamic pick and place

After stacking all static blocks, the Panda then went back to the place neutral pose and moved to another predefined "neutral" pose above the turn table containing dynamic blocks before grabbing a dynamic block and returning to its dynamic neutral pose. From there, the Panda moved the block to the "neutral pose" of the placement area and placed the block on top of the tower. The Panda continued attempting to grab dynamic blocks until the time limit was reached. 

Unlike with the static blocks, we only managed to grab a dynamic block a few times in practice and not at all during the competition. Figure 4 shows the Panda arm successfully retrieving a dynamic block during practice.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/4poses.png" title="panda poses" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 4: Panda arm grabbing a dynamic block.
</div>


<!-- The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}
```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
```
{% endraw %} -->
