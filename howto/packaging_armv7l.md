개발PC환경

node, npm, git 사용가능해야함. 
<pre>
jinia@jin:~$ <b>node -v</b>
v8.9.3
jinia@jin:~$ <b>npm -v</b>
5.6.0
jinia@jin:~$ <b>git --version</b>
git version 2.14.1
jinia@jin:~$ 
<pre>

소스는 github에서 가져오고.. 
<pre>
jinia@jin:~$ <b>cd <i>~/Documents/GitHub/</i></b>
jinia@jin:~/Documents/GitHub$ <b>git clone https://github.com/poscoict-arvrmr/second.git</b>
Cloning into 'second'...
remote: Counting objects: 324, done.
remote: Compressing objects: 100% (221/221), done.
remote: Total 324 (delta 137), reused 271 (delta 85), pack-reused 0
Receiving objects: 100% (324/324), 1.34 MiB | 1.03 MiB/s, done.
Resolving deltas: 100% (137/137), done.
jinia@jin:~/Documents/GitHub$ <b>cd second/</b>
jinia@jin:~/Documents/GitHub/second$
</pre>


빌드 수행하면 됨. 아래 로그 있음. 
```
cd second
npm install
npm run build
./node_modules/.bin/electron-builder --armv7l
```

라즈베리에서 AppImage를 ftp로 get하면 됨. 
```
sftp jinia@192.168.41.81
cd ~/Documents/GitHub/second/release
get second-1.0.0-armv7l.AppImage
exit
```


<pre>
jinia@jin:~/Documents/GitHub/second$ <b>npm install</b>

> electron-chromedriver@1.8.0 install /home/jinia/Documents/GitHub/second/node_modules/electron-chromedriver
> node ./download-chromedriver.js

successfully dowloaded and extracted!

> node-sass@4.7.2 install /home/jinia/Documents/GitHub/second/node_modules/node-sass
> node scripts/install.js

... 중략 ...

  • electron-builder version=19.55.2
  • loaded configuration file=package.json ("build" field)
  • installing production dependencies platform=linux arch=x64 appDir=/home/jinia/Documents/GitHub/second/app
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: 7zip-bin-win@2.1.1 (node_modules/7zip-bin-win):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for 7zip-bin-win@2.1.1: wanted {"os":"win32","arch":"any"} (current: {"os":"linux","arch":"x64"})
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: 7zip-bin-mac@1.0.1 (node_modules/7zip-bin-mac):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for 7zip-bin-mac@1.0.1: wanted {"os":"darwin","arch":"any"} (current: {"os":"linux","arch":"x64"})
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.1.3 (node_modules/fsevents):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.1.3: wanted {"os":"darwin","arch":"any"} (current: {"os":"linux","arch":"x64"})

added 1979 packages in 175.391s
jinia@jin:~/Documents/GitHub/second$ <b>npm run build</b>

> second@1.0.0 build /home/jinia/Documents/GitHub/second
> concurrently "npm run build-main" "npm run build-renderer"

[1] 
[1] > second@1.0.0 build-renderer /home/jinia/Documents/GitHub/second
[1] > cross-env NODE_ENV=production node --trace-warnings -r babel-register ./node_modules/webpack/bin/webpack --config webpack.config.renderer.prod.js --colors
[1] 
[0] 
[0] > second@1.0.0 build-main /home/jinia/Documents/GitHub/second
[0] > cross-env NODE_ENV=production node --trace-warnings -r babel-register ./node_modules/webpack/bin/webpack --config webpack.config.main.prod.js --colors
[0] 

... 중략 ...

[1] Child extract-text-webpack-plugin node_modules/extract-text-webpack-plugin/dist node_modules/css-loader/index.js??ref--2-1!app/components/Mymenu.css:
[1]        2 modules
[1] Child extract-text-webpack-plugin node_modules/extract-text-webpack-plugin/dist node_modules/css-loader/index.js??ref--2-1!app/components/Home.css:
[1]        2 modules
[1] Child extract-text-webpack-plugin node_modules/extract-text-webpack-plugin/dist node_modules/css-loader/index.js??ref--1-2!app/app.global.css:
[1]      5 assets
[1]     [./node_modules/css-loader/index.js?{"minimize":true}!./app/app.global.css] ./node_modules/css-loader?{"minimize":true}!./app/app.global.css 698 bytes {0} [built]
[1]         + 9 hidden modules
[1] npm run build-renderer exited with code 0
jinia@jin:~/Documents/GitHub/second$ <b>./node_modules/.bin/electron-builder --armv7l</b>
  • electron-builder version=19.55.2
  • loaded configuration file=package.json ("build" field)
  • writing effective config file=release/electron-builder.yaml
  • rebuilding native production dependencies platform=linux arch=armv7l
  • packaging       platform=linux arch=armv7l electron=1.7.11 appOutDir=release/linux-armv7l-unpacked
  • building        target=AppImage arch=armv7l file=release/second-1.0.0-armv7l.AppImage
  • building embedded block map file=release/second-1.0.0-armv7l.AppImage
  • building        target=deb arch=armv7l file=release/second_1.0.0_armv7l.deb
jinia@jin:~/Documents/GitHub/second$ <b>ls release -al</b>
total 125356
drwxr-xr-x  3 jinia jinia     4096 Feb  2 14:32 .
drwxrwxr-x 12 jinia jinia     4096 Feb  2 14:32 ..
-rw-r--r--  1 jinia jinia      443 Feb  2 14:29 electron-builder.yaml
-rw-r--r--  1 jinia jinia      376 Feb  2 14:32 latest-linux-armv7l.yml
drwxr-xr-x  4 jinia jinia     4096 Feb  2 14:30 linux-armv7l-unpacked
-rwxr-xr-x  1 jinia jinia 84430751 Feb  2 14:31 <b>second-1.0.0-armv7l.AppImage</b>
-rw-r--r--  1 jinia jinia 43909540 Feb  2 14:32 second_1.0.0_armv7l.deb
jinia@jin:~/Documents/GitHub/second$ 
</pre>
