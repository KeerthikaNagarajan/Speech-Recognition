
<h1 align="center">  
  Implementation of Speech Recognition 
</h1>  


## Aim:
 To implement the conversion of live speech to text.<BR>
## Algorithm:
#### Step 1: 
Import the speech_recognition library<Br>
#### Step 2: 
Initialize the Recognizer<Br>
#### Step 3: 
Create an instance of the Recognizer class, which will be used for recognizing speech.<Br>
#### Step 4: 
Set the duration for audio capture<Br>
#### Step 5: 
Define a variable to specify the duration (in seconds) for which the program will capture audio from the microphone.<Br>
#### Step 6: 
Display a message in the console to prompt the user to speak.<Br>
#### Step 7: 
Capture audio from the default microphone<Br>
#### Step 9: 
Use the default microphone as the audio source.<Br>
#### Step 10: 
Record audio for the specified duration using the Recognizer instance.<Br>
#### Step 11: 
Perform speech recognition with exceptional handling:<Br>
•	Attempt to recognize speech from the captured audio using the Google Speech Recognition service.<Br>
•	If successful, print the recognized text.<Br>
•	Handle specific exceptions: If the recognition result is unknown or if there is an issue with the request to the Google Speech Recognition service, print corresponding error messages.<Br>
•	A generic exception block captures any other unexpected errors.<Br>
## Program:
```py

import pyaudio
import speech_recognition as sr

# initialize the Recognizer
r = sr.Recognizer()

# Set duration for audio capture
duration = 10

# Record audio
print("Say Something")

# Use the default microphone as the audio source
with sr.Microphone() as source:
    audio_data = r.listen(source, timeout=duration)

try:
    text = r.recognize_google(audio_data)
    print("you said:", text)
except sr.UnknownValueError:
    print("Sorry, could not understand audio")
except sr.RequestError as e:
    print(f'Error with the request to Google Speech Recognition Service: {e}')
except Exception as e:
    print(f'Error: {e}')


```
## Output:
<img width="404" alt="output 8 " src="https://github.com/user-attachments/assets/59f7902f-0eac-4544-bf26-0db0eeb44251">


## Result:
Thus, we have implemented a program that will transcribe the audio file in the file variable and print the transcribed text on the console, one line at a time.
