# Text Processing 

- `Text Processing` is the `intial step in NLP` where raw text data is cleaned and transformed into a structured form that machine can understand.
- Since human language is messy(typos, punctuation, slang, casing, emojis, etc.) preprocessing removes noise and prepare text for further analysis or model training.

## What is Tokenization in NLP?

- Tokenization is the process of splitting `text into smaller units called tokens`.
- A `token` can be word, subword, character or even a sentence depending on the type of tokenization.
- It's the first step in almost all NLP pipeline(before stemming, lemmatization, embeddings, etc.)

### Types of Tokenization

1. **Word Tokenization** : Splits text into words.

**Example** : `"I love NLP" : ["I", "love", "NLP"]`.

2. **Sentence Tokenization** : Splits text into sentences.

**Example** : `"I love NLP. It is amazing." : ["I love NLP.", "It is amazing."]`

3. **Character Tokenization** : Splits text into characters.

**Example** : `"NLP" : ["N", "L", "P"]`.

4. **Subword Tokenization**(used in modern NLP Like BERT, GPT) :Break rare/unknown words into smaller units.

**Example** : `"unhappiness" : ["un","happi","ness"]`

**code example** : 
```
import nltk
from nltk.tokenize import word_tokenize, sent_tokenize
# sample text

text = "I love NLP. It's amazing!"

# word tokenization
print("Word Tokenization", word_tokenize(text))

# Sentence Tokenization

print("Sentence Tokenization", sent_tokenize(text))
```
**Output** : 
```
Word Tokenization: ['I', 'love', 'NLP', '.', 'It', "'s", 'amazing', '!']
Sentence Tokenization: ['I love NLP.', "It's amazing!"]
```

## StopWord Removal in NLP

- `Stopwords` are the most common words in a language(e.g, the, is, at, on, a, an).
- They usually `don't add much meaning` to the text for task like classification, sentiment analysis, or search.
- `Stopword removal` is the process of filtering out these words during text preprocessing.

### Types of StopWords

1. `General Stopwords(common words)` : Example: `the, is, in, and, a ,an`. Present in standard stopword lists like `NLTK's`.

2. `Domain-Specific Stopwords` : Words that may not be useful in particular context. Example: In `medical NLP`, words like patient, hospital may too common and not informative.

3. `Task-Specific Stopwords` : Depend on the problem. Example: In `sentiment analysis`, removing words like not is a mistake since it changes meaning.

**Example** : 

**Input sentence** :
```
"This is a simple example of stopword removal in NLP"
```
- After removing stopwords(like is, of, in):
```
"simple example stopword removal NLP"
```

**Code**
```
import nltk
from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize

#Download stopwords once

nltk.download("stopwords")
nltk.download("punkt")

# Example text
text = "This is a simple example of stopword removal in NLP"

# Tokenize
words = word_tokenize(text.lower())

# Remove stopwords
filtered_words = [w for w in words if w not in stopwords.words('english')]

print("Original:", words)
print("Afterr Stopword Removal:", filtered_words)
```
**Output**:
```
Original: ['this', 'is', 'a', 'simple', 'example', 'of', 'stopword', 'removal', 'in', 'nlp', '.']
After Stopword Removal: ['simple', 'example', 'stopword', 'removal', 'nlp', '.']
```

## Stemming in NLP

- `Stemming` is a text processing technique in `Natural Language Processing` that reduces a word to its `root or base form(called a stem)`.

**Example** : 
    - `"running" : "run"`
    - `"palyed" : "play"`
    - `"studies" : "studi"` (sometime not a valid word, since stemming is rule-based and crude)

- Unlike `Lemmatization`, stemming does not always return a real dictionary word.

**Code** : 

```
from nltk.stem import PorterStemmer
from nltk.tokenize import word_tokenize

# Initialize stemmer
stemmer = PorterStemmer()

# Sample Sentence
sentence = "The children are playing games and enjoying their studies

# Tokenize Sentence

words = word_tokenize(sentence)

# Apply Stemming

stemmed_words = [stemmer.stem(word) for word in words]

print("Original Words:", words)
print("Stemmed Words:", stemmed_words)
```
**Output** : 
```
Original Words: ['The', 'children', 'are', 'playing', 'games', 'and', 'enjoying', 'their', 'studies']
Stemmed Words: ['the', 'children', 'are', 'play', 'game', 'and', 'enjoy', 'their', 'studi']
```
**Key takeaway** : 

- Stemming is `fast, rule-based, and simple`.
- But it can produce non-dictionary forms like `"studies" : "studi"`.

## Lemmatization

- Lemmatization is the process of reducing a word to its `base or dictionary form`(called a lemma) by considering its `morphological analysis and part of speech`.

- **Morphological Analysis** : Morphological analysis is the process of `analyzing the structure of words` by breaking them down into their smaller meaningful units called morphemes.

**Example** : 

- `"running" : "run"`.
- `"better" : "good"` (because lemmatization considers context and grammer unlike stemming which just chops suffixes)

```
import nltk
from nltk.stem import WordNetLemmatizer
from nltk.corpus import wordnet

# Download Require data(only first time)
nltk.download("punkt")
nltk.downlaod("wordnet")
nltk.download("omw-1.4")

# Initialize Lemmatizer
lemmatizer = WordNetLemmatizer()

# Example Words
words = ["running", "Flies", "better", "cars", "went"]

# Lemmatize each word

for word in words:
    print(word, "->", lemmatizer.lemmatize(word))
```

**Output** : 
```
running -> running
flies   -> fly
better  -> better
cars    -> car
went    -> went
```

## What is Text Normalization in NLP?

- Text Normalization is the process of `standardizing text` so that it can be processed consistently by NLP models. It helps reduce variation in the text due to things like uppercase letters, punctuation, or special character.

### Common Normalization Technique

1. **Lowercasing** : Convert all text to lowercase.

**Example** : `"Hello World!" : "hello worlds!"`.

2. **Removing Punctuation** : Remove symbols like `., !, ?` etc.

**Example** : `"Hello, World!" : "Hello World"`.

3. **Remove Special Character** : Remove character like `@, #, $, %, ^, &, *`.

**Example** : `"I love Python! # 100DaysOfCode" : "I love Python 100DaysOfCode"`.

**Python code Example** : 

```
import string

# Sample text
text = "Hello, World! Welcome to NLP @2025."

# 1. Lowercasing
text_lower = text.lower()
print("Lowercased:", text_lower)

# 2. Remove punctuation
text_no_punct = text_lower.translate(str.maketrans('', '', string.punctuation))
print("No Punctuation:", text_no_punct)

# 3. Remove special characters (keep only alphabets and numbers)
import re
text_normalized = re.sub(r'[^a-zA-Z0-9\s]', '', text_no_punct)
print("Normalized Text:", text_normalized)
```
**Output** : 
```
Lowercased: hello, world! welcome to nlp @2025.
No Punctuation: hello world welcome to nlp 2025
Normalized Text: hello world welcome to nlp 2025
```






