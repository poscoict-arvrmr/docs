## SpeechRecognition 음성인식

1. Raspberry Pi Virtual Assistant book code example

**파이썬기본패키지설치**
```bash
# speechrecognition 패키지설치
$ sudo pip3 install SpeechRecognition 

# pyaudio 패키지설치
$ sudo pip3 install pyaudio
  이게 에러가 나면
$ sudo apt-get install portaudio19-dev
$ sudo pip3 install pyaudio
$ sudo pip3 install pyaudio --upgrade

# upgrade --> 0.2.11 버젼으로만들어줘야함
```

**실행예시코드**
```python
import speech_recognition as sr

r = sr.Recognizer()
with sr.Microphone() as source:
	print("Say something")
	audio = r.listen(source)

with open("recording.wav", "wb") as f:
	f.write(audio.get_wav_data())
```
