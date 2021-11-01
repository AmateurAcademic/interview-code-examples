# interview-code-examples
Notebooks with example code explained for interviews. 

I have often found when I am doing a tech interview as a canidate the following problems:
* The interviewer asks very specific questions about the tasks I did for companies I worked for. These questions can often times be too specific and answering their questions could breach an NDA.
* I honestly cannot remember exactly how I did something AI related from several years ago in great detail

And as someone who has also been a hiring manager, I am tasked to interview canidates, including tech interviews.

I thought it might be great to come up with some small challenges we could go through to aid canidates and interviewers alike. 

##  NLU Intent classifiers
Strangely I couldn't find an example of building a basic intent matcher used in an NLU engine for voice assistants, where utterances (ie user commands/questions) are classified by their intent category. So I decided to make a simple one for everyone out there. 
`NLU_Intent_matching.ipynb` explores the idea of intent matching on utterances and entity extraction. Using the [NLU Evaluation Dataset](https://github.com/xliuhw/NLU-Evaluation-Data) as a bases of data, both a word embedding approach (using Word2Vec) and a TFIDF approach are explored using the following algorithms to train intent classifiers:
* [(Gaussian) Naive Bayes Classifier](https://scikit-learn.org/stable/modules/generated/sklearn.naive_bayes.GaussianNB.html)
* [Decision Tree Classifier](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html)
* [AdaBoost Classifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.AdaBoostClassifier.html)
* [K-Nearest Neighbors Classifier](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html)
* [Random Forest Classifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html)
* [Support Vector Machine Classifier](https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html)

More may be added in the future. 

### Reasons these classifiers were choosen
* Using algorithms that are easy to find in other langauges (not just Python)
* Computationally inexpensive (they could run in real time on a phone, for example)
* Not just inference could be run on low-power device, training could also be performed (TinyML), therefore a user could always add/edit the data to create models that work better for them

### Good questions for NLU intent classifiers
* Why does Word2Vec perform much worse than TFIDF?
* Is there any other word embedding based approach that might work better? (how costly is it to run inference on?)
* Would TFIDF out-perform simple bag of words?
* Is f1 a good measure of performance?
* How would one fine tune the models and what kind of expectations are there for performance gains?
* How could adding in a entity tagger boost intent classification?
* Are there any other performance hacks?


### Entity extraction (Named Entity Recognition)
This notebook uses conditional random fields (CRFs) for entity extraction.


And there is more to come, whenever I find time. ;)
