# Book-Recommendation-System
Haoyin Xu1*, Jo-fan Chien*, Dawei Li*, and Qin Li*<br>
Introduction and hypotheses<br>
While the emergence of the internet provided access to tremendous digital information, it also led to
a potential challenge to dierentiate signicant information from trivial ones. Internet users often found
themselves with too many choices yet with insucient information to decide. Search engines such as Google
have partially solved this dilemma by facilitating the process of accessing relevant information, though lacking
personalization. One example of this is when a person looks for some novels or movies, they could search
online for recent publications but might not quickly nd one that interests them.
In this project, we aimed at constructing a recommendation system that specically helps a reader narrow
down the selections to a few new books based on the prediction of their preference. A recommendation system
is an information ltering system that nds the most vital information pieces according to the user's prole.
This will be a benecial system for both users and the service providers because while it can reduce the cost
of nding an ideal item, it could also improve the quality and eciency at the server end [1].
In this study, we showed the result of both collaborative ltering method and content-based ltering
method. For collaborative ltering, we compared the non-parametric memory-based model with the para-
metric dimensionality reduction model in their performance. We hypothesized that the dimensionality re-
duction method could provide a slightly better result because only the most essential features were selected
to produce the prediction. We also improved our models with the consideration of bias. In addition, we
discussed a design of a hybrid recommendation system that best utilizes available information and best suits
the user's needs.

Method<br>
Data Preprocessing<br>
After obtaining the dataset from Kaggle [2], we cleaned the data by dropping the irrelevant columns (e.g.
the link to the cover picture). To ensure statistical signicance, we drop any books that have less than 50
ratings and users who rated less than 10 books. The nal dataset is with 10,491 users, 2,125 books and
totally 1,149,780 ratings. For content-based ltering purposes, we also extract the titles from the dataset of
book information.
Collaborative ltering<br>
Collaborative ltering uses similar preferences towards items, specically books, with specic features to
provide recommendations. In other words, the system provides recommendations to the users solely based
on user-book interactions, specically ratings, instead of the content of the books. Given the user-book
rating matrix Rmn, with m rows of individuals and n columns of dierent books, ratings can be used for
recommendation in two ways: recommend high-rating books of similar users(rows are similar: user similarity)
or recommend books similar to the preferred ones(columns are similar: book similarity). Surprise [4] package
in python was used to build the collaborative ltering system.
