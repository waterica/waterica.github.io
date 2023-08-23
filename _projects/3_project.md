---
layout: page
title: MPC for Robot‑Based Stroke Therapy
description: Final project for meam 5170 control And optimization with applications in robotics
img: assets/img/15_RH_MPC.gif
importance: 3
category: school
related_publications:
---

**Description:** I worked with a partner to design and evaluate a model predictive controller (MPC) to assist in trajectory tracking with a simulated 1‑DOF rehabilitation robot. I tested the controller by simulating healthy and post-stroke humans as feedback controllers with using least‑squares method to fit the feedback controller to real human trajectory tracking data collected with the TheraDrive robot. I wrote a report and presented a poster comparing the MPC performance with the simulated humans to a traditional assistive PD controller.

**Language:** Python (PyDrake, Matplotlib, NumPy, SciPy)

**Key Competencies:** model predictive control, PD control, least-squares method

**Project Images:**

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/15_RH_MPC_mpc.GIF" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Representative simulated human performing the trajectory tracking task with assistance from the MPC.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/line_plots_mpc.PNG" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Line plots of a representative stroke model (Left) performing the trajectory tracking task different controllers resulting in (Right) different levels of human torque outputs.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/radar_plots_mpc.PNG" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Radar plots comparing human model performance in various controller configurations; (Left) Movement variability defined as the standard deviation of position [◦]; (Center) Percent of total torque provided by the human model; (Right) RMSE of position [◦].
</div>