# doohickey

A notebook with all the tools I want for Stable Diffusion:
- CLIP guidance
- LPIPS guidance
- support for text-inversion bin loading from the huggingface hub
  - (you can load the entire sd_concepts library with one toggle or specify which concepts to load from any user/organization)
- attention slicing for more memory efficient sampling
- perlin inits for better overall image coherence at high resolutions
- image inits
- multiple models to choose from

(link to open the code in a free GPU instance from Google Colab [here](https://colab.research.google.com/github/aicrumb/doohickey/blob/main/Doohickey_Beta.ipynb))

more to come, feel free to add code and submit issues etc (yipee for open source)

## Text-inversions
`load_full_concept_library` will take a While, it loads every single concept in sd_concepts. To take less time only choose the ones you want (https://huggingface.co/sd-concepts-library) and copy the ids (they should be something like "sd-concepts-library/my-inversion"). under "specific_concepts" you want a list of all the ids to import, like `["sd-concepts-library/my-first-inversion", "sd-concepts-library/my-second-inversion"]` etc

while importing them, it will print the tokens text so you know exactly how to use them in your prompts. Text inversions do not work in the `clip_text_prompt`.
