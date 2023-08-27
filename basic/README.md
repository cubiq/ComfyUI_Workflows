# Basic

This section contains the workflows for basic text-to-image generation in ComfyUI. These are the scaffolding for all your future node designs.

## [Basic SD1.x/2.x Workflow](./basic_workflow.json)

The easiest image generation workflow. We will examine each aspect of this first workflow as it will give a better understanding on how Stable Diffusion works but it's not something we will do for every workflow as we are mostly learning by example.

<img src="images/wf_sd1x_basic.png" alt="cat" width="100%" />

1. You start by loading a checkpoint which is the brain the generation. For this tutorial be sure to have at least the file [v1-5-pruned-emaonly.safetensors](https://huggingface.co/runwayml/stable-diffusion-v1-5/resolve/main/v1-5-pruned-emaonly.safetensors) installed in your `ComfyUI/models/checkpoints` directory, but you can use whatever SD1.5 model you want.

2. Next we set the **Latent** size. It is important to understand the difference between *latent and pixel space*. The image is actually processed in an environment that contains a lot more information than what our eyes can see. This environment is the **Latent**. Once the computation is finished the data can be interpreted and converted into **pixels**. This phase happens at #5 "Vae Decode" in the picture above.

3. Time to add a Positive and Negative prompt. The text has to interpreted into a language the machine can understand. This translation is performed by CLIP models (hence the node name "CLIP Text Encode").

4. If the checkpoint is the brain, the **KSampler** is the engine. We now have all the data needed to crunch some numbers. The main parameters we need to set are the following:
    - **Seed**: this is the number used to seed the random number generation. Different seed = different image.
    - **Steps**: number of steps used to reach the final image. More steps require more time to compute but might grant a better composition. That greatly varies based on the prompt, the sampler and the checkpoint. If usure start with a 15-20 value.
    - **CFG**: The *Classifier-free Guidance* scale defines how close the image will be to your prompt. The lower the number the less the model will "make up". If you are trying to create complex images the model is not directly trained for, a higher CFG might help with the composition. Generally a value between 4 and 9 should cover all your use cases but it depends on many factors including the checkpoint you are using.
    - **Sampler** and **Scheduler** together are deputized to carry on the noise in the latent space until the final image is reached withint the defined steps. Some samplers may reach a good reasult in less steps but might be slower. Generally speaking there's not a "best" sampler but good overall options are "euler ancestral" and "dpmpp_2m karras" but be sure to experiment with all of them.

5. Finally the latent is converted into an image we can see thank to the VAEDecode node. Note that the conversion is lossy and it's computationally heavy, so during your experiments the more you can work within the latent space the better.

**Important:** In ComfyUI the random number generation is different to other UIs, that makes it very difficult to recreate the same image generated for example on A1111.

**Tio:** The connection "dots" on each node has a color, that color helps you understand where the node should be connected to/from.

**Tip:** If the image looks oversaturated or has too much contrast, try to lower the CFG scale.