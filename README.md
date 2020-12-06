# ADM_HW_3
Mert YILDIZ / Nello Castaldo / Luca Avitabile

In this homework we have solved 4 questions of the Algorithmic Methods of Data Mining course homework. The goal of the homework is to build a search engine over the "best books ever" list of GoodReads.

## 1. Data collection

In the first question we start from the list of books to include in our corpus of documents. In particular, we focus on the best books ever list. From this list we want to collect the url associated to each book in the list. As you realize, the list is long and splitted in many pages. Therefore, we have retrieved only the urls of the books listed in the first 300 pages. Once we got all the urls in the first 300 pages of the list, we:
      Downloaded the html corresponding to each of the collected urls.
      After we collected a single page, we immediatly saved its html in a file. In this way, if our program stops, for any reason, we will not loose the data collected up to the stopping point.
      Organize the entire set of downloaded html pages into folders. Each folder will contain the htmls of the books in page 1, page 2, ... of the list of books.

At this point, we have all the html documents about the books of interest and that we can start to extract the books informations. The list of information we desire for each book are the following:

Title (to save as bookTitle)
Series (to save as bookSeries)
Author(s), the first box in the picture below (to save as bookAuthors)
Ratings, average stars (to save as ratingValue)
Number of givent ratings (to save as ratingCount)
Number of reviews (to save as reviewCount)
The entire plot (to save as Plot)
Number of pages (to save as NumberofPages)
Published (Publishing Date)
Characters
Setting
Url

For each book, we created an article_i.tsv file.

## 2. Search Engine
Now, we want to create two different Search Engines that, given as input a query, return the books that match the query.
First, we have pre-processed all the information collected for each book by

Removing stopwords
Removing punctuation
Stemming
and some more noise that we thought it's not needed

For this purpose, we used the nltk library.

For the first search engine we have created inverted index and found the tfidf and calculated cosine similarity score to retun the best matches with the given query. We have solve this question with manual calculations and also we have provide a second solution which finds the best match by the solution we have created with built-in functions.

## 3. Define a new score!

In this question we have decide to ask to user the query, minimum rating and minimum number of rating that he/she wants. After that we have filtered the books with minimum rating and minimum number of ratings. Additionally we have defined a new score which is the nomalized multiplication of rating and cosine similarity between the books' plot and given query. Finally we have returned the 10 books with the highest new score.

## 4. Make a nice visualization!

Since this question was not mandatory we choose to not solve it. 

## 5. Algorithmic Question

We are given a string written in english capital letters, for example S="CADFECEILGJHABNOPSTIRYOEABILCNR." We are asked to find the maximum length of a subsequence of characters that is in alfabetical order. For example, here a subsequence of characters in alphabetical order is the "ACEGJSTY": "CADFECEILGJHABNOFPSTIRYOEABILCNR." Among all the possible such sequences, we are asked to find the one that is the longest.

For this question we have wrote down a recursive and a dynamic algorithm. The execution time of the recursive algorithm is exponential while the execution time of the dynamic programing is O(nm).



