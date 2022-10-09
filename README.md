# Quizzy App

by Katriina Kalliokoski  
9 Oct 2022

## Description


### Application functionality
--------

Quizzy App is a Dart/Flutter web application that provides the user with quiz questions from a variety of topics. The topics and questions are fetched using the API at [https://dad-quiz-api.deno.dev]( https://dad-quiz-api.deno.dev).

The user picks a topic card from the list displayed on the home page. Then, they are shown a random question on that topic - with an image, if applicable - and a list of response option buttons, as well as a button that will take the user back to select another topic. Once the user clicks an option, another API request confirms whether the response was correct or incorrect and the result is shown on a result page with the 'Back to topics' button and a button to fetch a new question. Starting from the first response, the user can see their statistics for the number of answered questions and correct answers in the right corner of the top app bar. The statistics are shown on the topics/home page and the result pages after each question.

Quizzy App has a responsive layout with two different visual outlooks: for a display of 600px or more, the look is defined by a dark blue top bar and a light blue bakcground color. For the more narrow displays, the top bar is green-colored and the background is light yellow.

### Deployment
--------

Quizzy App is deployed and can be accessed at  
[https://katkalliok.github.io/quizzy-app/](https://katkalliok.github.io/quizzy-app/).

## Development Process
  
### Key Challenges
---------

Here are some of the most memorable and frustrating challenges I faced during the development process:

* **Processing complex API responses.** When the type is technically just dynamic, it becomes very restricted what you can do with the response data code-wise. Especially when fetching the topics, the response is decodes into a list of maps that needs a lot of work on code even after the API request. Here, I had to go for a questionable choice of putting a good deal of functionality into the Service class already - but, it works.
* **Updating state along with the API call.** Based on the course conversation, this was a problem that several classmates of mine had as well. While I did not perfectly understand the reason why you cannot update the system state via providers within the widget build method, I was happy to use the tip of putting the update into the widget init instead.
* **Alignments, paddings, and centering!** Getting the statistics to sit in a nice place on the top bar was particularly curious (at least with the Debug tag spicing up the upper corner). Also, the Center widget seems to have a different opinion about the horizontal center for different children - I was not able to figure this out and a careful eye might notice this as they review the Quizzy App pages.
* **Calling for a theme for the MaterialApp when a Go Router is in use.** This is another challenge I could not find a solution for just yet. In the course materials, themes were gloablly provided through the MaterialApp initiation in main. With the Go Router adding call, I did not understand how to implement this. After a few confused approaches and attempts, I ended up implementing the responsive layouts through each screen's build call.

### Key Learning Moments
--------

As per usual, the aforementioned challenges of this project mostly felt rather disappointing and exhausting than educating.  
Still, some particularly delightful learning moments happened, most memorably:

* **Having to also parse string parameters from router paths.** This was a small yet crucial detail that I had not thought about.
* **How easy it was to create the image from URL!**
