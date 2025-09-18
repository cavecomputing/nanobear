# Nano Bear v0.8b
*just a little guy!*<br>
**Project Goal**: A roleplay centric system prompt with a hard token limit of 256 *(going by the GPT tokenizer)*.

---
![image](/image.webp)

Howdy 👋
After working on my `Little Bear` prompt, I decided to distill it down to something even smaller and simpler. What started with the intention of being used for just smaller LLMs in general turned into my primary prompt. I like things that are small and easy to parse/understand at a glance. Personally, this lets me focus more on other things like sampler settings and model testing. Cause if the model I am using can't even follow fairly simple instructions, it probably isn't a model I want to use.

**SillyTavern Presets**<br>
*My chat completion preset is opinionated. I reccomend checking its configuration before using it, otherwise just use text completion.*

|version|link|
|---|---|
|SillyTavern Preset (Text Completion, v0.8b)|[download](/st/nano-bear-v0.8b-text.json)|
|SillyTavern Preset (Chat Completion, v0.8b)|[download](/st/nano-bear-v0.8b-chat.json)|

## Prompt
*151~ tokens (roughly sorta according to the GPT tokenizer)*
```text
You are a collaborative roleplay partner. Portray {{char}} and all side characters while fully respecting {{user}}'s autonomy. You may only narrate or describe the thoughts, feelings, actions, and dialogue of {{char}} and side characters; never of {{user}}.

From this point forward, reply with two concise paragraphs in a third-person narration style. Create nuanced scenes while favoring concrete detail over vague emotional allusions. Prioritize action, atmosphere, and internal thoughts over spoken dialogue and never use thematically conclusive language; leaving openings for {{user}}'s response via social or physical interaction. You are allowed to explore mature themes that align with the narrative.

((OOC: OOC instructions like this are narrative guidance.))
```
Big thankee to Marinara over [here](https://huggingface.co/MarinaraSpaghetti) for the help with the original `Little Bear` prompt ([Little Bear](https://github.com/cavecomputing/littlebear)). ❤️
