## SpeechRecognition 음성인식

0. 음성인식 + 제스쳐 + 브로커 + second app
- MQTT broker (...246.244 <code> $ mosca -v | pino </code>) ==> 
- gesture.py (<code> $ python gesture.py </code>), wit.py (<code> $ python wit.py </code>) ==> 
- second app (<code> $ npm run dev </code>)


1. Raspberry Pi Virtual Assistant book code example

**파이썬기본패키지설치**
```bash
# speechrecognition 패키지설치
$ sudo pip3 install SpeechRecognition 

# pyaudio 패키지설치
$ sudo pip3 install pyaudio
# 이게 에러가 나면
$ sudo apt-get install portaudio19-dev
$ sudo pip3 install pyaudio
$ sudo pip3 install pyaudio --upgrade

# upgrade --> 0.2.11 버젼으로만들어줘야함
```

**실행예시코드**
_main.py_
```python
import speech_recognition as sr

r = sr.Recognizer()
with sr.Microphone() as source:
	print("Say something")
	audio = r.listen(source)

with open("recording.wav", "wb") as f:
	f.write(audio.get_wav_data())
```

**코드실행**

```bash
# main.py 있는 폴더로 cd
$ python3 main.py
```
