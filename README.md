# Silly_ComfyUI_LCM

Requierments:

  lcm-lora-sdv1-5.safetensor:
  1. From https://huggingface.co/latent-consistency/lcm-lora-sdv1-5/tree/main
  2. Download "pytorch_lora_weights.safetensors" and rename to LCM-LORA-SDV1-5.safetensors
  3. move LCM-LORA-SDV1-5.safetensors to the lora-directory in "...\ComfyUI\models\loras\"


In SillyTavern, Under Extensions / Image Generation

  1. Add a new workflow (+)
  
  2. Name it LCM_Vae (or whatever you want to call it)
  
  3. Open workflow editor. (next to the +)
  
  4. Copy and paste content from Silly_LCM_VAE.json to the SillyTavern Workflow Editor and save.

  5. Set "Steps" to 6-8

  6. "CFG Scale" is set to 1.1 in the json-Workflow. (Line 6 if you want to edit:' "cfg": 1.1, )

  7. "Sampling method" is also set in the json. (no point in changing unless you want corrupted images)

# If you want to also be able to include Loras in the prompt you send from SillyTavern, follow these steps:

  1. In ComfyUI / Manager / Custom Nodes Manager

  2. Search and Install "lora tag loader for comfyui" from author: badjeff

  3. You will need to edit the file "nodes.py" in "...\ComfyUI\custom_nodes\comfyui_lora_tag_loader\"

  4. The '<' and '>' have been changed to '!', this is because SillyTavern strip '<'tags'>' from your prompt and it will not get sent to ComfyUI
  
  Line 12 should be changed to:
  ```
       self.tag_pattern = "\![0-9a-zA-Z\:\_\-\.\s\/\(\)\\\\]+\!"
  ```
  
  5. Follow the above instructions to add a new workflow, but copy and paste "SillyLCMVae_LoraTagLoader.json" instead.

  6. You can now use, for example: " !lora:add_detail:0.5! " in your prompt to load add_detail-lora at a strength of 0.5.
