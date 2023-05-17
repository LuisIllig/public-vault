# Stable Diffusion WebUI

The best way to use stable diffusion for image generation is stable-diffusion-webui by automatic111. [GitHub](https://github.com/AUTOMATIC1111/stable-diffusion-webui)
This tooling also provides alot of extension which enables much more than simple text to image. E.g. upscaling, inpainting, infinite zoom videos, etc.
All [features](https://github.com/AUTOMATIC1111/stable-diffusion-webui-feature-showcase)
Some [Resources](https://www.reddit.com/r/StableDiffusion/comments/yknrjt/list_of_sd_tutorials_resources/)

- [[#General Tips|General Tips]]
- [[#Models|Models]]
	- [[#Models#Gread Models:|Gread Models:]]
- [[#Prompts|Prompts]]
- [[#ControlNet|ControlNet]]
- [[#Plugins|Plugins]]
- [[#Problems and Solutions|Problems and Solutions]]
	- [[#Problems and Solutions#Stable Diffusion Model 2.1|Stable Diffusion Model 2.1]]



## General Tips
- Stable Diffusion is trained on 512x512 images. Therefore it is recommended to use this resolution and to upscale/outpaint  afterwards
- Recommended Sampler DDIM or DPM++ SDE Karras with 50 - 80 Steps

## Models

By default this tool comes with Stable Diffusion 1.5 which is a great model.
How to Install a new model:
- download model in this file format: .ckpt or .safetensors
- move the file to root/models/Stable-diffusion
- press refresh button besides the model list
- profit

Here are two good sites to get Stable Diffusion models: [Hugging Face](https://huggingface.co/models?other=stable-diffusion) and [CIVITAI](https://civitai.com/)
They can also be installed as plugins([Hugging Face](https://github.com/camenduru/stable-diffusion-webui-huggingface) and [CIVITAI](https://github.com/civitai/sd_civitai_extension)):
- Extensions -> Install from URL
- add link and install
- Installed -> Apply and restart UI
- restart webui

CIVITAI is currently not working as a plugin.

Gread Models
- Stable Diffusion 1.5
- [Open Journey 4](https://huggingface.co/prompthero/openjourney-v4)
- [Dreamlike Anime 1.0](https://huggingface.co/dreamlike-art/dreamlike-anime-1.0) (Anime)
- [Waifu Diffusion](https://huggingface.co/hakurei/waifu-diffusion) (Anime, Character)
- breakdomainrealistic
- deliberate
- ghostmix
- realist Vision
- revAnimated

## Prompts

Here are some great sites for prompt suggestions:
- [OpenArt](https://openart.ai/)
- [CIVITAI](https://civitai.com/images)
- [Hugging Face](https://huggingface.co/spaces/huggingface-projects/diffusers-gallery)
- [Prompt Hero](https://prompthero.com/stable-diffusion-prompts)
- [Best 100+ Stable Diffusion Prompts](https://mpost.io/best-100-stable-diffusion-prompts-the-most-beautiful-ai-text-to-image-prompts/#best-ai-architecture-prompts)

## ControlNet

Probably one of the most important tools for Stable Diffusion. Can be used in many ways to control image generation. All it's features are listed on their [GitHub](https://github.com/lllyasviel/ControlNet).
Download all the models you need from [Hugging Face](https://huggingface.co/lllyasviel/ControlNet-v1-1/tree/main) and put them in root/extensions/sd-webui-controlnet/models
Best start with canny, tile and openpose.
A great YT Channel for ControlNet is [Sebastian Kamph](https://www.youtube.com/@sebastiankamph) ControlNet [Playlist](https://www.youtube.com/watch?v=vFZgPyCJflE&list=PLXS4AwfYDUi7zeEgJRM-PfB6KKhXt1faY)
Some great videos:
- [upscaling](https://www.youtube.com/watch?v=EmA0RwWv-os)
- [lighting](https://www.youtube.com/watch?v=_xHC3bT5GBU)
- [style](https://www.youtube.com/watch?v=wDM8iDK-yng)

## Upscaling
There are two recommended ways to upscale:
1. Extras:
	- send image to extras
	- Upscaler 1 Lanczos
	- Upscaler 2 SwinIR_4x (If you don't have that install ultimate uspcaler extension)
	- Upscaler 2 Visibillity ~ 0.1
	- profit
2. ControlNet and ultimate upscale ([video](https://www.youtube.com/watch?v=EmA0RwWv-os))
	- send image to img2img
	- best case add original prompts and settings 
	- low denoising strength ~ 0.1 - 0.2
	- activate controlnet
	- add original image
	- preprocessor: tile-resample and model: controlnet-tile
	- set "ControlNet is more important"
	- set Script to Ultimate SD upscale
	- Target size type: Scale from image size
	- download upscaler from [Hugging Face](https://huggingface.co/datasets/Kizi-Art/Upscale/tree/fa98e357882a23b8e7928957a39462fbfaee1af5) and move it to root/models/ESREGAN
	- refresh and set upscaler to 4x-UltraSharp
	- Generate and if you want to upscale more set img2img to the generated image (not ControlNet's image) and repeat this step

## Plugins

Must haves:
- ultimate upscale
- infinite-image-browsing or images-browser
- controlnet
- aspect-ratio-helper

### [depthmap2mask](https://github.com/Extraltodeus/depthmap2mask)
Creates masks using depth estimation. Very usefull for inpainting.

### [infinite zoom](https://github.com/v8hid/infinite-zoom-automatic1111-webui.git)
Creates infinite zoom videos.

Tips:
- Zoom mode is by default "Zoom-out", there is also an "Zoom-in" option in 

### [ultimate upscale](https://github.com/Coyote-A/ultimate-upscale-for-automatic1111.git)
Adds more upscaling options. For examples see [here](https://github.com/Coyote-A/ultimate-upscale-for-automatic1111/wiki/Examples)

### [infinite-image-browsing](https://github.com/zanllp/sd-webui-infinite-image-browsing.git)
Image Browser without paging. Makes it easy to manage images and prompts.

### [images-browsing](https://github.com/AlUlkesh/stable-diffusion-webui-images-browser)
Same as infinite-image-browsing but with pages.

### [controlnet](https://github.com/Mikubill/sd-webui-controlnet)
Much better control over image generation with many functions.

### [openpose-editor](https://github.com/fkunn1326/openpose-editor)
Create openpose models in sd-webui. Really usefull for controlnets openpose model. 

### [aspect-ratio-helper](https://github.com/thomasasfk/sd-webui-aspect-ratio-helper)
Helps keeping aspect ratios. More can be added in the Settings

### [deforum](https://github.com/deforum-art/deforum-for-automatic1111-webui.git)
Text2Video extension

### [SD-CN-Animation](https://github.com/volotat/SD-CN-Animation.git)
Text2Video extension.

## Problems and Solutions

### Stable Diffusion Model 2.1

Generating images with the new model version 2.1 caused crashes. Adding 
```--no-half-vae --no-half``` to  **COMMANDLINE_ARGS** in the **webui-user.bat** file solved the issue.
Full example:
```Bash
@echo off

set PYTHON=
set GIT=
set VENV_DIR=
set COMMANDLINE_ARGS=--no-half-vae --no-half

call webui.bat
```

# Stuff I need to add

https://aigarlic.fanbox.cc/posts/5923261
https://huggingface.co/stabilityai/sd-vae-ft-mse-original/tree/main
https://pacoup.com/2011/06/12/list-of-true-169-resolutions/
https://huggingface.co/spaces/Gustavosta/MagicPrompt-Stable-Diffusion
https://stable-diffusion-art.com/samplers/