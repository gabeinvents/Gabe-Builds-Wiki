---
tags:
  - DRV8825
---

<div class="grid" markdown>

[:fontawesome-solid-arrow-left: Go Back To __Libraries__](../DRV8825%20Breakout%20Board/libraries.md)
{ .card }

[Go Next To __Cloning Inputs__ :fontawesome-solid-arrow-right:](../DRV8825%20Breakout%20Board/Cloning%20Inputs.md)
{ .card }

</div>

---

# Microstepping

Microstepping is a technique used in stepper motor control to achieve higher resolution and smoother motion. Stepper motors move in discrete steps, typically 1.8 degrees per step, or 200 steps per full rotation. Microstepping divides each full step into smaller increments, allowing more precise momements.

If a motor has 200 steps per full rotation at full step, the motor whould have 400 steps per full rotation if it was half-stepped. The 1.8 degree per step rotation would become 0.9 degrees per step.

Advantages of microstepping include:

* Increased resolution
* Smooth motion from the motor taking smaller steps reduces vibration and noise
* Quiter motion from less vibration and the smoother motion

The main disadvanatage of microstepping is that it would reduce the torque, making it difficult for the motor to move larger loads.

---

## Configurating Microstepping

The microstepping is configurated on the breakout board by the selector switches `MO`, `M1` and `M2`. 

<figure markdown="span">
  ![Microstep switch](../attach/DRV8825 Breakout Board/Introduction/pins-microstep.png){ max-width="100%" height: auto; loading="lazy";}
  <figcaption>Microstep selector switches</figcaption>
</figure>

Different combinations of these switches being ON sets the microstep resolution.

Microstep Resolution |  M0  |  M1  |  M2  | Ref. Steps/Revolution
-------------------- | ---- | ---- | ---- | ---------------------
Full Step            | -    | -    | -    | 200 
Half Step            | On   | -    | -    | 400 
1/4 Step             | -    | On   | -    | 800 
1/8 Step             | On   | On   | -    | 1600 
1/16 Step            | -    | -    | On   | 3200 
1/32 Step            | On   | -    | On   | 6400 
1/32 Step            | -    | On   | On   | 6400
1/32 Step            | On   | On   | On   | 6400

!!! warning
    Current limiting should be performed on the driver in full-step configuration

---

## Example

Testing the microstepping configurations is straight forward. Copy the code and setup from the [quick-start example](../DRV8825%20Breakout%20Board/Quick%20Start.md) and configure what switches are in the `ON` position from the table above. Start at `full-step` configuration and work your way down to the `1/32` step resolution.

Change the steps per revolution in the quick-start code as you increase the resolution.

---

<div class="grid" markdown>

[:fontawesome-solid-arrow-left: Go Back To __Quick Start__](../DRV8825%20Breakout%20Board/Quick%20Start.md)
{ .card }

[Go Next To __Cloning Inputs__ :fontawesome-solid-arrow-right:](../DRV8825%20Breakout%20Board/Cloning%20Inputs.md)
{ .card }

</div>