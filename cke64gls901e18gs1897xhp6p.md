## CREATING YOUR VIRTUAL ASSISTANT WITH PYTHON

Why undergo the stress of typing when you can ask a machine to execute the task?



![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1598106002999/UrdcbGfx0.png)

Your gadgets - mobile devices, personal computers et al- are at your disposal and they can do so much more than texting or making calls (I believe you know this already). 

Yeah, you've got Siri, Google Assistant, Bixby, Alexa, and the like to save you the stress but come on... You are a developer, **you build things!** By now, you should be thinking of how to create your personal assistant that acts, thinks, and responds the way you want it to. The already-built assistants are fantastic, no doubt about that; but do you derive the maximum satisfaction from something not bespoke, not exactly made for you- **JUST YOU**?

If you are thinking what I am thinking, then, it's time to get started! 


First of all, I need you to picture what you want your personal assistant to look like (if it were to be human). Now, imagine the many ways it can serve you and deliver services to you. Finally, think of a name for the assistant - a beautiful name in fact.

Now, it's time to build your virtual assistant. Whooo!!!

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1598121103384/TXpcETQWJ.png)


**WHAT ARE VIRTUAL ASSISTANTS?**

An artificial intelligence assistant is a software agent that can perform tasks or services for an individual based on commands and questions. They have the ability to read information ranging from stock predictions, weather conditions, stock prices, schedules and so.

It is also referred to as an application program that understands natural language voice commands and completes various designated tasks for the user or operator. Virtual assistants can perform tasks ranging from simple to complex ones including home controlling, playing songs, reading the news, telling jokes, rapping, just name it.


**STEPS INVOLVED IN BUILDING A VIRTUAL ASSISTANT**

**Step 1: Import the required modules into the workspace**

For a start, we need to import three(3) important modules into our workspace: 

