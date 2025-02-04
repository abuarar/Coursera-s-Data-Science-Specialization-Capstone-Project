Coursera's Data Science Specialization Capstone Project
========================================================
author: "Mohammed Abuarar"
date: "March 12, 2019"
autosize: true

This is an R-representation about Capstone Project [shiny application](https://abuarar.shinyapps.io/Coursera_Data_Science_Capstone_Project/).</br>
The main target of this capstone project is to practice the knowledge and skills we've learned through previous 9 courses in the specialization given by [Johns Hopkins University](https://www.jhu.edu/) with a real life task.
In cooperation with [SwiftKey](https://www.microsoft.com/en-us/swiftkey/about-us), the capstone project introduced a challenge to make a word prediction algorithm using text data from a corpus called HC Corpora, and by applying data science in the area of natural language processing.

Tasks to be accomplished and problems to be solved:
========================================================

Getting and cleaning the data was the first task, and  mainly accomplished by tidytext package, which did also tokenizing text into ngrams: Quadgram, Trigram and Bigram which is natural language processing commonly used method.

Exploratory analysis showed that the text has a statistical distribution that comes with very long tails (many words that occur rarely) and (fewer words that occur frequently) which is a common criterion in text data. This criterion will help to represent data fairly by taking a small sample compared to the the very large corpus, and this step will solve the performance vs accuracy tradeoff to achieve a good mix of both (higher performance with an acceptable accuracy) which will make the application speed practical on mobile smart phones.

Prediction algorithm:
========================================================

In my prediction model I used katz back-off smoothing technique to include the many unseen ngrams by reverting back to (n-1)grams and redistributing probabilities from low frequency ngrams to unseen (n-1)grams, so the algorithm will work in the following way:

* If the input text last 3-words match starting 3-words within Quadgram, the 4th-word is the prediction, (QuadgramBackoff will include unseen 4th-word as well).
* If above is not, and only the last 2-words match starting 2-words within Trigram, the 3rd-word is the prediction, (TrigramBackoff will include unseen 3rd-word as well).
* If above is not, and only the last word match starting 1-word within Bigram, the 2nd-word is the prediction.

Application Quick Tutorial:
========================================================

1. Your text input which can be entered via keyboard
2. This is both a **Display** for most 3 probable predicted word, and also an interactive **Clickable Button** to add predicted text once you click it to already entered previous text (**same as in swiftkey application**).
3. This is the total text you've entered so far.
4. This is a data table of the predicted next words, with Ngram used and Probability 

![](ApplicationTutorial.png)

References:
========================================================

* Shiny application to predict next word can be found in this link: [https://abuarar.shinyapps.io/Coursera_Data_Science_Capstone_Project/](https://abuarar.shinyapps.io/Coursera_Data_Science_Capstone_Project/)

* All work related to this project can be found in this Github repository [https://github.com/abuarar/Coursera-Data-Science-Specialization-Capstone-Project](https://github.com/abuarar/Coursera-Data-Science-Specialization-Capstone-Project)

* This presentation can be found in this link [https://rpubs.com/abuarar/DSCPR](https://rpubs.com/abuarar/DSCPR) 
