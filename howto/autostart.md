참고사이트
- [https://blog.startingelectronics.com/auto-start-a-desktop-application-on-the-rapberry-pi/](https://blog.startingelectronics.com/auto-start-a-desktop-application-on-the-rapberry-pi/)

<pre>
pi@raspberrypi:~ $ <i># github에서 다운로드할 위치로 이동해서 clone 해오기</i>
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ <b>cd <i>~/Downloads/</i></b>
pi@raspberrypi:~/Downloads $ <b>git clone <i>https://github.com/poscoict-arvrmr/first.git</i></b>
'first'에 복제합니다...
remote: Counting objects: 43, done.
remote: Compressing objects: 100% (27/27), done.
remote: Total 43 (delta 21), reused 34 (delta 14), pack-reused 0
오브젝트 묶음 푸는 중: 100% (43/43), 완료.
pi@raspberrypi:~/Downloads $ <b>cd <i>first</i></b>
pi@raspberrypi:~/Downloads/first $ 
pi@raspberrypi:~/Downloads/first $ 
pi@raspberrypi:~/Downloads/first $ <i># npm install 을 실행해야 </i>
pi@raspberrypi:~/Downloads/first $ <i># package.json에 등록되어 있는 모듈이 </i>
pi@raspberrypi:~/Downloads/first $ <i># node_modules 에 추가됨( eg. react ) </i>
pi@raspberrypi:~/Downloads/first $ 
pi@raspberrypi:~/Downloads/first $ 
pi@raspberrypi:~/Downloads/first $ <b>npm install</b>

> electron@1.7.10 postinstall /home/pi/Downloads/first/node_modules/electron
> node install.js

added 169 packages in 27.404s
pi@raspberrypi:~/Downloads/first $ <b>pwd</b>
/home/pi/Downloads/first
pi@raspberrypi:~/Downloads/first $ <b>whereis electron</b>
electron: /usr/lib/electron /home/pi/.nvm/versions/node/v9.3.0/bin/electron
pi@raspberrypi:~/Downloads/first $ <b>cd ~</b>
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ <i># 터미널에서는 4가지 방법으로 first app을 실행할 수 있음</i>
pi@raspberrypi:~ $ <i># electron ~/Downloads/first</i>
pi@raspberrypi:~ $ <i># electron /home/pi/Downloads/first</i>
pi@raspberrypi:~ $ <i># /home/pi/.nvm/versions/node/v9.3.0/bin/electron ~/Downloads/first</i>
pi@raspberrypi:~ $ <i># /home/pi/.nvm/versions/node/v9.3.0/bin/electron /home/pi/Downloads/first</i>
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ <i># autostart 파일 내용 확인 후 수정 -> 4번재 절대 패스 사용할것것</i>
pi@raspberrypi:~ $  
pi@raspberrypi:~ $ <b>cat .config/lxsession/LXDE-pi/autostart</b> 
@lxpanel --profile LXDE-pi
@pcmanfm --desktop --profile LXDE-pi
@xscreensaver -no-splash
@point-rpi
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ <b>nano .config/lxsession/LXDE-pi/autostart</b>
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ <i># @로 시작하는 명령어 추가하고 저장하고 나오기.</i>
pi@raspberrypi:~ $ <i># Ctrl+O:저장, Enter:확인, Ctrl+X:종료 순으로 </i>
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ <b>cat .config/lxsession/LXDE-pi/autostart </b>
@lxpanel --profile LXDE-pi
@pcmanfm --desktop --profile LXDE-pi
@xscreensaver -no-splash
@point-rpi
@/home/pi/.nvm/versions/node/v9.3.0/bin/electron /home/pi/Downloads/first 
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ 
pi@raspberrypi:~ $ <i># 수정사항 확인하고 새시작해서 확인</i>
pi@raspberrypi:~ $ <b>sudo reboot</b>
</pre>
