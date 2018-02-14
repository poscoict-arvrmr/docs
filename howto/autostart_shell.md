
* second-1.0.0-armv7l.AppImage

* second-1.0.0-gesture.py

* second.sh

# 파일

3개 파일의 위치는 default 로...    
즉 ```/home/pi``` 위치에 있다는 가정하에... 쉘 프로그램이 작성되었음. 

```bash
pi@raspberrypi:~ $ ls -al second*
-rwxr-xr-x 1 pi pi 84462543  2월 12 16:38 second-1.0.0-armv7l.AppImage
-rwxr-xr-x 1 pi pi     1134  2월 12 16:40 second-1.0.0-gesture.py
-rwxr-xr-x 1 pi pi      771  2월 12 18:17 second.sh
pi@raspberrypi:~ $ 
```

# 개발PC환경

 * npm

 * python


## npm

```bash
pi@raspberrypi:~ $ npm -v
5.5.1
pi@raspberrypi:~ $ mosca --version
       +++.+++:   ,+++    +++;   '+++    +++. 
      ++.+++.++   ++.++  ++,'+  `+',++  ++,++ 
      +`  +,  +: .+  .+  +;  +; '+  '+  +`  +` 
      +`  +.  +: ,+  `+  ++  +; '+  ;+  +   +. 
      +`  +.  +: ,+  `+   +'    '+      +   +. 
      +`  +.  +: ,+  `+   :+.   '+      +++++. 
      +`  +.  +: ,+  `+    ++   '+      +++++. 
      +`  +.  +: ,+  `+     ++  '+      +   +. 
      +`  +.  +: ,+  `+  +:  +: '+  ;+  +   +. 
      +`  +.  +: .+  .+  +;  +; '+  '+  +   +. 
      +`  +.  +:  ++;++  ++'++   ++'+'  +   +. 
      +`  +.  +:   +++    +++.   ,++'   +   +. 
2.7.0
pi@raspberrypi:~ $ 
```

mosca가 없으면 ```sudo npm install -g mosca pino``` 로 설치하면 됨. 

## python

```bash
pi@raspberrypi:~ $ python3 -V
Python 3.5.3
pi@raspberrypi:~ $ pip3 list | grep mqtt
DEPRECATION: The default format will switch to columns in the future. You can use --format=(legacy|columns) (or define a format=(legacy|columns) in your pip.conf under the [list] section) to disable this warning.
paho-mqtt (1.3.1)
pi@raspberrypi:~ $ 
```

paho-mqtt가 없으면 ```sudo pip3 install paho-mqtt``` 로 설치하면 됨.

# 실행순서

처음 실행하는 경우

```
mosca -v | pino
python3 second-1.0.0-gesture.py
second-1.0.0-armv7l.AppImage
```

프로세스 죽이기

<pre>
ps -ef | grep <i>mosca</i>
kill -9 <i>1111</i>
ps -ef | grep <i>python</i>
kill -9 <i>1111</i>
</pre>

쉘 스크립트로 실행하는 경우

```
second.sh
```

# 쉘 스크립트

```bash
pi@raspberrypi:~ $ cat second.sh
#!/bin/bash
PID=`ps -ef | grep 'python' | grep 'second' | awk '{print $2}'`
if [ "" == "$PID" ]
  then echo "no python process"
  else 
    kill $PID
    sleep 1
fi

PID=`ps -ef | grep 'mosca' | grep -v 'grep' | awk '{print $2}'`
if [ "" ==  "$PID" ]
  then echo "no mosca process"
  else
    kill $PID
    sleep 1
fi

echo "checked.."
rm /home/pi/Documents/second*
echo "remove logs"
/home/pi/.nvm/versions/node/v9.3.0/bin/mosca -v | /home/pi/.nvm/versions/node/v9.3.0/bin/pino > /home/pi/Documents/second.out &
echo "launch mosca"
sleep 5 && /usr/bin/python3 /home/pi/second-1.0.0-gesture.py > /home/pi/Documents/second.py.log &
echo "launch python"
/home/pi/second-1.0.0-armv7l.AppImage > /home/pi/Documents/second.AppImage.log &
echo "launch AppImage"

pi@raspberrypi:~ $ 
```

