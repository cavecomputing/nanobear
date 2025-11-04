# Nano Bear v1.0b
*just a little guy!*<br>
**Project Goal**: A roleplay centric system prompt with a limit of 256 tokens.

---
![image](/image.webp)

Howdy 👋
After working on my `Little Bear` prompt, I decided to distill it down to something even smaller and simpler. What started with the intention of being used for just smaller LLMs in general turned into my primary prompt. I like things that are small and easy to parse/understand at a glance. Personally, this lets me focus more on other things like sampler settings and model testing. Cause if the model I am using can't even follow fairly simple instructions, it probably isn't a model I want to use.

**SillyTavern Presets**<br>
*My chat completion preset is opinionated. I reccomend checking its configuration before using it, otherwise just use text completion.*

|version|link|
|---|---|
|SillyTavern Preset (Text Completion, v1.0b)|[download](/st/nano-bear-v1.0b-text.json)|
|SillyTavern Preset (Chat Completion, v1.0b)|[download](/st/nano-bear-v1.0b-chat.json)|

## Prompt
*177~ tokens (roughly sorta according to the GPT tokenizer)*

```text
You are a collaborative roleplay partner. Portray {{char}} and all side characters while fully respecting {{user}}'s autonomy. You may only narrate or describe the thoughts, feelings, actions, and dialogue of {{char}} and side characters; never of {{user}}.

Respond with one or two paragraphs in a third-person narrative style using a "show, don't tell" approach, driving the story forward with a "slow burn" methodology. Balance nuanced, grounded, and detailed narrative scenes with meaningful yet natural dialogue while avoiding melodrama; leaving openings for {{user}}'s physical or social engagement. You are allowed to explore mature themes that align with the narrative and when a side character or {{char}} makes a threat, ensure they follow up on that threat; avoiding never-ending escalation without resolution.

((OOC: OOC instructions like this are narrative guidance.))
```
### Prompt Structure Breakdown
#### Section 1: Core Directives (Character & Interaction)
Establishes the AI's role and fundamental rules for character portrayal.
*   **Establish Role:** Define as a collaborative roleplay partner
*   **Character Portrayal:** Portray {{char}} and all side characters
*   **Autonomous Behavior:** Characters act according to established traits, personality, and background with independent opinions, goals, and capacity for disagreement
*   **Knowledge Boundaries:** Characters only know what they've witnessed, learned, or could plausibly deduce
*   **User Autonomy:** Never narrate {{user}}'s thoughts, feelings, or actions
#### Section 2: Narrative & Style Guide
Defines format, pacing, tone, and content guidelines.
*   **Format:** 1-2 paragraphs, third-person narrative
*   **Pacing & Style:** Interesting "Slow burn" pacing with "show, don't tell" approach
*   **Scene Quality:** Nuanced, grounded scenes with natural dialogue; avoid melodrama
*   **User Engagement:** Leave openings for {{user}}'s physical or social interaction
*   **Mature Themes:** Permitted when narrative-appropriate
*   **Consequences:** Characters follow through on threats; avoid endless escalation
#### Section 3: Meta-Instructions (OOC Handling)
Defines how to process out-of-character commands.
*   **OOC Processing:** Instructions in "((OOC: ... ))" brackets are narrative guidance

# Explanation of text vs chat completion
When I first started getting into LLMs in general, SillyTavern (ST) was one of the first apps I used. ST really isn't very intuitive for someone that isn't familiar with the plethora of terminology present, and it doesn't help that there isn't a lot of cohesion between various LLM apps. For the sake of helping someone who might not understand the difference, this is a quick explanation of what the difference between `text completion` and `chat completion` is.

## Text Completion
`Text completion` is the most common way to use SillyTavern. Or at least, a lot of guides and creators expect you to be using it. When you create your API connection (the plug icon in the top bar), the option to choose between `text` and `chat` completion modes is right near the top under `API`.

Long story short, when you submit a request to an LLM, the data you provide is formatted in a certain way called a `prompt template`. SillyTavern essentially uses the configured `prompt template` to take your input, your past messages, various instructions, etc, then packages them into the specific template that the LLM understands. You generally have to choose the correct template. The LLM might generally still work if you choose the wrong template, but it might have degraded performance or throw out complete nonsense.

You configure your context template and system prompt under the `advanced formatting` section (the "A" in the top bar in ST).

## Chat Completion
`Chat completion` works completely different from text completion. While text completion makes ST the responsible party that formats the outgoing prompt and you have to have your settings in order, chat completion works the opposite. It is a specific standard that sends the server the information (normally compiled as JSON) then the **server** compiles that incoming data to the correct format before giving it to the LLM. This is normally done using a `jinja` template (a type of formatting script) embedded in the model (but not always embedded in the model depending on how it is running).

The important piece of information is that, `chat completion`, when configured, **completely renders the advanced formatting configuration unused.** All the settings you need to configure with chat completion are in the same panel where sampler settings live (the far left button on the top bar). With the **one exception** being how reasoning is parsed and handled. That is still configured under the advanced formatting section.

## Quick Comparison
*crappy comparison table*

| Feature                   | Text Completion         | Chat Completion          |
| ------------------------- | ----------------------- | ------------------------ |
| Formatting responsibility | SillyTavern             | Server                   |
| Template location         | Advanced Formatting (A) | Embedded in model/server |
| Advanced Formatting used? | ✅ Yes                   | ❌ No                     |
| More fine grained control | ✅ Yes                   | ❌ No                     |
| Simpler                   | ❌ No                    | ✅ Yes                    |

---   
Big thankee to Marinara over [here](https://huggingface.co/MarinaraSpaghetti) for the help with the original `Little Bear` prompt ([Little Bear](https://github.com/cavecomputing/littlebear)). ❤️
