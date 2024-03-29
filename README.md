Object Oriented Programming Course
Homework - VideosDB

November 2020

Bianca Necula \
Faculty of Automatic Control and Computer Science \
325CA 

# Info
```bash
git clone https://github.com/BiancaNecula/VideosDB.git
```
https://ocw.cs.pub.ro/courses/poo-ca-cd/teme/tema \
This project is the implementation of an IMDB-like application written in Java, that provides information about movies and series. Users can receive personalized recommendations based on their preferences. \
The platform simulates actions that users can take on a movie viewing platform: ratings, movie viewing, searches, recommendations, etc.

# About the code

* test_db - contains the tests in JSON format
* src
   * checker - the checker's sources including the checkstyle necessary files
   * fileio - classes for parsing the input files, not to be modified
   * common, utils
        * contain utility classes with constants and static methods
   * actor
        * contains an enum for the types of awards an actor can have
        * you can add here your actor related classes
   * entertainment
        * contains an enum for the supported video genres
        * class for representing a Season of a tv show
        * you can add here your entertainment related classes
   * entities
        * contains classes for homework solving
* ref - tests output for reference
* result - tests output for this implementation

# Implementation

After parsing and storing input data, the Entities redistribute the input in the new created objects:

* User: new functionality like storing the given ratings
* Show: abstract class with new functionality to calculate the total duration of a show, total number of views and average rating.
    * Movie
    * Serial: using Season objects for duration, views and rating
* Actor
* Action: split in 3 actions
    * Commands: solving 3 types of commands (Favorite, View, Rating) which store the result of the action in the respective objects and gives output for success or failure
        * Favorite: adding video in favorite videos list
        * View: adding video in viewed list
        * Rating: give rating
    * Queries: solving 8 types of query with list output
    * Recommendations: solving 5 types of recommendations for users 
* Util: utility class with methods for queries
    * Average: returns a list with name of actors sorted by the number of ratings received for their movies
    * Awards: returns a list with actors which have all the awards mentioned in the query
    * Filter Description: returns a list with actors which have all the words mentioned in query in their description
    * Rating: returns a list of videos (shows or movies) sorted by rating
    * Favorite: returns a list of the most favorite videos (shows or movies) for users
    * Longest: returns a list of videos (shows or movies) sorted by duration
    * Most Viewed: returns a list of videos (shows or movies) sorted by the number of views
    * Number of ratings: returns a list with name of users sorted by the number of ratings given
    * Methods for finding users, shows and actors by name in lists
* UtilRecommendation: utility class with methods for recommendation
    * Standard: returns the first unseen video by user
    * Best unseen: returns the best unseen video by user (by rating)
    * Popular: for premium users, returns the first unseen video by user from the most popular genre
    * Favorite: for premium users, returns the most favorite video unseen by the user
    * Search: for premium users, returns a list with all the videos unseen by the user from a genre

# Testing

The Main class runs the checker.
Comparing ref files with result files.
