# Movie Recommender

Our Book Recommendation System is an advanced platform that aims to enhance users' reading experiences by suggesting books that align with their preferences and interests. Through the utilization of sophisticated algorithms and data analysis techniques, our system provides personalized book recommendations
In today's vast world of literature, with countless books being published regularly, it can be challenging to discover titles that resonate with an individual's reading preferences. Our Book Recommendation System addresses this issue by employing a variety of techniques to curate a customized selection of books.

## Process
DATA - Find the relevant data through API, CSV etc
Preprocess - Check and clean the data
Model - Build a relevant model as per the data
Interface - Build an interface to present the results

### Finding the DATA options
Kaggle - CSV files 
Books are uniquely identified by their ISBN (International Standard Book Number), and their information includes content-based details such as Book-Title, Book-Author, Year-Of-Publication, and Publisher, which are obtained from Amazon Web Services. Additionally, the system provides URLs that link to cover images, available in three different sizes (Image-URL-S, Image-URL-M, Image-URL-L) - small, medium, and large. These URLs direct users to the corresponding book page on Amazon's website.

### Preprocessing the DATA
Missing Data - Check if there is any field with missing data
Relevant Columns - After the intial check, we decided to drop excess columns 
Duplicate Data - Check if there are duplicate fields
Formatting - Pull data from dictionaries and have all the data in the same format
Creating Tags - Concatenating the Overview, Genre, authors, themes

### Model Building
Popularity-Based Recommender System:
Merge ratings with book data based on the ISBN.
Calculate the number of ratings for each book.
Calculate the average rating for each book.
Merge the number of ratings and average ratings.
Filter popular books based on a minimum number of ratings (250) and sort by average rating.
Select relevant columns from the popular books dataframe.

Collaborative Filtering-Based Recommender System:
Identify users with a high number of ratings (more than 200).
Filter ratings for popular books.
Identify books with a high number of ratings (at least 50).
Filter ratings for famous books.
Create a pivot table of ratings with books as rows, users as columns, and ratings as values.
Calculate cosine similarity between items (books) based on the pivot table.

Define the recommend() function:
Given a book name, find the index of the book in the pivot table.
Find similar items (books) based on cosine similarity scores.
Retrieve relevant information (title, author, image URL) for the similar books.

![Jupyter Notebook](https://github.com/sam7jay/Final-Project/blob/main/photos/final1.png)

### Interface
Local Host - Using HTML, CSS, Bootstrap to create and customize localhost page
Data Dump - Used Pickle library to dump dataframe created to localhost page 
Top 50 - Create a page with the top 50 books, their authors and their rating.

![Home](https://github.com/sam7jay/Final-Project/blob/main/photos/final2.png)

![Recommender](https://github.com/sam7jay/Final-Project/blob/main/photos/final3.png)

![Please check your spelling or try another book](https://github.com/sam7jay/Final-Project/blob/main/photos/final4.png)

### CHALLENGES
Cleaning the data

Making a model

Visualization

Using new libraries and Programming languages for interface
