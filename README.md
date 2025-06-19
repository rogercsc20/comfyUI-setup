# 🧠 ComfyUI Ultra-Realistic AI Workflow (FaceID + Inpainting + Detailer + Upscalers)

This repository documents the full working setup of a high-fidelity **ComfyUI workflow** for **ultra-realistic character creation**, including **FaceID consistency**, **inpainting**, **high-resolution upscaling**, and **AI detailing** using industry-grade tools and LoRAs.

> ✅ Verified on `g5.2xlarge` EC2 instance with 200GB EBS – tested and working with full VRAM optimization.

---

## 🚀 Features

- ✅ FaceID Consistency using `ip-adapter-faceid-plusv2` (bin + LoRA)
- ✅ Multiple ultra-realistic checkpoints preloaded (Juggernaut XL, Dreamshaper Lightning, SD1.5)
- ✅ SDXL-compatible Eye & Face Detectors
- ✅ Upscalers: 4x-LSDIR & 4x-FaceUpDAT
- ✅ Stable Yogi Detailer for enhanced skin and eye realism
- ✅ All modules and custom nodes modularly restored and curated
- ✅ Fully portable & dependency-locked with `requirements-comfy.txt`

---

## 🗂️ Directory Structure

ComfyUI/
├── custom_nodes/               # All working custom nodes (modular)
├── models/
│   ├── checkpoints/            # Main models (Juggernaut, Dreamshaper, SD1.5)
│   ├── loras/
│   │   ├── ipadapter/          # FaceID LoRAs
│   │   └── detailer_yogi       # StableYogi detailer
│   ├── ultralytics/bbox/       # Eye/Face/Hand detectors (.pt + .zip)
│   └── upscale_models/         # ESRGAN & other upscale models
├── workflows/                  # JSON workflow files
├── requirements-comfy.txt      # All pinned Python dependencies
└── main.py                     # Launch script (see below)

1. Clone the repo and set up Python

git clone https://github.com/...
cd comfyui-ultrarealistic
python3 -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install -r requirements-comfy.txt

2. Start the UI

python main.py --listen 0.0.0.0 --port 3000

You can now access it at: http://<your-ip>:3000

📦 Models to Download
✅ Installed via ComfyUI-Manager → Model Manager:
ControlNet (ControlNet++):

    xinsir/ControlNet++ (All-in-one ProMax)

FaceID Models:

    ip-adapter-faceid-plusv2_sdxl.bin

    ip-adapter-faceid-plusv2_sdxl_lora.safetensors

    CLIP-ViT-H-14-laion2B-s32B-b79K

    CLIP-ViT-bigG-14-laion2B-39B-b160k

📥 Manual Downloads:
🧠 Detectors:

    Eyes Detection (by adetailer):
    https://civitai.com/models/150925/eyes-detection-adetailer
    ➤ Place in: models/ultralytics/bbox/

🎨 LoRAs:

    Super Eye Detailer by Stable Yogi:
    https://civitai.com/models/178167/detailersbystableyogi
    ➤ Place in: models/loras/

🧱 Checkpoints:

    Juggernaut Inpainting XL FP16
    https://civitai.com/models/575395?modelVersionId=1071060
    ➤ Place in: models/checkpoints/

🔼 Upscalers:

    https://openmodeldb.info/models/4x-LSDIR

    https://openmodeldb.info/models/4x-FaceUpDAT
    ➤ Place in: models/upscale_models/

🧩 Custom Nodes

This setup includes and validates the following nodes:



