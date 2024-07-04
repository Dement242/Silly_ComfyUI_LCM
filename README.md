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
