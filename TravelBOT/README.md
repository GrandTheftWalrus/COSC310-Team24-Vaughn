## Team24-COSC310


Flight Booking Chatbot 

An application used to help a user find the perfect flight for them.
Built using html, CSS, Python and Flask.
Rasa and Spacy were used in order to improve bot accuracy and overall conversational flow.

The Rasa model allows the implementation of multiple story flows following intents created to predict user responses.

## Project Status
Assignment 2 milestone complete. The next step is to further test input and responses and implement an API to lookup and return actual data.

We are looking to increase the system's ability to recognize a particular intent by adding in more dynamic conversation variants.


## Project Screen Shots

[ PRETEND SCREEN SHOT IS HERE ]

[ PRETEND OTHER SCREEN SHOT IS HERE ]


## Installation and Setup Instructions

#### Example:  

Clone down this repository. You will need to install all libraries listed in requirements.txt

***Your system may require the python 3.8 version to run Rasa libraries***

Navigate to the TravelBot folder and confirm the virtual environment is running for that file. You will run:

Installation:

`pip3 install -U --user pip && pip3 install rasa`  

When this is complete, you will run:

'rasa data validate'

To confirm the files are in place and the model will load. Then begin to train the model on your local device by entering: 

'rasa train'

In the console... Once the model is trained (takes a few seconds!!!) you will see a file saved response in your terminal or command line and thus can enter:

'rasa run -m models --enable-api'

Proceed to navigate to the main directory in your terminal window and proceed to enter:

'python app.py'

If Flask server needed:

    Export Flask Server. Syntax depends on terminal used. See:  
    `https://flask.palletsprojects.com/en/2.0.x/quickstart/`  

    To Start Flask Server:
    `flask run`  

You should then be able to view the chat interface by using this URL:
To View App:

`http://127.0.0.1:5000/`  

# TravelBOT

Travel bot stores all the required conversational elements. It uses a RASA model to implement the chat flow and allows the system to deduce intentions of the users statements. The system uses a neural network to predict the possible meaning behind the user's response.
### nlu.yml:  
  The nlu document is responsible for holding all the possible statements a user could give for the following intent. We created the intents to follow the story line we are trying to achieve with the travel bot. 
  
  The following are called entities [00-09-22](date) where the items within the square brackets is the value and the round brackets hold the entity name. We can use these to capture key elements within a conversation to be saved for future API call.


### rules.yml: 

  rules are used in the RASA model to structure the outcomes of particular responses. The rules are mean't to help the model better predict the concrete actions that have to happen within the conversation dialogue.



### stories.yml:  

  stories are a way for the chat bot to know the ways the conversation could move in while still being within the designers intended primary task. We have implemented single large story with 25 turns that we will in future versions build out to include different paths.

### domain.yml:

The domain.yml file is responsible for holding all the conversation elements that the user and bot may produce.

The intents are described in the nlu.yml file, and are the possible user responses categorized by intent.

Entities are elements within a user's response which the system can grab and subsequently store within the slots section.

The slots can be used to store user data across sessions or can be set to wipe clean each session
We currently are unable to implement this capture feature as the time for the assignment was limited
look back at version 2 for improvements to the depth of conversation entity implementation. 

Actions are the system's responses to the user's intents

Responses define the particular text response given by the bot after each action call