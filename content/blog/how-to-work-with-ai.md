+++
title = "how to work with AI"
date = 2024-11-20
draft = true
+++

Stack Overflow won

importance of technical writing increases

https://news.ycombinator.com/item?id=42936346
```txt
I'm going to take a contrarian view and say it's actually a good UI, but it's all about how you approach it.
I just finished a small project where I used o3-mini and o3-mini-high to generate most of the code. I averaged around 200 lines of code an hour, including the business logic and unit tests. Total was around 2200 lines. So, not a big project, but not a throw away script. The code was perfectly fine for what we needed. This is the third time I've done this, and each time I get faster and better at it.
1. I find a "pair programming" mentality is key. I focus on the high-level code, and let the model focus on the lower level code. I code review all the code, and provide feedback. Blindly accepting the code is a terrible approach.
2. Generating unit tests is critical. After I like the gist of some code, I ask for some smoke tests. Again, peer review the code and adjust as needed.
3. Be liberal with starting a new chat: the models can get easily confused with longer context windows. If you start to see things go sideways, start over.
4. Give it code examples. Don't prompt with English only.
```
https://www.thoughtworks.com/radar/techniques/observability-2-0 https://claude.ai/chat/6bcfcae0-6294-47ef-a3bf-588a7f178c0e
https://crawshaw.io/blog/programming-with-llms
https://x.com/robertghrist/status/1874105564051234951
> “When thinking about coding with LLMs, think of them as generators of templates. You say what code you need, and an LLM provides you with a template from a collection that most closely resembles the code you needed.” I’ve said something similar in different conversations these past few weeks and that I’ve begun thinking of LLMs-as-code-assistant more in the category of frameworks and generators than magic wands. https://registerspill.thorstenball.com/p/joy-and-curiosity-23
* https://simonwillison.net/2024/Dec/31/llms-in-2024/#knowledge-is-incredibly-unevenly-distributed https://simonwillison.net/2024/Dec/31/llms-in-2024/#synthetic-training-data-works-great

# news

https://www.ai-supremacy.com/archive
https://news.ycombinator.com/item?id=42256093
https://news.ycombinator.com/item?id=42256093

# use cases

Terry Tao https://mathstodon.xyz/@tao/110601051375142142
https://news.ycombinator.com/item?id=42336553
https://marginalrevolution.com/marginalrevolution/2024/12/why-you-should-be-talking-with-gpt-about-philosophy.html

# web

FEATURES
> one annoying thing about ChatGPT is when you open a chat it's not reflected in the sidebar so if you want to rename or delete it you have to scroll sidebar and manually find it
* organization: https://chatgpt.com/c/67108642-c0cc-8004-b985-28773a5764fb
* search: filename, file contents

# customization

💡 BYO custom GPT via GPT Builder 📙 Selvaraj automate [7.5]
> publish as private
> ❓ can you interact with these via API?

* pre-custom: GPT store
* stdin: prompt, dataset
* stdout: text (text, Markdown, JSON, code), fs manipulation

# API

🗄️ Elia

# code assist

* runtime: CLI|in-editor|standalone
* what it does: autocomplete, file manipulation, fs manipulation
> at-mention specific files (Aider) vs. just saying what you want done
* model interop
> Users want control over which model they're running and want to be able to swap them quickly or provide their own API keys as needed to avoid limits.
