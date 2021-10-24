## Word Embeddings and GloVe

### Learning Goals

- Optimization Basics
- Intro to Gradiant Descent and SGD
- Global Vectors for Word Representation (GloVe)
- Intrinsic and extrinsic evaluations
- Effect of hyperparameters on analogy evaluation tasks
- Correlation of human judgment with word vector distances
- Dealing with ambiguity in word using contexts
- Window classification


### Summary

- We have looked at two classes of algorithms for learning word embeddings
- Statistical Ones : (LSA, HAL) : They levrage global statistical information effectively but can't capture a high-level meaning of words that could help in word analogy or similar tasks. Indicating a sub-optimal vector-space structure
- Iterative Ones : (Skip-gram and CBOW) : Shallow window-based. Learn word embeddings by making predictions in local context windows. Have the capacity to capture complex linguistic patterns beyond word similarity, but fail to make use of the global co-occurrence statistics
- So we try to use GloVe which consists of a weighted least squares model that trains on global word-word co-occurrence counts and thus makes efficient use of statistics
- Evaluation of Word Vectors :
    - Intrinsic
        - These subtasks are typically simple and fast to compute, allows to help understand the system used to generate the word vectors. An intrinsic evaluation should typically return number that indicates the performance of those word vectors on the evaluation subtask
        - Helps understand subsystem
        - Needs positive correlation with real task to determine usefulness
    - Extrensic
        - Is the evaluation on a real task
        - Can be slow to compute performance
        - Unclear if subsystem is the problem, other subsystems, or internal interactions
        - If replacing subsystem improves performance, the change is likely good
- Intrinsic Evaluation examples : Word vector analogies (Analogies of the form a:b::c:?) both semantic and syntactic, Analogy evaluation , Correlation with human judgemement (Humans rate the correlation and then that is compared to the models output)
- Observations on hyperparameters derived from intrinsic evaluation :
    - Performance is heavily dependent on the model used for word embedding : As skip-gram, CBOW, GloVe all uses different mechanism to capture the word meaning
    - Performace increases in proportion of corpus size
    - Performance is lower for extremely low dimentional word vectors : They don't have enough dimention to capture all the context that the word provides. E.g Nokia can be close to Samsung in one dimension as they are both electronics companies and it can also be close to Finland as it's the origin of the company. If you have less dimensions you can lose some of this meaning
    - A window size of around 8 works well
    - Skip-gram and GloVe are robust to higher dimension word embeddings over-fitting the data
- Extrinsic Tasks
    - Most NLP tasks can be thought of as classification tasks. NER, Sentiment analysis etc.
    - We need a decision boundary
    - Retraining word embeddings : Usually fine to leave it as such, but we can finetune. Be careful not to bias the boundary
    - Softmax classification and regularization
    - Window Classification
        - Natural languages tend to use the same word for very different meanings and we typically need to know the context of the word usage to discriminate between meanings
        - Use a word window as input



### Lectures & Readings

**Required:**

- [Stanford CS224N: NLP with Deep Learning | Winter 2019 | Lecture 2 – Word Vectors and Word Senses](https://www.youtube.com/watch?v=kEMJRjEdNzM&list=PLoROMvodv4rOhcuXMZkNm7j3fVwBBY42z&index=2)
- [Lecture Notes: Word Vectors II: GloVe, Evaluation and Training](http://web.stanford.edu/class/cs224n/readings/cs224n-2019-notes02-wordvecs2.pdf)

**Optional:**

- [Orignal GloVe paper](https://nlp.stanford.edu/pubs/glove.pdf)
- [Improving Distributional Similarity with Lessons Learned from Word Embeddings](https://aclanthology.org/Q15-1016/)
- [On the Dimensionality of Word Embedding](https://proceedings.neurips.cc/paper/2018/file/b534ba68236ba543ae44b22bd110a1d6-Paper.pdf)


### Exercises

- [Assignment 1 (Preview)](http://web.stanford.edu/class/cs224n/assignments/a1_preview/exploring_word_vectors.html)
    - [(Downloadable zip file)](http://web.stanford.edu/class/cs224n/assignments/a1.zip)
