# CloudComputing

RECOMMENDATION ENGINE

THE PROPOSAL- Why Recommendation Important?

In present generation of Computing revolution, recommendation systems are integral part of any intelligent information systems. e.g. Search engines (Google), Netflix, Amazon, YouTube and so on, recommends the article or entities which might interest users. For a system to be intelligent, it needs have informative data about user and about the entities he was interested in. This proposal, we are planning to develop a Book recommendation engine (stand-alone) which is used to recommend books using the User profile and User rating details. The rating system will be designed with three recommendation algorithms, 1. Collaborative based, 2. Content based and 3. User demographic profile (User location and age).
THE IMPLEMENTATION

The Collaborative based Recommendations:

This is basically build based on the collaboration of different user’s contribution on a book. The parameter which will be taken into consideration is the different user’s rating.

1. We need to group all the books each user has rated for all the users and sort descending order of the rating and ignoring the low rating book that the user has.

2. Now, we get ordered pairs of interest for books each user has. Now, we can drop the user information from the pairing.

3. Then, we need to calculate the similarity between every book with every other book which are rated by the same user.

4. Finally, we need to combine the similarity score we calculated with for each book with other book we have calculated in the previous step.

5. Implementation will be in Hadoop MapReduce. Programming language will be Java.

The Content based Recommendations:

Content based method are build using the user profile and item profile. The possible candidate parameter which can be used for this method is the used Id and age.

1. We need to segregate the data with User’s age and list of books/authors/publisher, certain age group has read.

2. Then, we need to form a vector representation with age and book as labels.

3. Using a SVM or Naïve Bayes model, we need to train this model using this vector data and label. (Note, we are going to use the adaptive model approach where the system trains the model with 70% training data and tests the model with remaining 30% data, whichever model has better efficiency, it will be used for classification)

4. Now, predict the book to be recommended based on the user’s age using the model we trained in the previous step.

5. Implementation will be using Hadoop Spark has this has the iterative machine learning computation. Programming language will be Python

The Recommendations filtering based on Demographic data:

Now, we have all the data grouped and ready for clustering based on location or country the user belongs to. We are using the unsupervised learning algorithm K-Means clustering for clustering the data based on the Country. We can even include age or any other user information to cluster data. After clustering, we will display the recommendations which falls close to his country cluster.
We will be implementing this using the Hadoop Spark, has this has got the iterative computation. Programming language will be Python

DATASET:

We are using the Book-Crossing Dataset from the link
http://www2.informatik.uni-freiburg.de/~cziegler/BX/
Description: The data is in the csv format, which has three files. Mainly

1. BX-Users.csv, which has the user information like UsedID, Location and age attributes. Roughly has 278858 user records.

2. BX-Books.csv, which has the ISBN, Book-Title, Book-Author, Year-Of-Publication, Publisher, Image-URL-S, Image-URL-M, Image-URL-L attributes. Roughly has 271380 records.

3. BX-Book-Ratings.csv, User-ID, ISBN, Book-Rating. Roughly has 1048576 records.
The BX-Books.csv and BX-Users.csv will be used for Content based Recommendations. BX-Book-Ratings.csv will be used for Collaborative based Recommendations and BX-Users.csv will be used for filtering based on Demographic

Final output:

We anticipate to have all the three filters work and final recommendation will be the output from filtering based on Demographic. The recommendation will be Content + Demographic which
is suitable for new users or Collaborative + Demographic which is suitable for users who is in long run. We are foreseeing to show the output through a webpage/UI/HTML for better visualization.

Programming Languages

Mapreduce- JAVA
SPARK & Machine Learning – Python

Environments –
Cloudera- Development
Testing – UNCC Hadoop DSBA cluster
Implementation and Demo – Amazon AWS Cluster.

WHAT YOU WILL DEFINITELY ACCOMPLISH

One of the recommendation model discussed above, like Content + Demographic or Collaborative + Demographic will be implemented from the scratch by the team.

WHAT YOU ARE LIKELY TO ACCOMPLISH

Implementing both Content + Demographic and Collaborative + Demographic algorithms combination for efficient recommender system.

WHAT YOU WOULD IDEALLY LIKE TO ACCOMPLISH

A responsive UI for the system and showing the recommendation in a webpage and storing any new user data in the database for adding him to the existing dataset we have and include his data for further analysis and recommendation computation.
