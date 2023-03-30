# Gonzo Post Process
Copyright 2023, Mad Tea Party Games. All Rights Reserved.

---
#### *Hope* is **not** a *strategy* 
#### We **need** to avoid going down a path where we might find the doors **slamming** shut behind us.
---
>
> 1. Make a post process actor to apply trippy effects
> 1. ...
> 1. Profit
>
---
## **Plugin Overview:**
---
### **Background:**
> This plugin is intended to allow for quick and easy post process effects. Some of the are common effects, others are intended to add some trippy mind altering effects.
---
### **Quick Start:**
> 1. Place a GonzoFX actor into a level
> 1. Default settings will use a timer to always check for Gameplay Tags and setting changes for the various effects.
> 1. Add Gameplay Tags from under **Gonzo.Effects** to apply the effects
> 1. Individual settings can be found under the **Gonzo Effects** section of the GonzoFX actor.
---
### **Important Information:**
> - Timer can be disabled by removing **Gonzo.AlwaysOn** or setting **Gonzo Update Rate** to **0.0**
> - If **Gonzo.AlwaysOn** is removed, or **Gonzo Update Rate** set to **0.0**, settings and effects can be manually applied by calling the function **UpdateGonzo**, which is exposed to Blueprint.
> - There are also helper functions exposed to Blueprint for starting and stopping the timer if manual control is desired, or things like temporary effects. These would be **GonzoStart** and **GonzoStop**. If using **GonzoStart**, ensure you add **Gonzo.AlwaysOn** as well as setting **Gonzo Update Rate** to a value greater than **0.0**, like the default of **0.1**
> - **StencilMask** and **StencilBuffer** settings found under the effect's Advanced Settings requires the project setting **Custom Depth-Stencil Pass** set to **Enabled with Stencil**
---
## **TODO:**
- Add more details and examples to docs, maybe an example map.
---