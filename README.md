This is a basic Text-to-Image pipeline built in ComfyUI for generating magical forest scenes using Stable Diffusion 1.5.

## Prompt

> A mystical forest at night, glowing mushrooms, cinematic lighting

## Nodes Used

- Load Checkpoint
- CLIP Text Encode (positive + negative)
- Empty Latent Image
- KSampler
- VAE Decode
- Save Image

## How to use

1. Clone this repo
2. Copy the JSON file to `ComfyUI/workflows/`
3. Open ComfyUI → Load Workflow
