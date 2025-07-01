# Claude (AI Chatbot, Anthropic)

## 📑 Table of Contents

1. [What is Claude AI?](#what-is-claude-ai)  
2. [Claude AI Versions](#claude-ai-versions)  
   - [Claude 3.5 Sonnet](#claude-35-sonnet)  
   - [Claude 3 Opus](#claude-3-opus)  
   - [Claude 3 Haiku](#claude-3-haiku)  
   - [Claude 4 Sonnet](#claude-4-sonnet)  
3. [What is Claude Used For?](#what-is-claude-used-for)  
4. [How Does Claude AI Work?](#how-does-claude-ai-work)  
   - [Transformer Models](#transformer-models)  
   - [Constitutional AI Principle](#constitutional-ai-principle)  
5. [What are Transformer Models?](#what-are-transformer-models)  
6. [What is Constitutional AI?](#what-is-constitutional-ai)  
   - [How Was It Created?](#how-was-it-created)  
   - [First 3 Constitutional AI Rules](#first-3-constitutional-ai-rules)  
7. [How is Claude Trained?](#how-is-claude-trained)  
8. [Benefits of Claude vs ChatGPT and Gemini](#benefits-of-claude-vs-chatgpt-and-gemini)  
   - [Large Context Window](#large-context-window)  
   - [Strong Performance in Tests](#strong-performance-in-tests)  
9. [Claude's Disadvantages](#claudes-disadvantages)  
   - [Limited Image Generation](#limited-image-generation)  
   - [No Internet Browsing](#no-internet-browsing)
   - 
## What is Claude AI?

- `Claude AI` is a smart chatbot made by a company called `Anthropic`. It uses powerful language models to understand and respond to human language. Claude is good at `working with natural language and is multimodel`, which means it can understand and respond to `text, audio, and images`. It can do many things like `answer questions, summarize documents, write long article, create diagrams, animations, and even generate computer code`.

- `Claude` follows `Anthropic's Constitutional AI rules`, which are like a set of `ethical guidlines`. These rule help make claude `safer and more responsible` compared to other AI models like `ChatGPT and Google Gemini`. The goal is to make Claude give `helpful answer while avoiding harmful behavior, like being biased or giving unsafe replies`.

## Claude AI Versions

**Claude 3, released in May 2024, includes one free and two premium AI chatbot**.

### Claude 3.5 Sonnet


- `Claude 3.5 Sonnet` : It is the version used in the `Free Claude AI`. It is built to be `very fast`, so it can quicly handle user questions and tasks that need fast results. According to `Anthropic`, Claude 3.5 sonnet is `twice as fast` as `claude 3 opus`, which is one of their paid versions.

### Claude 3 Opus

- `Claude 3 Opus` : It is one of the two advanced version available `Claude Pro(paid) users`. It is made for doing `detailed work, like reading big documents and creating complex content.` Even though it's `slower than claude 3.5 sonnet`, It is more accurate and is less likely to `make up false information(a problem known as **hallucination**)`.

### Claude 3 Haiku

- `Cluade 3 Haiku` : It is the second premium Claude offering. It is the `smallest and fastest of the three` and is ideal for use in `summarizing long documents, real-time customer services and simple text generation`.

### Claude 4 Sonnet

- `Claude 4 Sonnet` : It is a powerful, mid-range AI model from Anthropic, part of the larger Claude 4 family, known for its strong coding and reasoning abilities. It's designed to balance high performance with practical use, making it suitable for various applications, including AI assistants, everyday coding tasks, and business intelligence. 

## What is Claude Used For?

People use Claude AI for:

- Question answering and research  
- Editing  
- Summarizing PDFs and Word documents  
- Content generation  
- Translation  
- Business plan writing  
- Audio and image processing  
- Code snippet generation and review

Claude 3 is **multimodal**, meaning it can work with images and audio. For example, it can generate product descriptions based on an image.

## How Does Claude AI Work?

Claude works like ChatGPT and Gemini using the **transformer architecture** but guided by **Constitutional AI principles**.

### Transformer Models

These models are good at finding relationships between distant words, improving understanding and generating better responses.

### Constitutional AI Principle

A set of safety rules that guide Claude's behavior to be helpful and reduce harm or bias.

## What are Transformer Models?

- Transformers are type of `AI model built for high-performance natural language processing`. They work by `complex mathematical algorithm to statistically predict the most like response to a user query`.
- The transformer `break up user query into **tokens**`. Each token represent either a whole word or a portion of word. `AI model pricing is typically represented as the **cost per token**`. Claude Pro's `context window is 200,000 tokens`, meaning  it can process user queries of up to `200000` tokens in length.

    1. Each token is plotted into a `three-dimensional vector space via mathematical processes`. Tokens that are more similar in meaning are `plotted closer together in space`, This helps the AI understand the meaning. The result of this process is called a `vector embedding`.
    
    2. `Transformers` like `Claude and GPT-4` use `self-attention` to focus on the most `important parts of user inputsand better understand the context`.

    3. AI model like `Cluade use probability and math to guess the most likely response to what you type`. They don't actually know things - They just use patterns from their `training data to give the best possible answer`.

---

## What is Constitutional AI?

A set of **rules and safety guidelines** created by Anthropic to help Claude behave ethically, safely, and honestly.

### How Was It Created?

Anthropic asked **1,000 people** to vote and suggest AI rules. These guided Claude’s training.

### First 3 Constitutional AI Rules

1. Don’t give harmful or hateful answers.  
2. Be honest, reliable, and truthful.  
3. Ensure responses show good intentions.

---

## How is Claude Trained?

Claude is trained with **Reinforcement Learning from Human Feedback (RLHF)**. Another AI checks Claude’s answers using the Constitutional rules and helps correct them.

---

## Benefits of Claude vs ChatGPT and Gemini

### Large Context Window

Claude supports up to **200,000 tokens** — much more than GPT-4 Turbo (128,000 tokens). This allows Claude to understand and reference longer documents.

### Strong Performance in Tests

In benchmark tests, **Claude 3 Opus** outperformed GPT-4 and Gemini 1.0 in many evaluation categories.

## Claude's Disadvantages

Despite strong performance, Claude has a few limitations.

### Limited Image Generation

- Compared to GPT-4o, Claude is less able to create images. While Claude  can produce interactive `flowcharts, entiy relationship diagram and graphs.` It stops short of full image creation.

### No Internet Browsing

Unlike GPT-4 with Bing, Claude has **no live internet browsing**. Its knowledge is updated periodically but remains slightly outdated.

