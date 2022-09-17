# doohickey

*alternate name, De-5-ofem (it's funny because it's like Deforum but there's 5 models in the notebook)*

A notebook with all the tools I want for Stable Diffusion:
- CLIP guidance
- LPIPS guidance
- support for text-inversion bin loading from the huggingface hub
  - (you can load the entire sd_concepts library with one toggle or specify which concepts to load from any user/organization)
- attention slicing for more memory efficient sampling
- perlin inits for better overall image coherence at high resolutions
- image inits
- multiple models to choose from

(link to open the code in a free GPU instance from Google Colab [here](https://t.co/zCV2xsC3UE))

more to come, feel free to add code and submit issues etc (yipee for open source)

## Good classifier guidance settings for the new open ViT-H
```
classifier_guidance = True
lpips_guidance = False
lpips_scale = 0
loss_scale = 1.
clip_model_name = "ViT-H-14"
clip_model_pretrained = "laion2b_s32b_b79k"
cutn = 2
```

i prefer the new ViT-B
```
classifier_guidance = True
lpips_guidance = False
lpips_scale = 0
loss_scale = 8.
clip_model_name = "ViT-B-32"
clip_model_pretrained = "laion2b_s34b_b79k"
cutn = 8
```

## Text-inversions
`load_full_concept_library` will take a While, it loads every single concept in sd_concepts. To take less time only choose the ones you want (https://huggingface.co/sd-concepts-library) and copy the ids (they should be something like "sd-concepts-library/my-inversion"). under "specific_concepts" you want a list of all the ids to import, like `["sd-concepts-library/my-first-inversion", "sd-concepts-library/my-second-inversion"]` etc

while importing them, it will print the tokens text so you know exactly how to use them in your prompts. Text inversions do not work in the `clip_text_prompt`.


##   later
on the agenda right now are:
- gobig clone
- support clip models from HF (just in case)
- visualization for intermediate steps
- support older text inversion files. this could've been done so easy but im soooo tired
- save/load settings to/from file
