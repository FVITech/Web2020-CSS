# Front End Development Quiz App Project

## 00: Intro
The purpose of this project is to develop an application that loads a quiz from a restful interface and checks the user's answers against the API as well.

Learning Outcomes:
- Practice AJAX requests and responses
- Receive a complex JSON structure from a web server (an array of JS objects)
- Iterate through object arrays and build DOM elements based on the data within those objects
- Practice firing multiple asynchronous requests and handling the responses for them

## 01: The API

#### Endpoint to get all questions
The Api endpoint for this project is located at 

<code>http://fvi-grad.com:4004/quiz</code>

A GET request to this endpoint will return a JSON object which is an array containing five objects with this structure:

<code>
{ 
    id: 4,
    questionText: "What's your name?",
    answers: ["Donald", "Mickey", "Trumperator"]
}
</code>

All questions are multiple choice and the 'answers' attribute of the object represents an array containing the possible choices.

#### Endpoint to check answers

This endpoint allows you to retrieve the correct answer to a question based on the question id. A GET request to this array will return the actual value of the correct answer for the question. For example, if your question is "Who was the first president of the US?" and this question's id is 66555, then a GET request to the following uri:

<code>
http://fvi-grad.com:4004/quiz-get-answer/66555
</code>

Will produce the value "George Washington". You can then use this value to compare to whatever the user's answer was. Please note that the value "George Washington" is served by the API with a response type of "application/json" and therefore when the browser receives it it has quotes around it. You must use the Javascript eval function in order to evaluate the string and put its value into a new variable. You may also use the substring method to get rid of the first and last character (the quotes).

You are free to use either radio buttons for your multiple choice or structure your quiz app as a short answer quiz.
