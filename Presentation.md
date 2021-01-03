Data Science Capstone Final Report
========================================================
author: N. Hayashi
date: January 3, 2020
autosize: true

Predicting Next Word by using Ngrams and Katz Backoff Model

Project Goal and Requirements
========================================================

The goal in this project is to create a shiny app predicting the next word 
by a phrase that the user inputs from, for instance, a mobile text application. 
The requirements are that:
- The algorithm be based on principles of Natural Language Processing
- The size and runtime of the algorithm be reasonable
- The user interface be intuitive  
  
The training data provided from Swiftkey contains various texts in four languages from blogs, news and twitter. 
Our application uses the English dataset only. 


Apps and resources
========================================================

### [Shiny App](https://nobumasah5183.shinyapps.io/PredictNextWord/) 

### Resources
- [Data Science Capstone: Milestone report](https://rpubs.com/nobu5183/708037)  

- [Github repository for Final Report](https://github.com/NobumasaHayashi/DataScienceCapstone_FinalProject.git)

#### Useful videos about Natural Language Processing by Prof. Dan Jurafsky
- [N gram models](https://www.youtube.com/watch?v=Saq1QagC8KY)  
- [Katz Backoff](https://www.youtube.com/watch?v=naNezonMA7k)  
- [Good Turing Smoothing](https://www.youtube.com/watch?v=fhvDgKBZa1U)



Algorithm
========================================================
The algorithm used here is based on *N*-gram model, which predict the last word of an *N*-gram from previous *N-1* word sequence. *N*-gram model calculate the probabilities and find out the most probable next word. The major problem of this method is it cannot handle *N*-grams that are not seen in training corpus, which will has zero probability.  

There are many different methods to smooth the probability distribution. Here, we chose **Katz backoff method**, in combination with the Good-Turing discounting.  

- **Katz backoff method**:  
In this method, the probability of an *N*-gram with zero count is approximated by backing off to (*N-1*)-gram. The backoff will further continue until a word sequence preceding the the candidate word with non-zero count is encountered.


User Interface
========================================================
The user just types an English phrase, and then 5 next words predicted and a wordcloud of the next word candidates will be suggested. Wordcloud will help to understand how much the difference of the probability between the next word candidates.

![plot of chunk unnamed-chunk-1](./Interface.png)
