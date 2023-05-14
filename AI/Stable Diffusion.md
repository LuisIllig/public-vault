# Stable Diffusion WebUI

The best way to use stable diffusion for image generation is stable-diffusion-webui by automatic111. [GitHub](https://github.com/AUTOMATIC1111/stable-diffusion-webui)
This tooling also provides alot of extension which enables much more than simple text to image. E.g. upscaling, inpainting, infinite zoom videos, etc.
All [features](https://github.com/AUTOMATIC1111/stable-diffusion-webui-feature-showcase)

- [[#General Tips|General Tips]]
- [[#Models|Models]]
	- [[#Models#Gread Models:|Gread Models:]]
- [[#Prompts|Prompts]]
- [[#Plugins|Plugins]]
	- [[#Plugins#depthmap2mask|depthmap2mask]]
	- [[#Plugins#infinite zoom|infinite zoom]]
	- [[#Plugins#ultimate upscale|ultimate upscale]]
- [[#Problems and Solutions|Problems and Solutions]]
	- [[#Problems and Solutions#Stable Diffusion Model 2.1|Stable Diffusion Model 2.1]]


## General Tips
- Stable Diffusion is trained on 512x512 images. Therefore it is recommended to use this resolution and to upscale/outpaint  afterwards
- Recommended Sampler DDIM with 50 - 75 Steps
- Recommended Upscaler 1 Lanczos and Upscaler 2 SwinIR_4x (ultimate upscale plugin)

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

### Gread Models:
- Stable Diffusion 1.5
- [Open Journey 4](https://huggingface.co/prompthero/openjourney-v4https://huggingface.co/prompthero/openjourney-v4)
- [Dreamlike Anime 1.0](https://huggingface.co/dreamlike-art/dreamlike-anime-1.0) (Anime)
- [Waifu Diffusion](https://huggingface.co/hakurei/waifu-diffusion) (Anime, Character)

## Prompts

Here are some great sites for prompt suggestions:
- [OpenArt](https://openart.ai/)
- [CIVITAI](https://civitai.com/images)
- [Hugging Face](https://huggingface.co/spaces/huggingface-projects/diffusers-gallery)
- [Prompt Hero](https://prompthero.com/stable-diffusion-prompts)
- [Best 100+ Stable Diffusion Prompts](https://mpost.io/best-100-stable-diffusion-prompts-the-most-beautiful-ai-text-to-image-prompts/#best-ai-architecture-prompts)
## Plugins
Must haves:
- ultimate upscale

### depthmap2mask
[GitHub](https://github.com/Extraltodeus/depthmap2mask) 
Creates masks using depth estimation. Very usefull for inpainting.

### infinite zoom
[GitHub](https://github.com/v8hid/infinite-zoom-automatic1111-webui.git)
Creates infinite zoom videos.

Tips:
- Zoom mode is by default "Zoom-out", there is also an "Zoom-in" option in 

### ultimate upscale
[GitHub](https://github.com/Coyote-A/ultimate-upscale-for-automatic1111.git)
Adds more upscaling options. For examples see [here](https://github.com/Coyote-A/ultimate-upscale-for-automatic1111/wiki/Examples)

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