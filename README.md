# Ron
The mood Jukebox

pip install pyttsx3
pip install SpeechRecognition
pip install pywhatkit

import speech_recognition as sr
import pyttsx3
import pywhatkit
import datetime
import wikipedia
from vaderSentiment.vaderSentiment import SentimentIntensityAnalyzer

analyser = SentimentIntensityAnalyzer()
scoreavg= 0

def sentiment_analyzer_scores(sentence):
    score = analyser.polarity_scores(sentence)
    print("{:-<40} {}".format(sentence, str(score)))
    global scoreavg
    scoreavg = score['compound']





listener = sr.Recognizer()
engine = pyttsx3.init()
voices = engine.getProperty('voices')
engine.setProperty('voice', voices[0].id)

def talk(text):
    engine.say(text)
    engine.runAndWait()


def take_command():
    try:
        with sr.Microphone() as source:
            print('How do you feel?')
            voice = listener.listen(source)
            command = listener.recognize_google(voice)
            command = command.lower()
            if 'Hey Ron' in command:
                command = command.replace('Hey Ron', '')
                print(command)
    except:
        pass
    return command


def run_Ron():
    command = take_command()
    sentiment_analyzer_scores(command)
    if scoreavg < -0.5:
        song = ('Sad')
        talk('Playing a sad song to empthasie with you')
        pywhatkit.playonyt(song)
    elif scoreavg <0:
        song = ('mood')
        talk('Playing a mooding song to feel realy moody')
        pywhatkit.playonyt(song)
    elif scoreavg <0.5:
        song = ('Normal')
        talk('Playing a normal song because you are normal')
        pywhatkit.playonyt(song)
    else:
        song = ('happy')
        talk('Playing a happy song because you love life')
        pywhatkit.playonyt(song)


run_Ron()
