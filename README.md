# PRODIGY_GAI_03

**Markov Chain Text Generator**

This project is a simple Python implementation of a text generator using Markov chains. It analyzes a given input text and generates new text that mimics the style and structure of the original input using statistical word patterns.

**Key Concepts:**

Markov Chain:
A Markov chain is a probabilistic model where the next state (or word) depends only on the current state (or current word(s)). In this context, it predicts the next word based on the current word or a sequence of words (n-gram).

n-grams:
An n-gram is a contiguous sequence of n items (words) from a given text. For example, in the sentence "Artificial intelligence is powerful", the 2-grams are:

('Artificial', 'intelligence') → 'is'

('intelligence', 'is') → 'powerful'


**Main Components of the Code:**

1.build_markov_chain(text, n)
This function processes the input text to build a dictionary (the Markov chain) where:

-Keys are n-grams (tuples of n words).

-Values are lists of possible words that follow each n-gram.

-text: the input paragraph as a string.

-n: the size of the n-gram (e.g., 1 for unigram, 2 for bigram).

2.generate_text(markov_chain, n, length, start=None)
This function uses the Markov chain to generate new text.

-markov_chain: the dictionary created from the build function.

-n: n-gram size (must match what was used to build the chain).

-length: the desired number of words in the generated text.

-start: optional starting n-gram (as a tuple of words); if not provided or invalid, a random one is chosen.


**How It Works:**

-The program first lowers and splits the input text.

-It builds a dictionary that maps every sequence of n words to the list of words that follow them.

-It then randomly walks through this dictionary to generate new text by repeatedly choosing a word that likely follows the current n-gram.

-You can optionally provide a starting word/phrase, or let the program choose one at random.


**Example Use Case:**

You input a paragraph about artificial intelligence. The program analyzes the sequence of words and then generates new text like:

"Artificial intelligence is transforming the way we live and work it enables machines to learn from data and perform tasks that traditionally required human intelligence."

The generated text is unique and based on patterns found in the original input.
