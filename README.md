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

more to come, feel free to add code and submit a PR (yipee for open source)


good classifier guidance settings for the new open ViT-H
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
