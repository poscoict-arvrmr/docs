참고사이트 
- [https://www.npmjs.com/package/mqtt](https://www.npmjs.com/package/mqtt)
- [http://www.mosca.io/](http://www.mosca.io/)


개발PC환경
<pre>
jinia@jin:~/Documents/GitHub/second$ <b>cd app</b>
jinia@jin:~/Documents/GitHub/second/app$ <b>npm install mqtt --save</b>
npm WARN second@1.0.0 No repository field.

+ mqtt@2.15.1
added 49 packages in 3.272s
jinia@jin:~/Documents/GitHub/second/app$ 
</pre>

package.json 확인 (
[https://github.com/poscoict-arvrmr/second/blob/master/app/package.json](https://github.com/poscoict-arvrmr/second/blob/master/app/package.json)
)
```
{
  "name": "second",
  ... 중략 ...
  "dependencies": {
    "firebase": "^4.9.0",
    "mqtt": "^2.15.1"
  }
}
```

1. mosca 라는 MQTT Broker를 설치한다. ```sudo npm install mosca pino -g```  

2. mosca 를 실행한다. ```mosca -v | pino```

3. 터미널을 하나 더 실행해서 public 를 실행한다. ```

<pre>
jinia@jin:~$ <b>sudo npm install mosca pino -g --unsafe-perm=true</b>
npm WARN deprecated mongodb@2.1.21: Please upgrade to 2.2.19 or higher
npm WARN deprecated node-uuid@1.4.8: Use uuid module instead
/usr/local/bin/mosca -> /usr/local/lib/node_modules/mosca/bin/mosca
/usr/local/bin/pino -> /usr/local/lib/node_modules/pino/bin.js
+ mosca@2.7.0
+ pino@4.10.3
updated 2 packages in 25.934s
jinia@jin:~$ 
</pre>

<pre>
jinia@jin:~$ <b>mosca -v | pino</b>
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
[2018-01-26T05:52:33.677Z] INFO (mosca/5634 on jin): server started
    mqtt: 1883



</pre>


<pre>
jinia@jin:~$ cd ~/Documents/GitHub/second
jinia@jin:~/Documents/GitHub/second$ ./app/node_modules/.bin/mqtt publish -t 'gesture/state' -h 'localhost' -p '1883' -i 'cmd' -m 'tap'
jinia@jin:~/Documents/GitHub/second$ ./app/node_modules/.bin/mqtt publish -t 'gesture/state' -h 'localhost' -p '1883' -i 'cmd' -m 'down'
jinia@jin:~/Documents/GitHub/second$ ./app/node_modules/.bin/mqtt publish -t 'gesture/state' -h 'localhost' -p '1883' -i 'cmd' -m 'up'
jinia@jin:~/Documents/GitHub/second$ ./app/node_modules/.bin/mqtt publish -t 'gesture/state' -h 'localhost' -p '1883' -i 'cmd' -m 'right'
jinia@jin:~/Documents/GitHub/second$ ./app/node_modules/.bin/mqtt publish -t 'gesture/state' -h 'localhost' -p '1883' -i 'cmd' -m 'left'
jinia@jin:~/Documents/GitHub/second$ 
</pre>


```
jinia@jin:~$ mosca -v | pino
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
[2018-01-26T05:52:33.677Z] INFO (mosca/5634 on jin): server started
    mqtt: 1883
[2018-01-26T05:54:21.063Z] INFO (mosca/5634 on jin): client connected
    client: "cmd"
[2018-01-26T05:54:21.068Z] INFO (mosca/5634 on jin): closed
    client: "cmd"
[2018-01-26T05:55:09.453Z] INFO (mosca/5634 on jin): client connected
    client: "cmd"
[2018-01-26T05:55:09.458Z] INFO (mosca/5634 on jin): closed
    client: "cmd"
[2018-01-26T05:55:13.065Z] INFO (mosca/5634 on jin): client connected
    client: "cmd"
[2018-01-26T05:55:13.069Z] INFO (mosca/5634 on jin): closed
    client: "cmd"
[2018-01-26T05:55:16.891Z] INFO (mosca/5634 on jin): client connected
    client: "cmd"
[2018-01-26T05:55:16.896Z] INFO (mosca/5634 on jin): closed
    client: "cmd"
[2018-01-26T05:55:21.227Z] INFO (mosca/5634 on jin): client connected
    client: "cmd"
[2018-01-26T05:55:21.232Z] INFO (mosca/5634 on jin): closed
    client: "cmd"
```

[mosca](https://www.npmjs.com/package/mosca) 모듈은 mqtt broker 이고.. [pino](https://www.npmjs.com/package/pino) 모듈은 logger 라는거 같다.  
테스트용으로 standalone 방식으로 실행할 예정이다.  