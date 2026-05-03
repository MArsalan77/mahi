# mahi
A humanized Python based Text to Speech assistant designed as a study companion for BE-CSE coursework. Named 'Mahi' this project turns complex Discrete Mathematics notes into interactive audio.
import pyttsx3

# Project Name: Mahi
def logivox_assistant():
    # Initialize
    engine = pyttsx3.init()
    
    # Configure: 0 for Male, 1 for Female (usually)
    voices = engine.getProperty('voices')
    engine.setProperty('voice', voices[0].id) 
    engine.setProperty('rate', 160)

    print("--- LogiVox Terminal Assistant ---")
    print("Type something for me to say (type 'exit' to stop)")

    while True:
        user_input = input("You: ")
        
        if user_input.lower() == 'exit':
            engine.say("Goodbye! Go finish Unit 1 now.")
            engine.runAndWait()
            break
        
        engine.say(user_input)
        engine.runAndWait()

if __name__ == "__main__":
    logivox_assistant()
