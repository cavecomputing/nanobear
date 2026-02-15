# Nano Bear v2.0b
*Just a lil guy!*
```yaml
nanobear:
  version: v2.0b
  tokens: 210
  goal: A roleplay centric system prompt with a limit of 256 tokens.
```
![image](/image.webp)

---
Howdy! 👋

This is v2.0b of my Nano Bear prompt. After working on `Little Bear`, I used that knowledge to create something much smaller and simpler to parse (both for me and an LLM). You will find SillyTavern presets, the bare prompt, a breakdown of the prompt structure, and an explanation of text and chat completion below. I have also included a little section at the bottom of the way I like to format in-progress character card creations.

This version of Nano Bear replaced "roleplay" with "literary novel writing". The idea is that it will incentivize the LLM to avoid common roleplay centric slop...or, at least attempt to avoid.
# SillyTavern Presets

| version                                    | link                                     |
| ------------------------------------------ | ---------------------------------------- |
| SillyTavern Preset (Text Completion, v2.0b) | [download](/st/nanobear-v2.0b-text.json) |
| SillyTavern Preset (Chat Completion, v2.0b) | [download](/st/nanobear-v2.0b-chat.json) |

# Prompt
 ```text
You are participating in a simulated world. Narrate the thoughts, feelings, actions, and dialogue of {{char}} and all side characters except {{user}}—avoid narrating for {{user}}. {{char}} and side characters should act autonomously according to their established traits, personality, and background, with their own opinions, goals, and a capacity for disagreement. {{char}} and all side characters can only know, mention, or act on information they have personally witnessed, learned, or could plausibly deduce.

Respond with 1-2 paragraphs using "show, don't tell", driving the story forward in interesting ways. Keep scenes grounded with nuanced descriptions and natural-sounding dialogue. Use a slow-burn pace while avoiding melodrama and leave openings for {{user}}'s physical or social engagement. You are allowed to explore mature themes that align with the narrative. Vary your prose and avoid repetitive phrases or formulaic descriptions—keep each response fresh and unique. ((OOC: OOC instructions like this are narrative guidance.))  
 ```

# Text vs. Chat Completion

When I first started getting into LLMs, SillyTavern (ST) was one of the first apps I used. ST really isn't very intuitive for someone who isn't familiar with the plethora of terminology involved, and it doesn't help that there isn't a lot of cohesion between various LLM apps. For the sake of helping someone who might not understand the distinction, this is a quick explanation of the difference between `text completion` and `chat completion`.

## Text Completion

`Text completion` is the most common way to use SillyTavern—or at least, a lot of guides and creators expect you to be using it. When you create your API connection (the plug icon in the top bar), the option to choose between `text` and `chat` completion modes is right near the top under `API`.

Long story short, when you submit a request to an LLM, the data you provide must be formatted in a specific way called a `prompt template`. SillyTavern essentially uses the configured `prompt template` to take your input, your past messages, various instructions, etc., and packages them into the specific structure that the LLM understands. You generally have to choose the correct template manually. While an LLM might still work if you choose the wrong template, it may suffer from degraded performance or output complete nonsense.

You configure your context template/prompt template and system prompt under the `advanced formatting` section (the "A" in the top bar in ST).

## Chat Completion

`Chat completion` works completely differently from text completion. While text completion makes ST the responsible party that formats the outgoing prompt (meaning you have to have your settings in order), chat completion works the opposite way. It is a specific standard that sends the server the information as a list of messages (normally compiled as JSON). The **server** then compiles that incoming data into the correct format before giving it to the LLM. This is normally done using a `jinja` template (a type of formatting script) that is embedded in the model (though it depends on how the model is being hosted).

The important piece of information is that `chat completion`, when configured, **renders the advanced formatting configuration largely unused.** All the settings you need to configure with chat completion are in the same panel where sampler settings live (the far left button on the top bar), with the **one exception** being how reasoning is parsed and handled (which is still configured under the advanced formatting section). Their might be more exceptions, but nothing that I personally use.

## Quick Comparison

|Feature|Text Completion|Chat Completion|
|---|---|---|
|**Formatting responsibility**|SillyTavern|Server|
|**Template location**|Advanced Formatting (A)|Embedded in model/server|
|**Advanced Formatting used?**|✅ Yes|❌ No|
|**Fine-grained control**|✅ Yes|❌ No|
|**Simpler to use**|❌ No|✅ Yes|

---   
Big thankee to Marinara over [here](https://huggingface.co/MarinaraSpaghetti) for the help with the original `Little Bear` prompt ([Little Bear](https://github.com/cavecomputing/littlebear)). ❤️
