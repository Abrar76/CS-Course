# 1. Introduction
I chose to explore prompt injection attacks in Large Language Models (LLMs). I find AI security interesting because AI tools are becoming increasingly common, but they can also have security weaknesses. 
# 2. Finding and Selecting the Article
•	Search platform: Google Scholar.
•	Search terms: prompt injection attacks, large language models, review.
•	Article selection: I picked this one because it is recent (2026) and covers attacks, causes and defences in one place.
•	Publication date: 2026.
•	Journal: Computers, Materials & Continua.
•	JUFO rating: Level 1. (I checked the journal’s JUFO rating using its online ISSN (1546-2226)
•	Article type: Review article. 
## 3. Article Information
Article title: Prompt Injection Attacks on Large Language Models: A Survey of Attack Methods, Root Causes, and Defense Strategies
Authors: Tongcheng Geng et al.
Journal: Computers, Materials & Continua
Year: 2026
Article Type: Review Article
JUFO Rating: 1
DOI: 10.32604/cmc.2025.074081
### 4. Review of the Article
# 4.1 What are the key areas being researched?
The key area being researched is about “prompt injections” that are used to trick AI into performing malicious attacks. Prompt injection means sneaking malicious instructions into the input of an AI model so it does something it should not. The authors reviewed 128 studies from 2022 to 2025.
Attacks come in three main types. Direct injection puts the bad instruction straight into the user’s message. Indirect injection hides it in outside content like webpages, documents or emails, which the AI then reads. Multimodal injection hides it in images or other non-text input. The attackers’ goals vary too: leaking secret system prompts, hijacking behaviour, gaining extra privileges, or stealing private data.
On the defence side, researchers study three areas: input filtering and preprocessing, system-level design (like sandboxing and separating instructions from data), and training the model itself to resist attacks.
## 4.2 What's widely agreed upon?
Researchers mostly agree that prompt injection is a real and growing problem. Attacks have developed from simple tricks into automated, optimised and multimodal methods, and some succeed over 90% of the time against unprotected systems.
The core issue is that an LLM can’t reliably tell instructions apart from data. Everything is just text to it. That makes protection hard. Making a model better at following instructions also makes it easier to manipulate. Most also agree that no single defence is enough. The common advice is defence in depth: filter inputs, check outputs, and build safer system architecture. Filters help, but they can be fooled by small changes like encoding.
### 4.3 What are the open questions?
Defences that work against known attacks often fail on new ones. Filters sometimes block harmless requests. Some defences also slow the system down quite a bit. Multimodal attacks (images, audio, video) and attacks in low-resource languages are especially weak spots, and they haven’t been studied enough.
Another problem is evaluation. Studies use different datasets and metrics, so it’s hard to compare results fairly. The authors call for shared benchmarks and testing against adaptive attackers.
Future research should focus on formal verification, meaning mathematical proof that a defence works, and on new model designs that separate instructions from data from the start. Human oversight for high-stakes decisions could also help. In short, AI becomes safer when security is built in from the beginning, not added afterwards.
#### 5. References
Geng, T., Xu, Z., Qu, Y., & Wong, W. E. (2026). Prompt Injection Attacks on Large Language Models: A Survey of Attack Methods, Root Causes, and Defense Strategies. Computers, Materials & Continua.
DOI: https://doi.org/10.32604/cmc.2025.074081 
