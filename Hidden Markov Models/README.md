#Vector-based Parts of Speech Tagging with HMM-Viterbi
## Overview
* Given a sequence of words, produces the POS tag sequence
* Universal tag set of 12 Parts of Speech - Noun, Pronoun, Verb, Adjective, Adverb, Adposition, Conjunction, Determiner, Cardinal Number, Particles, Foreigh Words(X), Punctuation(.)
* Dataset used: NLTK Brown Corpus
* 5-fold Cross Validation: Training data: 45872 and Test Data: 11468

## Implementation
* Generative and discriminative POS tagging
* Used probability value for paths and pointers to path of states(to backtrack best path)
* For each word in sentence, calculate path probability with each state in tags. Choose next state with which maximum probability occurs for the given word. Add the state to path pointer
* After all the probabilities are computed, find the end state for which probability is maximum, and corresponding path pointer would be the best POS tagged sequence

### Generative POS Tagging
Used Joint distribution P(t,w)

### Discriminative models
* Used Conditional probability P(w/t)
* If unknown word is encountered, it is tagged as ‘X’
 

## Results 


## Inference
* Generative models for POS tagging are computationally slow, as it tries to model the whole distribution
* Tag NOUN gets confused with VERB and Tag VERB gets confused with NOUN
   * Reason: Since there are many words which can act as both noun and verb, the above confusion is frequently seen
* Tag NOUN is confused with ADJ and vice-versa (above reason)
* Tag X is most confused with Tag NOUN
   * Reason: For words of training data not in dictionary, we are assigning equal probabilities to all tags for that word
   * As transition probability to noun gives maximum probability path for given previous states, Tag X is most confused with Tag NOUN 

