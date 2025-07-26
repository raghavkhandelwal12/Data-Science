# Definition of NLP
- `Natural Language Processing(NLP)` is a field of `Artificial Intelligence` that enables computers to understand, interpret, generate, and repond to human language in a way that is both meaningful and useful.

## More Detailed Version
- NLP combines `linguistics, computer science, and machine learning to allow machines to process and analyze large amounts of natural language data - such as speech or text to perform task like translation, sentiment analysis, speech recognition, and chatbot interactions`.

## Simple Definition:
- NLP is how computers understand and work with human language like English, Hindi, or any spoken/written language.

# NLP VS NLU VS NLG

1. `NLP(Natural Language Processing)` : NLP is the broad field of AI that focuses on the `interaction between computers and human language`. It include entire process of `analyzing, understanding, and generation language`.

**Scope** : 
- Include both `NLU and NLG`
- Convert the end-to-end pipelines: `understanding → processing → responding.`

**Common Task** : 
- Tokenization
- Name Entity Recognition
- Sentiment Analysis.
- Text Classification
- Translation
- Chatbots
- Question Answering

2. `NLU(Natural Language Understanding)` : NLU is a `subfield of AI` that focurses specifically on `understanding the meaning and intent behind the text`. It convert human langauge into structured data that machine can understand.

**Goal** : Extract the semantics(meaning) and intent from the text.

**Key Responsibilities** : 
- Intent Recognition("Book a flight").
- Entity Recognition(e.g. "New York" as a location)
- Semantic Parsing
- Context Understanding.
- Conference Resolution(e.g understanding what "he" refer to)

**Example** : 

`Input` : "What is the weather like in Delhi Today?"
`NLU Output` : 
```
{
    "Intent" : "get_weather",
    "location" : "Delhi",
    "date" : "Today"
}
```

3. `NLG(Natural Language Generation)` : Creating Language: NLG is a another `subfield of NLP` that focuses on the `generation of human-like text or speech from structure data or computer output`.

**Goal** : Convert machine-generated data into natural, fluent language that human can understand.

**Key Capabilities** : 
- Text Summarization
- Report Generation
- Dialogue Generation(e.g ChatGPT Response)
- Content Creation(emails, stories etc)
- Machine Translation(output side)

**Example** : 
`Input Data`: 
```
{
    "temparture" : "35C",
    "location" : "Delhi",
    "condition" : "sunny"
}
```
**NLG Output** : 
```
"It's a sunny data in Delhi with a temprature of 35 degree centigrad"
```


| Feature         | NLP (Natural Language Processing)     | NLU (Understanding)                  | NLG (Generation)                   |
| --------------- | ------------------------------------- | ------------------------------------ | ---------------------------------- |
| **Focus**       | Processing human language             | Understanding meaning & intent       | Generating human-like language     |
| **Stage**       | Full pipeline                         | Input analysis (comprehension)       | Output generation (expression)     |
| **Subfield of** | AI                                    | NLP                                  | NLP                                |
| **Direction**   | Bi-directional                        | Input-focused                        | Output-focused                     |
| **Examples**    | Translation, chatbots, search engines | Intent detection, sentiment analysis | Automated reports, content writing |
