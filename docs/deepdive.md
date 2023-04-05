---
layout: default
title: The Gonzo Way
nav_order: 3
---
# GonzoFX Deep Dive
{: .fs-9 }
[Home](https://madteapartygames.github.io/the-gonzo-docs/){: .btn .btn-purple }
[Quick Start](https://madteapartygames.github.io/the-gonzo-docs/docs/quickstart.html){: .btn .btn-purple }
[Recommends](https://madteapartygames.github.io/the-gonzo-docs/docs/recommends.html){: .btn .btn-purple }
### Yesterday's weirdness is tomorrow's reason why.
{: .fs-4 }

## A Deeper Look Into the GonzoFX Actor:
{: .fs-6 }

### From the Core: 
{: .fs-4 }
> - **Gameplay Tags**
>
> GonzoFX utilizes Gameplay Tags to drive the main settings, and which effects it should apply. The Gameplay Tags utilized by GonzoFX are Native Gameplay Tags. Since they are all setup natively in C++, they will just showup in your project settings without needing to load any data tables or .ini's.
> 
> ![](../assets/images/native-tags.png)
> 
> The main GonzoFX control setting tags are:
> > 1. **Gonzo.AlwaysOn** - This is enabled by default. When enabled, GonzoFX will use a looping timer to check for tag and setting changes.
> > 1. **Gonzo.Debug** - This is disabled by default. When enabled, GonzoFX will display various messages when functions are run, and effects applied.
> > 1. **Gonzo.Enabled** - This is enabled by default. With this tag, GonzoFX can be easily turned _on_ and _off_.
> > 1. **Gonzo.Unbound** - This is enabled by default. When enabled, GonzoFX post process effects will not be bound by the bounding box that is native to the actor. When disabled, GonzoFX post process effects will be confined to the limits of the bounding box.
> >
> > ![](../assets/images/tag-defaults.png)
> >
> The **Gonzo.Effects** tags are what will determine which post process effects to apply.
>
> ![](../assets/images/tag-effects.png)
>
> - **Gonzo Update Rate**
>
> ![](../assets/images/update-rate.png)
>
>  GonzoFX utilizes a timer, specifically **FTimerManager::SetTimer**, to have a looping timer that will always be checking for updates. This setting determines how often the **GonzoUpdate** event will execute, to check for any effect and setting changes. The higher the value, the slower the **GonzoUpdate** event will execute. Default value of **0.1** gives as close to tick as needed. This setting will have no impact if **Gonzo.AlwaysOn** has been removed.
>
>This is chosen over using tick to have an always on type of actor as it is designed to have more than one instance running. There is a chance that I might move this all over to its own async task, but with the option of being able to disable the timer and control this manually, the actor is already very performant.
>
> - **Volume Limits**
>
> ![](../assets/images/volume-limits.png)
>
> GonzoFX, by default, will have the **Gonzo.Unbound** tag applied, making it a global post process effect. With this tag, this setting will have no impact. If the **Gonzo.Unbound** tag is removed, then this setting will determine the bounding box limits making it a local post process effect when the camera is within the **Volume Limits**.
>
> ![](../assets/images/volume-limits-2.png)
>
> - **Native Post Process**
>
> ![](../assets/images/native-post-process.png)
>
> GonzoFX exposes access to the native post process settings via the struct **FPostProcessSettings**. I am not going to detail what each individual setting does, as these are native to the engine, but have been exposed for expanding the capabilities of GonzoFX and allow for further user customization of effects. For more details you can look at the Unreal documentation for **FPostProcessSettings**.
>
>
> - **Gonzo Effects**
>
> ![](../assets/images/gonzo-effects.png)
>
> GonzoFX's main purpose is to provide custom post process effects. These are the individual settings for each effect that can be applied to a GonzoFX actor by applying the corresponding tag from **Gonzo.Effects**. These will be detailed further in the section below.
> 


### Gonzo Effects: 
{: .fs-4 }
> - **Blur**
>
> - **Custom Depth Outline**
>
> - **Distance Fog**
>
> - **Drugs**
>
> - **Drunk**
>
> - **Glitch**
>
> - **Gradient Fog**
>
> - **Hue Panner**
>
> - **Invert**
>
> - **Iridescent**
>
> - **Kaleidoscope**
>
> - **Letterbox**
>
> - **Liquify**
>
> - **Party Lights**
>
> - **Pyramid**
>
> - **Radial Blur**
>
> - **Retro**
>
> - **Tiles**
>
> - **World Glitch**
>

### Advanced Effects: 
{: .fs-4 }
