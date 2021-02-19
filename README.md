# Ron
## The Mood Jukebox
This is a talking chatbot that recommonds a song based on the mood of the way you are talking at the moment. In this manner, you can find the perfect song that suits your mood. 

### Prerequisites
I have used Pycharm as my coding environment (the community version).
Link: https://www.jetbrains.com/pycharm/download/#section=windows
### Installing
It is important to install every library you are importing. You are using 'pip install' and then add the specific library to it. For example: pip install pyttsx3. You write this in the terminal at Pycharm and just enter. 

### Components 
#### Talking 
The function talk creates the voice. I have slowed the rate down because it was too fast. Later at take command, I am indicating what the bot should say. 

#### Understanding 
First of all we needed it a Listener. With the library speech recognition was this easily possible. Following to the result of the listener we need to determine the mood of the person. Vader sentiments analyzer was a handy solution to it. With the column compound we could find a overall score of the mood.

#### Spotifylist
To find the perfect song we have used a spotify list on kaggle. Each song on Spotify has a danceability score. It was a good match to link with compound.

#### Playing on Youtube 
The function playonyt of pywhatkit plays the resulted song in a second on YouTube.

### Future
1. Developing a online web application. I try to use Flask or Streamlit, but due to limited time I could not finish it. 
2. Making it avalaible in different languages 

### Links
These are the links that I have used during the project.
https://stackoverflow.com/
https://github.com/ProgrammingHero1/romantic-alexa
https://www.kaggle.com/yamaerenay/spotify-dataset-19212020-160k-tracks
https://analyticsindiamag.com/sentiment-analysis-made-easy-using-vader/

### Authors
Eray Boynuince - Student at the University of Antwerp
with
Benedikt Perak - Assistant Professor att the University of Rijeka 
In functionn of the course Digital Linguistics and related to the YUFE program
