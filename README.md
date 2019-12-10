# Email_spam_filtering_with_NLP

 Now we will do text preprocessing since main issue for our data is that it is in text format or string  we need numerical data or numerical feature vector in order to perform the classification tasks.
 There are many actual methods where u can convert a corpus of strings to vector format.
 
 The simplest approach is bag of words where each unique word in the text will be represented by one number
 Now here we will write a function that will split a message into its individual words and return a list

 Takes in a string of text, then performs the following:
    1. Remove all punctuation
    2. Remove all stopwords
    3. Returns a list of the cleaned text
    
 we are going to tokenize these messages and tokenization is just a term use to describe the process what we just did
 converting a normal text string into list of tokens and tokens are just words we actually want(clean version of words or important words)
 
 Vectorization

 Currently, we have the messages as lists of tokens (also known as lemmas) and now we need to convert each of those messages into a vector the SciKit Learn's algorithm models can work with.
 Now we'll convert each message, represented as a list of tokens (lemmas) above, into a vector that machine learning models can understand.

 We'll do that in three steps using the bag-of-words model:

 1. Count how many times does a word occur in each message (Known as term frequency)
 2. Weigh the counts, so that frequent tokens get lower weight (inverse document frequency)
 3. Normalize the vectors to unit length, to abstract from the original text length (L2 norm)
 
 After the counting, the term weighting and normalization can be done with TF-IDF, using scikit-learn's TfidfTransformer.

So what is TF-IDF?
 TF-IDF stands for term frequency-inverse document frequency, and the tf-idf weight is a weight often used in information 
retrieval and text mining. This weight is a statistical measure used to evaluate how important a word is to a document in
a collection or corpus. The importance increases proportionally to the number of times a word appears in the document but 
 is offset by the frequency of the word in the corpus. Variations of the tf-idf weighting scheme are often used by search
 engines as a central tool in scoring and ranking a document's relevance given a user query.

 Training a model
 With messages represented as vectors, we can finally train our spam/ham classifier. 
 Now we can actually use almost any sort of classification algorithms. For a variety of reasons, the Naive Bayes classifier algorithm is a good choice.
 We'll be using scikit-learn here, choosing the Naive Bayes classifier to start with:
