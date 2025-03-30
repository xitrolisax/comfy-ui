# ComfyUI Project Repository: Various Image Manipulation Workflows

## Description

This repository contains multiple workflows for image manipulation using **ComfyUI**. The projects cover different tasks, such as background replacement, image refinement, image generation with detailed prompts, and style transfers.

### Projects in this Repository:

1. **Background Replacement**: Replaces the background of an image with various settings (e.g., studio lighting, beige tones).
2. **Image Generation with CLIP**: Uses **CLIPTextEncode** and **KSampler** for generating new images based on text descriptions.
3. **Inpainting**: Fine-tunes specific areas of images, such as background replacement or object refinement.
4. **Advanced ControlNet**: Uses **ControlNet** and inpainting models to refine and adjust generated images.
5. **Lora Model Styling**: Applies Lora models to generate images in specific styles or based on specific conditions.

## Dependencies

Before running these workflows, ensure that you have the following dependencies installed:

1. **ComfyUI**: A visual interface for working with generative models.
2. **Stable Diffusion Checkpoints**:
   - `sdXL_v10VAEFix.safetensors`
3. **Lora Models**:
   - `web_design_active-apex_01.safetensors`
4. **ControlNet Models**:
   - `diffusion_pytorch_model_V2.safetensors`

## Project Overview

### 1. **Background Replacement Workflow**

- **Description**: Replaces the background of an image while keeping the subject intact.
- **Key Nodes**: `InpaintModelConditioning`, `KSampler`, `VAEDecode`, `CLIPTextEncode`.
- **Input**: Image with a subject (e.g., portrait), a corresponding mask.
- **Output**: Image with the background replaced by studio lighting or other settings.

### 2. **Image Generation with CLIP Workflow**

- **Description**: Generates images from a detailed text prompt using **CLIPTextEncode** and **KSampler**.
- **Key Nodes**: `CLIPTextEncode`, `KSampler`, `VAEDecode`.
- **Input**: Text prompt describing the desired image (e.g., "minimalist website homepage design").
- **Output**: New image generated according to the provided text prompt.

### 3. **Inpainting Workflow**

- **Description**: Fine-tunes and inpaints specific parts of the image (like background areas or object refinement).
- **Key Nodes**: `InpaintModelConditioning`, `VAEDecode`.
- **Input**: Image with masked regions for inpainting, mask to specify the areas to be changed.
- **Output**: Refined image with inpainted areas.

### 4. **Advanced ControlNet Workflow**

- **Description**: Uses **ControlNet** for advanced image control and generation with additional refinement based on pre-defined models.
- **Key Nodes**: `ControlNetLoader`, `ControlNetApplySD3`, `InpaintModelConditioning`.
- **Input**: Image, control net models for detailed generation.
- **Output**: Image refined based on ControlNet inputs.

### 5. **Lora Model Styling Workflow**

- **Description**: Applies pre-trained **Lora models** for specific image styles or modifications.
- **Key Nodes**: `LoraLoader`, `VAEDecode`, `KSampler`.
- **Input**: Image, Lora model.
- **Output**: Image with the Lora-styled modifications applied.

## How to Run

### 1. **Set Up Your Environment:**

- Install **ComfyUI** and all the required models (`sdXL_v10VAEFix.safetensors`, `web_design_active-apex_01.safetensors`, and any ControlNet models).
- Ensure all necessary checkpoints and Lora files are placed in the correct directories for ComfyUI to access.

### 2. **Load the Image and Mask:**

For each project, upload your **original image** and, if required, the corresponding **mask** to isolate the subject or areas for inpainting.

### 3. **Customize Text Prompts:**

For projects that use **CLIPTextEncode**, update the **positive** and **negative** prompts based on your desired outcome. Example prompts:

- **Positive**: "portrait of a person, clear details, realistic, soft lighting."
- **Negative**: "unrealistic, ugly, distorted."

### 4. **Connect the Nodes:**

Ensure the nodes are properly connected to achieve the desired result. Each project has its own set of nodes and connections.

### 5. **Run the Workflow and Save the Output:**

Run the workflow for the desired project and save the output to your preferred directory.

## Troubleshooting

- **Image not changing as expected?**
  - Double-check the **mask** for proper alignment and accuracy.
  - Ensure that the **positive** and **negative** prompts are correctly set up for your desired results.
  - Verify node connections to make sure data is passed correctly between nodes.

---

## Example Workflow (Background Replacement)

1. **Load the Image and Mask**:

   - `LoadImage`: Load the original image.
   - `LoadImageMask`: Load the mask for inpainting.

2. **Set Up the Prompts**:

   - `CLIPTextEncode`: Set the positive and negative prompts for the background replacement.

3. **Run the Workflow**:
   - Connect `InpaintModelConditioning`, `KSampler`, and `VAEDecode`.
   - Run the workflow and generate the final image with the background replaced.

## Notes

- **Experiment** with different combinations of prompts, masks, and nodes to get varied results.
- You can modify the **background replacement** prompts and **image generation conditions** according to your needs for each project.

---

Feel free to experiment and adjust the workflows for your specific image manipulation tasks!
