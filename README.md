<p>THIS A J A R V I S (personnel assistant)created using python.
You have to type your name where its asked in the code.
If you want to add a new website a place is given there to add.</p>
<p><strong>How To build your own personnel assitant<strong><p>
<p>Language</p>
PYTHON
<p>Modules Required</p>
<ol>
<li> pyttsx3</li>
<li> webbrowser</li>
<li> smtplib</li>
<li> random</li>
<li>speech_recognition as sr</li>
<li> wikipedia</li>
<li> datetime</li>
<li> wolframalpha</li>
<li> os</li>
<li>sys</li>
</ol>
<p><b>requirement<b><p>
Wolfram alpha API id
<div>
    def speak(audio):
    print('Computer: ' + audio)
    engine.say(audio)
    engine.runAndWait()

    def greetMe():                              (Over here we define how we want to greet ourselfs)
    currentH = int(datetime.datetime.now().hour)
    if currentH >= 0 and currentH < 12:
        speak('Good Morning!')

    if currentH >= 12 and currentH < 18:
        speak('Good Afternoon!')

    if currentH >= 18 and currentH !=0:
        speak('Good Evening!')

    greetMe()

    speak('Hello YOUR NAME')   (You have to add your name here)
    speak('How may I help you?')

  
    def myCommand():
   
    r = sr.Recognizer()                                                                                   
    with sr.Microphone() as source:                                                                       
        print("Listening...")
        r.pause_threshold =  1
        audio = r.listen(source)
    try:
        query = r.recognize_google(audio, language='en-in')
        print('User: ' + query + '\n')
        
    except sr.UnknownValueError:
        speak('Sorry YOUR NAME! I didn\'t get that! Try typing the command!')
        query = str(input('Command: '))

    return query
        

    if __name__ == '__main__':

    while True:
    
        query = myCommand();
        query = query.lower()
        
        if 'open youtube' in query:
            speak('okay')
            webbrowser.open('www.youtube.com')

        elif 'open google' in query:
            speak('okay')
            webbrowser.open('www.google.co.in')

        elif 'open gmail' in query:
            speak('okay')
            webbrowser.open('www.gmail.com')

        elif "what\'s up" in query or 'how are you' in query:
            stMsgs = ['Just doing my thing!', 'I am fine!', 'Nice!', 'I am nice and full of energy']
            speak(random.choice(stMsgs))
        elif'open WEBSITE' in query:
            speak('okay')
            webbrowser.open('THE LINK') 
        elif 'open stackoverflow' in query:
            speak('okay')
            webbrowser.open('www.stackoverflow.com') 
        elif 'nothing' in query or 'abort' in query or 'stop' in query:
            speak('okay')
            speak('Bye YOUR NAME, have a good day.')
            sys.exit()
           
        elif 'hello' in query:
            speak('Hello YOUR NAME')

        elif 'bye' in query:
            speak('Bye YOUR NAME, have a good day.')
            sys.exit()

<strong>YOU CAN KEEP ON ADDING elif and define different functions its upto u</strong>



        else:
            query = query
            speak('Searching...')
            try:
                try:
                    res = client.query(query)
                    results = next(res.results).text
                    speak('WOLFRAM-ALPHA says - ')
                    speak('Got it.')
                    speak(results)
                    
                except:
                    results = wikipedia.summary(query, sentences=2)
                    speak('Got it.')
                    speak('WIKIPEDIA says - ')
                    speak(results)
        
            except:
                webbrowser.open('www.google.com')
        
        speak('what else YOUR NAME') (add your name here)
</div>
<strong>Additional Info</strong>
<p>Anyone Can Use the File's given here, with the use of this License...</p>
<p>Please refrain from using these content from any malicious use. I do not claim responsibility or involvement for any trouble you may get into by using these files....</p>
