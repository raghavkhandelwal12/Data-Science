# Claude (AI Chatbot, Anthropic)

## 📑 Table of Contents

1. [What is Claude AI?](#what-is-claude-ai)  
2. [Claude AI Versions](#claude-3-released-in-may-2024-includes-one-free-and-two-premium-ai-chatbot)  
   - [Claude 3.5 Sonnet](#claude-35-sonnet)  
   - [Claude 3 Opus](#claude-3-opus)  
   - [Claude 3 Haiku](#cluade-3-haiku)  
   - [Claude 4 Sonnet](#claude-4-sonnet)  
3. [What is Claude User for?](#what-is-claude-user-for)  
4. [How does Claude AI Work?](#how-does-claude-ai-work)  
5. [What are Transformer models?](#what-are-transformer-models)  
6. [What is Constitutional AI?](#what-is-constitutional-ai)  
   - [How was it created?](#how-was-it-created)  
   - [First 3 Constitutional AI rules Are](#first-3-constitutional-ai-rules-are)  
7. [How is Claude Trained?](#how-is-claude-trained)  
8. [The benefits of Claude vs ChatGPT and Gemini](#the-benefits-of-claude-vs-chatgpt-and-gemini)  
   - [Large Context Window](#large-context-window)  
   - [Strong Performance in many Tests](#strong-performance-in-many-tests)  
9. [Claude's Disadvantages](#claudes-disadvantages)  
   - [Limited Image Generation](#limited-image-generation)  
   - [No Internet Browsing](#no-internet-browsing)


## What is Claude AI?

- `Claude AI` is a smart chatbot made by a company called `Anthropic`. It uses powerful language models to understand and respond to human language. Claude is good at `working with natural language and is multimodel`, which means it can understand and respond to `text, audio, and images`. It can do many things like `answer questions, summarize documents, write long article, create diagrams, animations, and even generate computer code`.

- `Claude` follows `Anthropic's Constitutional AI rules`, which are like a set of `ethical guidlines`. These rule help make claude `safer and more responsible` compared to other AI models like `ChatGPT and Google Gemini`. The goal is to make Claude give `helpful answer while avoiding harmful behavior, like being biased or giving unsafe replies`.

**Claude 3, released in May 2024, includes one free and two premium AI chatbot**.

- `Claude 3.5 Sonnet` : It is the version used in the `Free Claude AI`. It is built to be `very fast`, so it can quicly handle user questions and tasks that need fast results. According to `Anthropic`, Claude 3.5 sonnet is `twice as fast` as `claude 3 opus`, which is one of their paid versions.

- `Claude 3 Opus` : It is one of the two advanced version available `Claude Pro(paid) users`. It is made for doing `detailed work, like reading big documents and creating complex content.` Even though it's `slower than claude 3.5 sonnet`, It is more accurate and is less likely to `make up false information(a problem known as **hallucination**)`.

- `Cluade 3 Haiku` : It is the second premium Claude offering. It is the `smallest and fastest of the three` and is ideal for use in `summarizing long documents, real-time customer services and simple text generation`.

- `Claude 4 Sonnet` : It is a powerful, mid-range AI model from Anthropic, part of the larger Claude 4 family, known for its strong coding and reasoning abilities. It's designed to balance high performance with practical use, making it suitable for various applications, including AI assistants, everyday coding tasks, and business intelligence. 

## What is Claude User for?

- In general, People can use Claude AI to help with a wide range of tasks including:
    - Question-answering and research
    - Editing
    - Document summarization, including PDFs and Word documents.
    - Text and content generation
    - Language translation
    - Business plan creation
    - Image and audio processing
    - Code snippet generation and review.

- Unlike Claude 2 and 1, `Claude 3` is multimodel: It can process image and audio content alongside text-based prompts. For example, `Claude 3 can generated e-commerce product descriptions based on images`.

## How does Claude AI Work?

- Like `Gemini and OpenAI's ChatGPT,` Anthropic's Claude family of AI systems are based on the `transformer architecture of neural network.` But unlike its competitors, Claude applies the principle of `Constitutional AI to govern its behavior.`

    - `Transformer Models` : Transformer models are very good at `finding relationships between words that are fat apart in a sentence`. This helps them `understand the meaning better and give longer more accurate answer`.

    - `Constituional AI` : It is guiding set of harm reduction principle designed to make claude more `benefecial with less risks`.

## What are Transformer models?

- Transformers are type of `AI model built for high-performance natural language processing`. They work by `complex mathematical algorithm to statistically predict the most like response to a user query`.
- The transformer `break up user query into **tokens**`. Each token represent either a whole word or a portion of word. `AI model pricing is typically represented as the **cost per token**`. Claude Pro's `context window is 200,000 tokens`, meaning  it can process user queries of up to `200000` tokens in length.

    1. Each token is plotted into a `three-dimensional vector space via mathematical processes`. Tokens that are more similar in meaning are `plotted closer together in space`, This helps the AI understand the meaning. The result of this process is called a `vector embedding`.
    
    2. `Transformers` like `Claude and GPT-4` use `self-attention` to focus on the most `important parts of user inputsand better understand the context`.

    3. AI model like `Cluade use probability and math to guess the most likely response to what you type`. They don't actually know things - They just use patterns from their `training data to give the best possible answer`.

## What is Constitutional AI?

- `Constitutional AI` is a set of `rules and safety guidlines` made by the AI company `Anthropic` to help their chatbot `Claude behave in a safe, honest, and ethical way`.

### How was it created?

- Anthropic asked around `1000 people` to vote on and suggest what rules an AI should follow. These ideas were used to `train claude` and guide its responses.

### First 3 Constitutional AI rules Are:

1. Give answers that are not `harmful and hateful`.
2. Be `honest, reliable, and as truthful as possible`.
3. Make sure responses show `clear and good intentions`.

## How is Claude Trained?

- Like other AIs(e.g, ChatGPT), `Claude was trained using Reinforcement learning from human feedback`.
- Here, Another AI check Claude's answer based on the `Constitutional rule and helps correct them`.

## The benefits of Claude vs ChatGPT and Gemini

- When releasing Claude 3, Anthropic AI conducted a series of LLM benchmarking tests to evaluate their model against those of their two primary competitors : `OpenAI and Goolge`. 

- **Claude demonstrate several key advantages**
    1. Large contex window
    2. Strong performance in many tests
    3. No input or output data retention

### Large Context Window

1. `Large Context Window` : Able to field prompts of up to `200,000 tokens` aprroximately 350 pages of text - claude can remember and use more information when creating relevant answer. By comparison `GPT-4 Turbo and GPT-4o limit users to 128,000 tokens`.

### Strong Performance in many Tests

2. `Strong Performance in many Tests` : When Anthropic tested `Claude 3 against GPT-4 and Gemini 1.0`. `Claude 3 Opus` was the top performer in all selected evaluation benchmarks. 

## Claude's Disadvantages

- While Claude's overall performance is strong when compared to the competition, it also has a handful of weakness that can deleay its acceptance by the greater population.

    - Limited images Generation
    - No internet browsing.

### Limited Image Generation

1. `Limited Image Generation` : Compared to GPT-4o, Claude is less able to create images. While Claude  can produce interactive `flowcharts, entiy relationship diagram and graphs.` It stops short of full image creation.

### No Internet Browsing

2. `No internet Browsing` : Duee to Microsoft's integration with Bing, GPT-4 is able to search the internet when answering user queries. While Claude is regularly updated with new training data, its knowledge based is always several months behind until Anthropic elects to open Claude up to the internet in the same way.
