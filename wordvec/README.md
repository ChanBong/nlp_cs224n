## Wordvec

### Learning Goals

- Human language and word meaning
- Word2vec introduction
- Word2vec objective function gradients


### Summary

- Human language is complex
- What do we mean by the meaning of the word ? the idea that is represented by the word or the idea that the speaker want to express
- How do we get usable meaning in computers
    - Option : Wordnet
    - Not scalable, too many problems
- One hot encoding is also inefficient and it doesn't has any sense of similarity ingrained in it
- Idea of representing a word by its context : A word is known by the company it keeps
- Word Vectors
    - Every word is represented by a vector of dimension d {100-1000}
    - In a fixed window size we have a center word (c) and neighbouring words (n)
    - Use similarity of vectors to calculate the probability of n given c or vica versa
    - Keep adjusting these word vectors to maximize the probability
- Variants
    - Skip-grams (SG)
        - Predict context (“outside”) words (position independent) given center word
    - Continuous Bag of Words (CBOW)
        - Predict center word from (bag of) context words
    - Negative sampling


### Lectures & Readings

**Required:**

- [Stanford CS224N: NLP with Deep Learning | Winter 2019 | Lecture 1 – Introduction and Word Vectors](https://www.youtube.com/watch?v=8rXD5-xhemo&list=PLoROMvodv4rOhcuXMZkNm7j3fVwBBY42z)
- [Lecture Notes: Word Vectors I: Introduction, SVD and Word2Vec](http://web.stanford.edu/class/cs224n/readings/cs224n-2019-notes01-wordvecs1.pdf)

**Optional:**

- [Efficient Estimation of Word Representations in Vector Space](https://arxiv.org/pdf/1301.3781.pdf)
- [Distributed Representations of Words and Phrases and their Compositionality](https://proceedings.neurips.cc/paper/2013/file/9aa42b31882ec039965f3c4923ce901b-Paper.pdf)

### Exercises

- [Assignment 1 (Preview)](http://web.stanford.edu/class/cs224n/assignments/a1_preview/exploring_word_vectors.html)
    - [(Downloadable zip file)](http://web.stanford.edu/class/cs224n/assignments/a1.zip)
