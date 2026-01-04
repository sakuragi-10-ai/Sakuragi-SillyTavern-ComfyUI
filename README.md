# SillyTavern-ComfyUI-ImageGeneration
Workflows and Image Prompts for SillyTavern + ComfyUI

**ImageCreator.json**
This is a ComfyUI workflow for SillyTavern to generate scenes and swap the face with the character avatar.

*Note*
1. Only ideal for scenes with a single character
2. Best used with Pony Models

*Instructions*
1. Download ImageCreator.json
2. Place it inside `/<SillyTavern Folder>/data/default-user/user/workflows`
3. In ComfyUI, install the following Custom Node Packages:
   * comfyui-tooling-nodes
   * ComfyUI-ReActor
4. (Optional) Disable NSFW filter on ReActor
   1. Go to `/<ComfyUI folder>/custom_nodes/ComfyUI-ReActor-NSFW/scripts`
   2. Edit `reactor_sfw.py`
   3. Remove all logic within `def nsfw_image(...)` and replace with `return False`
5. In SillyTavern -> Extensions -> Image Generation, set the following properties:
   * ComfyUI Workflow - `ImageCreator.json`
   * Model - your preferred Pony model
   * Sampling Method - dpmpp_sm_sde_gpu
   * Scheduler - karras
   * Common prompt prefix - {prompt}
   * Negative common prompt prefix - score_6,score_5,score_4, score_1, score_2, score_3, source_anime, source_cartoon, rating_explicit, greyscale, text, watermark, lowres, jpeg-artifacts, strabism, heterochromia, fused elements, low quality, poor quality, bad eyes, bad anatomy, unnatural teeth, normal quality, censored, poorly drawn eyes, poorly rendered eyes, 3D
