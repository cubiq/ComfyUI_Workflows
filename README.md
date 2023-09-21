# ComfyUI Workflows

A repository of well documented easy to follow workflows for [ComfyUI](https://github.com/comfyanonymous/ComfyUI).

## Introduction

The workflows are meant as a **learning exercise**, they are by no means "the best" or the most optimized but they should give you a good understanding of how ComfyUI works.

The workflows are designed for readability; the execution flows from left to right, from top to bottom and you should be able to easily follow the "spaghetti" without moving nodes around.

This repo is divided into macro categories, in the root of each directory you'll find the basic json files and an `experiments` directory. The experiments are more advanced examples and tips and tricks that might be useful in day-to-day tasks.

This documetantion is mostly for beginners to intermediate users. Experienced users might find some inspiration in the experiments. No matter your skill level, please let me know if you have suggestions, corrections or if you wish to add a new workflow.

The majority of the workflows work **without** any plugin installed with very few exceptions that are outlined in the documention. This is by design to lower as much as possible the entry level and to avoid conflict with a very fast evolving ecosystem.

## Why ComfyUI

There's a bit of turmoil in the community about [Stability AI](https://stability.ai/) endorsing ComfyUI.

First of all there are many easier to use alternatives (like [StableSwarmUI](https://github.com/Stability-AI/StableSwarmUI)) and you are not forced to use ComfyUI if you are not comfortable with it. The most likely downside is that new features will take a little longer to get implemented outside of Comfy.

ComfyUI has a tidy and swift codebase that makes adjusting to a fast paced technology easier than most alternatives. Its modular nature lets you mix and match component in a very granular and unconvential way. Most Stable Diffusion UIs choose for you the best pratice for any given task, with ComfyUI you can make your own best practice and easily compare the outcome of multiple solutions.

On top of that ComfyUI is very efficient in terms of memory usage and speed.

## How-to

To follow all the exercises, clone or download this repository and place the files in the `input` directory inside the `ComfyUI/input` directory on your PC. That will let you follow all the workflows without errors.

To review any workflow you can simply drop the JSON file onto your ComfyUI work area, also remember that any image generated with ComfyUI has the whole workflow embedded into itself. You can take many of the images you see in this documentation and drop it inside ComfyUI to load the full node structure.

Let's get started!

<img src="images/SDXL_fox.png" alt="fox" width="256" height="256" />

## Categories

### [Basic](basic/README.md)
In this section you'll learn the basics of ComfyUI and Stable Diffusion. Any future workflow will be probably based on one of theses node layouts.

### [Upscale](upscale/README.md)
Explores various options to upscale (aka *hires fix*) a generated image.

### [Text to Image](text2img/README.md)
Advanced Text-to-Image techniques. Word weighting, embeddings, timestepping, gligen, ...

### [Image-to-Image conditioning](image_conditioning/README.md)
An image is worth a thousand words. Image-to-image techniques and some image conditioning models.

### [In/Out painting](in-out_painting/README.md)
How to expand and alter your already generated images.

### [Guided composition](guided_composition/README.md)
In this section we'll explore ControlNets, T2I-Adapter and other techniques to better pose and compose your images.

### TO-DO
This is a work in progress, be sure to check back if there are any new additions. The next planned section is **Detailing** where we'll learn how to cut out pieces (eg. faces, hands) of an image to enhance them.