a. *pyttsx3*: A basic library we need to import into our workspace is the *pyttsx3* module. **pyttsx3 is a text-to-speech conversion library in Python.** You can read more about this library [here](https://pypi.org/project/pyttsx3/).

b. *datetime* function: The datetime module supplies classes for manipulating dates and times. The documentation can be found [right here](https://docs.python.org/3/library/datetime.html).  

c. **SpeechRecognition**: This is a library for performing speech recognition, with support for several engines and APIs, online and offline. Read more [here](https://pypi.org/project/SpeechRecognition/) 


Before you import these modules, you must have it installed on your computer. There are two ways to install it:
 
 1. **Virtual Environment:** If you are using a virtual environment such as **Pycharm** or **Anaconda**, you can install it using: *`conda install` [insert the library to be installed]* (for Anaconda) or install it under the Python Interpreter for the project under the **SETTINGS TAB** (for Pycharm).

2. **Terminal:** To directly install it on your computer, you can install it on the Command Prompt (cmd) using the *`pip install` [insert the library to be installed]* command. Ensure to install it to the right PATH where your Python application is installed on your computer.

**KINDLY NOTE THAT:** We would be importing other important modules in subsequent steps and the aforementioned methods are still applicable.


**Step 2: Initialize the Modules and Create a Basic Function **

Now that we have our foundational libraries installed, we can now go ahead and write a basic function to hear what our new *baby* sounds like. 


```
import pyttsx3

import datetime # this function is to enable our virtual assistant to get us the date and time which we want

import speech_recognition as sr

engine = pyttsx3.init() #line 1

engine.setProperty('rate', 150) #line 2

engine.setProperty('volume', 0.9) #line 3

voices = engine.getProperty('voices') #line 4

engine.setProperty('voice', voices[1].id) #line 5

engine.say('Hello Mom, how are you doing?') # line 6

engine.runAndWait() #line 7
``` 
I have commented some of the codes using ***lines 1 - 7***. I would love to explain each line of code: 

#line 1 - On this line, we are performing a **one-time initialization** of the text-to-speech function which we earlier installed and imported.

#line 2 - This function `Property(rate)` helps us to set the speed at which our assistants would speak when we assign sentences or words.

#line 3 - Here, we are including an additional setting - `volume`- which obviously sets how audible our virtual assistant would be.

#line 4 - As I said earlier, you should picture the kind of assistant you want, right? So, with this line, we are drawing from the `getProperty` function the `voice` feature which enables us to set a male or female voice for our assistant.

#line 5 - After importing the `voice` feature, we can now select the voice which we want using the number [0]-Male or [1]-Female. 

#line 6 - Now, we can tell our virtual assistant something to say. To do this, we need to pass a text which can be converted to speech. The `say` function enables us to do this. 

#line 7 - Remember that we assigned our text-to-speech library to the variable - engine- when we initialized it? So, this line is where we instruct our assistant to ***speak***. As humans, we observe certain punctuations when we speak and this requires us to usually pause at certain intervals. This is the only way our sentences can make sense to whoever is listening. In the same vein, similar structures should apply to our assistant. After converting a text to speech, we need our assistant to take short pauses before converting the next text - a virtual assistant is a machine but we do not want it to sound like one, right? 

That is why we have used the `runAndWait` function in #line 7.

You can now run this function and hear your assistant convert the bracketed texts in #line 6. You can always change this based on your discretion.


**Step 3: Define New Functions**

We now know what our assistant sounds like and we should now do more with this progress, right?

In basic python, you must have learned that we have in-built functions and sometimes, we have to **define our own functions.** The reason for creating our own functions is to enable efficiency in writing codes and eliminate repetitions. 

We would like our virtual assistant to always convert text to speech, observe punctuations, and continue speaking. Basically, the assistant has to execute #lines 6 and 7 consistently - as long as we continue updating our codes with instructions. But, we do not want to rewrite these lines over and over again. The ultimate way to tackle this problem is **to define a function that incorporates the two steps**. 

Let me show you how:


```
def speak(audio):

    engine.say(audio)
    
    engine.runAndWait()

speak("Talking is fun")
``` 


**Step 4: Adding Basic Instructions**

Now that we have our assistant ***ready to talk***, we can now begin to serve basic instructions to it (him or her).

Let us instruct our assistant to **tell us what the time is** at every current period when we run the function. See for yourself:



```
def time():
    
    Time = datetime.datetime.now().strftime("%H:%M:%S")# gives us the current time and date
    
    speak("The time is:")
    
    speak(Time)

time()
``` 

The function we have written above helps us when we create further instructions for our assistant. But the basic use of this function is for our assistant to tell us what the current time. You can now run it and hear what your assistant has to say. Be sure to confirm by checking your wristwatch! 

Note that the `datetime` function has helped us to do this. There are different ways of applying this function and you can find [an extensive explanation here](https://stackabuse.com/how-to-get-the-current-date-and-time-in-python/).

Our virtual assistant is looking great and wants to do much more for us. Now, let us write **a function that enables our assistant to tell us the current date**.


```
def year():
    
    Year = int(datetime.datetime.now().year) # we apply the int() function in order to make our results readable
    
    Month = int(datetime.datetime.now().month)
    
    Day = int(datetime.datetime.now().day)
    
    speak("Today's date is:")
    
    speak(Day)
    
    speak (Month)
    
    speak(Year)

year()
``` 

Okay. Now, run this new function and listen to your assistant! 

Mindblowing, right?


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1598126965436/PrdTqM3CA.png)

 The pieces are finally coming together. 


Now, for the final touch. We do not want a rude assistant, right? I mean, every time you start up your assistant, you need to be ***acknowledged***. 

With the functions we have created for the time and date, let us add a bit of *spice* by creating **a function which enables our assistant to welcome us as well as give us the basic information about the current date and time** before we proceed to give further instructions.  


```

def greet_me():
    
    speak("Hello there! Welcome! How are you doing today?")
    
    hour = datetime.datetime.now().hour
    
    if hour >= 6 and hour <= 12:
    
        speak('Good morning')
    
    elif hour >= 12 and hour < 18:
    
        speak('Good afternoon')
    
    elif hour >= 18 and hour <= 24:
    
        speak('Good evening')
    
    else:
        
        speak('Good night')
    
    time()
    
    year()
    
    speak("Tess at your service. How may I help you today?")

greet_me()

``` 

Pay attention that, with the `greet_me()` function, we have modified our assistant to greet us according to the hour of the day. To do this, I  imported a function that stores the current hour and accompanied it with an `if()` clause to be able to designate the greetings according to the hour of the day.


VOILA! You now have your basic virtual assistant up and running.



![bd6cb27c7cd527d680a30c1ccb7e512f.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1598128453589/jX2yRBQcj.gif)


However, that is not all there is to this. We need to ***level up*** and make a better version of our virtual assistant. 

Our virtual assistant was meant to relieve us of the stress of having to type. So, we need to now integrate a speech recognition function into our workspace so that we can now pass vocal instructions to our assistant.

Wanna see how it's done? Then you need to watch out for the next and final part of this article! You can hit the  [subscribe button](https://tesstife.hashnode.dev/) so that you don't miss anything. 

Let me know how this article has impacted you and don't forget to add the thumbs up, it'll only take a minute!

Till next time........................Codificación Feliz!