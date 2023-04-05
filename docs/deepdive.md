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
> - GameplayTags
>
> GonzoFX utilizes Gameplay Tags to drive the main settings, and which effects it should apply. The Gameplay Tags utilized by GonzoFX are Native Gameplay Tags. Since they are all setup natively in C++, they will just showup in your project settings without needing to load any data tables or .ini's.
> 
> ![](../assets/images/native-tags.png)
> 
> The main GonzoFX control setting tags are:
> > 1. **AlwaysOn** - This is enabled by default. When enabled, GonzoFX will use a looping timer to check for tag and setting changes.
> > 1. **Debug** - This is disabled by default. When enabled, GonzoFX will display various messages when functions are run, and effects applied.
> > 1. **Enabled** - This is enabled by default. With this tag, GonzoFX can be easily turned _on_ and _off_.
> > 1. **Unbound** - This is enabled by default. When enabled, GonzoFX post process effects will not be bound by the bounding box that is native to the actor. When disabled, GonzoFX post process effects will be confined to the limits of the bounding box.
>
> The **Gonzo.Effects** tags are what will determine which post process effects to apply.