# NLP (Natural Language Processing):

Natural language processing (NLP) is an important research area in artificial intelligence
NLP is a field of linguistics and machine learning focused on understanding everything related to human language. The aim of NLP task is not only to understand single words individually, but to be able to understand the context of those words

## Language Modeling:

A language model in NLP is a probabilistic statistical model that determines the probability of a given sequence of words occurring in a sentence based on the previous words. It helps to predict which word is more likely to appear next in the sentence

### Types of Language Models:
•	Statistical Language Model

•	Neural language models

### Statistical language Model:
Statistical models include the development of probabilistic models that are able to predict the next word in the sequence, given the words that precede it
### Neural language Model:
Neural language models overcome the shortcomings of classical models such as n-gram and are used for complex tasks such as speech recognition or machine translation.
### N-Gram language model:
An N-gram language model predicts the probability of a given N-gram within any sequence of words in the language. A good N-gram model can predict the next word in the sentence that is based on the value of p(w|h)

**For example:** 
N gram such as unigram (“we”,”are”,”students”,”of”,”Abhinav”,”sir”)

Or Bigram(“we are”,”are students”,”students of”,”of Abhinav”,”Abhinav sir”)

P(w∣h)=C(hw)/C(h)

**Chain rule:**

P(w1:n)=P(w1)P(w2∣w1)P(w3∣w1:2)...P(wn∣w1:n−1)=∏k=1nP(wk∣w1:k−1)

![n gram img](https://user-images.githubusercontent.com/84316456/203908292-b9b883ad-cde8-4450-a789-1f7fc0be2f8f.gif)

### **Importing libraries:**

![libraries](https://user-images.githubusercontent.com/84316456/203908463-3e5b66da-213c-42da-b220-4c7b3f5a9e57.jpg)

## **DATA:**

### **IMDB reviews file**

![input](https://user-images.githubusercontent.com/84316456/203908671-c30712f1-ce47-4bae-b958-eaf85d1fecbf.jpg)

List created as **reviews** and appending all the data from the file into the reviews list

![list data](https://user-images.githubusercontent.com/84316456/203908787-181ea638-ca10-4cfa-84df-7ca8e2e4f483.jpg)

List created as **data** and append the data without spaces and if it contain any empty sentences it removes all the spaces and append it to the data list.
And returning the length of the data list.

![reg](https://user-images.githubusercontent.com/84316456/203908882-cab0a54d-7cd2-445b-a144-9c8386714857.jpg)

Using **tagremover** function regular expressions removing all the special symbols tags and operators from the data file.
It takes in the sentence and returns the clean sentence.

![n gram](https://user-images.githubusercontent.com/84316456/203909040-7c03d742-6ea4-41b6-a3be-978f3b50716c.jpg)

### **Class N-Gram:**
**gramDiv:** function 

gram_count dictionary calculates the numerator of the N gram 

hist_count dictionary calculates the denominator of the N gram

If the count of the n value is given it returns the same probability of the words, as the value of 1 returns unigrams

List_of_ngrams list is appended with the with the words according to the count 

Example:

Unigram [“we”,”are”,”students”,”of”,”Abhinav”,”sir”]

If the **“n”** is greater than 1 

The sentence is appended with start of the sentence with symbol

and end of the sentence with symbol

List_of_ngrams list is appended with the with the words according to the count 

Example:

Bigram[“we are”,”are students”,”students of”,”of Abhinav”,”Abhinav sir”]

Trigram[“we are students”,”are students of”,”students of Abhinav”,”of Abhinav sir”]

Functions returns the gram_count,hist_count,list_of_ngrams,sent_data

![test data](https://user-images.githubusercontent.com/84316456/203909483-a233248a-6ab4-4d68-a9f7-15c66440af12.jpg)

### **adder** 

function takes in the file as an input and append it to the test_data list as sentences

![prob for test](https://user-images.githubusercontent.com/84316456/203909569-85377bab-13e2-4d0e-b1ad-f73448d5a03c.jpg)

Finding the probabilities of the test sentence 

The function ### **prob_for_test_sent**

The sentence is also appended with the start of the sentence with symbol and end of the sentence with symbol 

returning the list of the n grams and the sentences list

![perplexity](https://user-images.githubusercontent.com/84316456/203909742-19cd81bd-f88e-4b68-881e-3ea3ba4abec0.jpg)

### **Calculating perplexity :**

Perplexity is a metric used to find the best ngram model for a corpus. If we want to know the perplexity of the entire corpus C that contains m sentences and N words. 

The perplexity of the corpus is given by

![perploxity1](https://user-images.githubusercontent.com/84316456/203918580-de2dc66b-9e58-47ae-9212-8b55b5b68431.png)

![perplexity2](https://user-images.githubusercontent.com/84316456/203918743-363f14e9-2ec1-428e-9906-9f38111eed5b.png)

![perplexity3](https://user-images.githubusercontent.com/84316456/203918998-7c94a4a6-1c19-4e6d-a1ad-6c5c21d35c81.png)

In the function perplexity_of_test_sent, I’ve taken list of ngrams for a test sentence,vocabulary size  as parameters. 

I took the frequency of ngrams of that sentence and calculated perplexity as per formulae. 

When unseen data comes we have to do smoothing i.e., add-one smoothing which adds 1 to numerator and  vocabulary size to denominator.
