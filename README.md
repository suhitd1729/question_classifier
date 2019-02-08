# Question_classifier

### Agenda : To create a classifier that can identify whether or not a provided series of words is a question

### Approaches :

#### Two approaches have been followed : 

**Approach 1**

The first approach is more naive. It just checks for certain words such as how , where, what , when etc. 
(will refer to these as q_words from here on) in the text provided. 

Normally, I would have only checked if any of the sentences provided begins with one of the q_words, but then,
I would miss out on sentences which might be a question where the q_words occur in the middle.

Since my aim is to build an adequate Question identifier model , I would rather have a few False Positives than miss 
out on a Inquiry statement that might be relevant.

The analogy is similar to Spam Filtering. We would prefer having a Spam labelled as Non-Spam than have an important 
email labelled as a Spam and miss out on it. 

The output is saved as **output.txt**

**Approach 2**

Using **nps_chat corpus** which comprises of sample chats and their corresponding dialogue act types. 

There are 15 dialogue act types, such as "Statement," "Emotion," "ynQuestion" etc. The nps_chat corpus can be obtained 
from the **nltk** library.

Amongst the dialogue act types, the ones that are of type "ynQuestion" and "whQuestion", implying a question type
are classified as 1 and the rest as 0. This would serve as a reference source (training data)

Using this training data , a Naive Bayes model is built which is used to test on the sample data provided. 

The output is saved as **output_nltk.txt**

-- Suhit
