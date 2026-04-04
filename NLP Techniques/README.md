# Experiment 15: Natural Language Processing (NLP) Techniques in Python

**Name:** Khush Chauhan  
**PRN:** 25070123062  
**Batch:** A3  
**Date:** 03/04/2026  

---

## 1. Objective
To understand and implement fundamental Natural Language Processing (NLP) techniques for text preprocessing and analysis using Python's Natural Language Toolkit (`nltk`) library.

## 2. Introduction to NLTK and Resource Downloading
Natural Language Processing (NLP) allows computers to process and analyze large amounts of natural human language data. The experiment utilizes the `nltk` (Natural Language Toolkit) library. Before performing any operations, specific linguistic data packages must be downloaded:

* **`punkt` & `punkt_tab`:** Unsupervised trainable models used for tokenizing sentences and words.
* **`stopwords`:** A corpus containing common filler words in various languages.
* **`wordnet`:** A large lexical database of English used for lemmatization.
* **`averaged_perceptron_tagger`:** The default pre-trained model used for assigning Part-of-Speech tags.

---

## 3. Theoretical Breakdown and Function Descriptions

### A. Tokenization
**Theory:** Tokenization is the foundational step in NLP. It is the process of breaking down a large body of text into smaller, manageable units called "tokens." These tokens can be words, characters, or subwords. It allows the machine to understand the structure of the text.

* **Word Tokenization:** Splits a text string into individual words and punctuation marks.
    * **Function Used:** `word_tokenize(text)` parses the string *"Natural language processing is interesting"* into a list of individual word strings.
* **Sentence Tokenization:** Splits a text string into individual sentences, usually by looking for punctuation like periods, exclamation marks, or question marks.
    * **Function Used:** `sent_tokenize(text)` divides a paragraph into a list of sentences.

### B. Stop Word Removal
**Theory:** Stop words are the most common words in a language (e.g., "is", "the", "and", "in"). While they are necessary for grammatical structure, they rarely carry significant meaning for text analysis tasks like sentiment analysis or keyword extraction. Removing them reduces the dataset size and helps algorithms focus on the important words.

* **Function Used:** `stopwords.words('english')` retrieves a predefined list of English stop words. A list comprehension is then used to filter out any token from our text that appears in this stop word set.

### C. Stemming
**Theory:** Stemming is a rule-based process that heuristically chops off the ends of words to reduce them to their root or base form. For example, "playing", "plays", and "played" all reduce to "play". Because it uses rigid rules, stemming can sometimes result in non-actual words (e.g., "studies" becomes "studi").

* **Function Used:** `PorterStemmer()` initializes one of the most common stemming algorithms. The `.stem(word)` method is applied iteratively to strip suffixes from the input words.

### D. Lemmatization
**Theory:** Unlike stemming, lemmatization considers the context and morphological analysis of the word. It links words with similar meanings to one single word known as the "lemma," which is an actual dictionary word. For example, it correctly identifies that the root of "studies" is "study", and the root of "better" is "good".

* **Function Used:** `WordNetLemmatizer()` initializes the lemmatizer using the WordNet database. The `.lemmatize(word)` method returns the valid dictionary base form of the word. *(Note: Without specifying the Part of Speech context, words like "running" or "coding" may remain unchanged if they are treated as nouns by default).*

### E. Part of Speech (POS) Tagging
**Theory:** POS tagging is the process of marking up a word in a text as corresponding to a particular part of speech (noun, verb, adjective, etc.) based on both its definition and its context. This is crucial for understanding the grammatical structure and meaning of a sentence.

* **Function Used:** `pos_tag(words)` takes a list of tokenized words and returns a list of tuples, where each tuple contains the word and its corresponding POS tag.
* **Observation:** In the phrase *"Python is a powerful programming language"*, the tagger correctly identified "Python" as a Proper Noun (`NNP`), "is" as a verb (`VBZ`), "powerful" as an adjective (`JJ`), and "language" as a noun (`NN`).

### F. Word Frequency Count
**Theory:** Word frequency analysis counts how many times each distinct word appears in a text. This is a basic yet highly effective technique used in creating Bag-of-Words models, term frequency-inverse document frequency (TF-IDF) calculations, and identifying the main themes of a document.

* **Function Used:** `FreqDist(words)` creates a frequency distribution object from the tokenized list. The `.most_common()` method is then used to display the words and their occurrence counts, sorted in descending order of frequency.

---

## 4. Conclusion
Through this experiment, the foundational techniques of text preprocessing for Natural Language Processing were successfully implemented using Python and NLTK. I observed how raw text data is transformed into structured formats (tokens, lemmas, POS tags, and frequency distributions) making it suitable for feeding into machine learning models for deeper textual analysis.
