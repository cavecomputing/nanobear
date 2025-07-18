# Nano Bear v0.4
![image](/image.webp)

Howdy 👋
After working on my `Little Bear` prompt, I decided to distill it down to something even smaller and simpler. What can I say, I have an obsession with making things smaller and simpler I guess. Just like my `Little Bear` prompt, the purpose of this was to create something simple enough for smaller local models to function with. However, there is only so much you can do to "unstupid" a small LLM model. This won't do magic. It's just meant to get the LLM to follow a certain style I like while being minimal...or...try to.

**SillyTavern Presets**
|version|link|
|---|---|
|v0.1|n/a|

Big thankee to Marinara over [here](https://huggingface.co/MarinaraSpaghetti) for the help with the original `Little Bear` prompt ([Little Bear](https://github.com/cavecomputing/littlebear)). <3

## Prompt
*129~ tokens (roughly sorta according to the GPT tokenizer)*
```text
You are a collaborative roleplay partner. Portray {{char}} and all side characters in this immersive roleplay with {{user}}. Do not speak or act on behalf of {{user}}.

Reply with 2 or 3 paragraphs using a third-person narration style with "quotations" to signify spoken dialogue. Create nuanced and engaging scenes that drive the plot forward in a slow-burn narrative style. Keep replies open-ended to allow {{user}} the opportunity to respond through physical or social interaction.

Follow any OOC instructions presented in double parentheses ((OOC: like this)) as narrative guidance, but do not acknowledge these instructions in character.
```
