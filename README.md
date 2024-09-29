# Stable Diffusion WebUI Forge/reForge

Stable Diffusion WebUI Forge/reForge is a platform on top of [Stable Diffusion WebUI](https://github.com/AUTOMATIC1111/stable-diffusion-webui) (based on [Gradio](https://www.gradio.app/)) to make development easier, optimize resource management, speed up inference, and study experimental features.

The name "Forge" is inspired from "Minecraft Forge". This project is aimed at becoming SD WebUI's Forge.

# Installing Forge/reForge

Tutorial from: https://github.com/continue-revolution/sd-webui-animatediff/blob/forge/master/docs/how-to-use.md#you-have-a1111-and-you-know-git

### Step 1 - First Install

If you know what you are doing, you can install Forge/reForge using same method as SD-WebUI. (Install Git, Python, Git Clone the reForge repo `https://github.com/Panchovix/stable-diffusion-webui-reForge.git` and then run webui-user.bat):

```bash
git clone https://github.com/irarayzelji2002/sd-webui-reForge-decoraition.git
cd sd-webui-reForge-decoraition
git checkout main
```

Then run

`.\webui-user.bat` or `.\webui-user.sh`

When you want to update:

```bash
cd sd-webui-reForge-decoraition
git pull myrepo main
```

### Step 2 - Download Models

To download:

1. Go to the link of the model, download it or follow the steps if command-line.
2. Place the downloaded file on their respective folder under models/<type of model>

List of models are in `models/my models.txt`

##### Folder: ControlNet

• Downloaded Manually:\
[diffusion_sd_controlnet_canny.safetensors (used)](https://huggingface.co/lllyasviel/sd-controlnet-canny)\
[diffusion_sd_controlnet_depth.safetensors](https://huggingface.co/lllyasviel/sd-controlnet-depth)\
[diffusion_sd_controlnet_mlsd.safetensors](https://huggingface.co/lllyasviel/sd-controlnet-mlsd/tree/main)\
[diffusion_sd_controlnet_seg.safetensors](https://huggingface.co/lllyasviel/sd-controlnet-seg)\
[ip-adapter_sdxl.safetensors](https://huggingface.co/h94/IP-Adapter/tree/main/sdxl_models)\
[kohya_controllllite_xl_canny.safetensors](https://huggingface.co/lllyasviel/sd_control_collection/tree/main)\
[kohya_controllllite_xl_depth.safetensors](https://huggingface.co/lllyasviel/sd_control_collection/tree/main)\
[t2iadapter_color_sd14v1.pth (used)](https://huggingface.co/TencentARC/T2I-Adapter/tree/main/models)\
[t2iadapter_style-fp16.safetensors](https://huggingface.co/webui/ControlNet-modules-safetensors/tree/main)\
[t2iadapter_style_sd14v1.pth](https://huggingface.co/TencentARC/T2I-Adapter/tree/main/models)\

#### Folder: ControlNetPreprocessor

• Automatically downloaded:\
clip_vision/clip_g.pth\
clip_vision/clip_vitl.pth\
midas/dpt_hybrid-midas-501f0c75.pt\
mlsd/mlsd_large_512_fp32.pth\
oneformer/250_16_swin_l_oneformer_ade20k_160k.pth\
uniformer/upernet_global_small.pth\
CLIP-ViT-H-14.safetensors\

#### Folder: diffusers (used in img2img inpainting)

• Automatically downlaoded:\
[models--bert-base-uncased (folder, used)](https://huggingface.co/google-bert/bert-base-uncased)\
[models--Uminosachi--realisticVisionV51_v51VAE-inpainting (folder, used)](https://huggingface.co/Uminosachi/realisticVisionV51_v51VAE-inpainting/tree/main)\
• Downloaded Manually:\
[realisticVisionV51_v51VAE-inpainting.safetensors](https://civitai.com/models/4201?modelVersionId=130090)\

#### Folder: ESRGGAN

• Downloaded Manually:\
[4x_NMKD-Siax_200k.pth](https://docs.gymdreams8.com/automatic1111_upscalers.html#_4x-nmkd-siax-200k)\

#### Folder: Stable-diffusion

• Automatically downloaded (on first install):\
[realisticVisionV51_v51VAE.safetensors (used)](https://civitai.com/models/4201?modelVersionId=130072)\
• Downloaded Manually:\
[juggernautXL_juggXIByRundiffusion.safetensors (Jugg_Xl_by_RunDIffusion)](https://civitai.com/models/133005?modelVersionId=782002)\
[juggernautXL_v9Rundiffusionphoto2.safetensors (V9 + RunDIffusionPhoto 2)] (https://civitai.com/models/133005?modelVersionId=348913)\

#### Folder: VAE-approx

• Automatically downloaded (on first install):\
model.pt\
vaeapprox-sdxl.pt\

### Step 3 - Download Extensions

To install:

1. Run `.\webui-user.bat`, wait for it to load the web ui.
2. Go to "Extensions" tab, then "Available" tab, and click "Load from:".
3. Search for the extension (list above), and click "Install", wait for install to finish, repeat on other extensions.
4. Go to "Installed" tab of "Extensions" tab, click "Check for updates", and click "Apply and restart UI".

List of models are in `extensions/put extensions here.txt`

sd-extension-system-info
sd-webui-agent-scheduler
sd-webui-aspect-ratio-helper
sd-webui-controlnet
sd-webui-inpaint-anything
sd-webui-segment-anything
StyleSelectorXL

### Step 4 - Test Models and Extensions

To run, use `.\webui-user.bat` or `.\webui-user.sh`:

```bash
cd sd-webui-reForge-decoraition
.\webui-user.bat
```

This will open the app in `http://127.0.0.1:7860/`

To exit the app, `Ctrl + C` on the keyboard until exited.

# Notes

### Python Version

To run the app, your computer must have:

#### Python 3.10.6

If you're downgrading, uninstall "Python Launcher" from the "Control Panel" because you have higher Python version installed, so you can install it as administrator.

Download Link: https://www.python.org/downloads/release/python-3106/

Recommended: Windows installer (64-bit)

### Checking dependencies

To check installed modules in the virtual environment:

```bash
cd sd-webui-reForge-decoraition
.\venv\Scripts\activate
pip freeze
```

To export module versions:

```bash
cd sd-webui-reForge-decoraition
.\venv\Scripts\activate
pip freeze > requirements_new.txt
```

To install module from requiremnts.txt manually:

```bash
cd sd-webui-reForge-decoraition
.\venv\Scripts\activate
pip install -r requirements.txt
```

To exit the virtual environment:

```bash
deactivate
```

### Checking if SD Web UI API is working

Make sure SD Web UI is running then go to `http://127.0.0.1:7860/docs`. It should load the different Web APIs available.
