참고사이트 
- [https://www.youtube.com/watch?v=kN1Czs0m1SU](https://www.youtube.com/watch?v=kN1Czs0m1SU)



개발PC환경

```
jinia@jin:~$ node -v
v8.9.3
jinia@jin:~$ npm -v
5.6.0
jinia@jin:~$ electron -v
v1.7.10
jinia@jin:~$ 
```

package.json 확인 (
[https://github.com/poscoict-arvrmr/first/blob/master/package.json](https://github.com/poscoict-arvrmr/first/blob/master/package.json)
)
```
{
  "name": "startup",
  ... 중략 ...
  "scripts": {
    "start": "electron ."
  },
  ... 중략 ...
  "dependencies": {
    "electron": "^1.7.10",
    "react": "^16.2.0",
    "react-dom": "^16.2.0"
  }
}
```

package.json에 elctron-packager를 추가하고 scripts 를 수정한다. 
프로젝트로 이동해서 ```npm install --save-dev eclectron-packager``` 를 실행한다.
<pre>
jinia@jin:~$ <b>cd <i>~/Documents/GitHub/first/</i></b>
jinia@jin:~/Documents/GitHub/first$
jinia@jin:~/Documents/GitHub/first$ <b>npm install --save-dev electron-packager</b>

> electron@1.7.10 postinstall /home/jinia/Documents/GitHub/first/node_modules/electron
> node install.js

+ electron-packager@10.1.1
added 243 packages in 7.945s
jinia@jin:~/Documents/GitHub/first$
</pre>

package.json 파일을 열어서 scripts 부분을 수정한다. 
<pre>
  ... 중략 ...
  "scripts": {
    "start": "electron ."<b>,
    "package": "electron-packager . --overwrite --platform=linux --arch=x64 --icon=icon.png --prune=true --out=release-builds"</b>
  },
  ... 중략 ...  
  "devDependencies": {
    "electron-packager": "^10.1.1"
  }
  ... 중략 ...  
</pre>

icon.png 파일을 추가한다. 
[http://www.iconarchive.com/](http://www.iconarchive.com/)에서 icon.png 파일을 다운로드 받을수 있다. 
<pre>
jinia@jin:~/Documents/GitHub/first$ <b>wget <i>http://icons.iconarchive.com/icons/custom-icon-design/flatastic-10/512/Edit-validated-icon.png</i></b>
--2018-01-05 13:51:03--  http://icons.iconarchive.com/icons/custom-icon-design/flatastic-10/512/Edit-validated-icon.png
Resolving icons.iconarchive.com (icons.iconarchive.com)... 104.25.157.13, 104.25.156.13, 2400:cb00:2048:1::6819:9d0d, ...
Connecting to icons.iconarchive.com (icons.iconarchive.com)|104.25.157.13|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30575 (30K) [image/png]
Saving to: ‘Edit-validated-icon.png’

Edit-validated-icon.png                      100%[===========================================================================================>]  29.86K  --.-KB/s    in 0.02s   

2018-01-05 13:51:03 (1.71 MB/s) - ‘Edit-validated-icon.png’ saved [30575/30575]

jinia@jin:~/Documents/GitHub/first$ <b>mv <i>Edit-validated-icon.png</i> icon.png</b>
jinia@jin:~/Documents/GitHub/first$ 
</pre>


```npm run package``` 를 실행한다.
<pre>
jinia@jin:~/Documents/GitHub/first$ <b>npm run package</b>

> startup@1.0.0 package /home/jinia/Documents/GitHub/first
> electron-packager . --overwrite --platform=linux --arch=x64 --icon=icon.png --prune=true --out=release-builds

Packaging app for platform linux x64 using electron v1.7.10
Wrote new app to <b>release-builds/startup-linux-x64</b>
jinia@jin:~/Documents/GitHub/first$ 
jinia@jin:~/Documents/GitHub/first$ 
jinia@jin:~/Documents/GitHub/first$ <b>ls</b>
changePages.js  index.js         myapps.html   node_modules  package-lock.json  <b>release-builds</b>  stylesheet.css
<b>icon.png</b>        mainWindow.html  myfiles.html  package.json  README.md          setup.md
jinia@jin:~/Documents/GitHub/first$
jinia@jin:~/Documents/GitHub/first$
jinia@jin:~/Documents/GitHub/first$ <b>ls -al release-builds/startup-linux-x64/</b>
total 130464
drwxrwxr-x 4 jinia jinia     4096 Jan  5 14:00 .
drwxrwxr-x 3 jinia jinia     4096 Jan  5 14:00 ..
-rw-r--r-- 1 jinia jinia    24844 Jan  5 14:00 blink_image_resources_200_percent.pak
-rw-r--r-- 1 jinia jinia       15 Jan  5 14:00 content_resources_200_percent.pak
-rw-r--r-- 1 jinia jinia 12032534 Jan  5 14:00 content_shell.pak
-rw-r--r-- 1 jinia jinia 10130560 Jan  5 14:00 icudtl.dat
-rw-r--r-- 1 jinia jinia  2980664 Jan  5 14:00 libffmpeg.so
-rwxr-xr-x 1 jinia jinia 21136056 Jan  5 14:00 libnode.so
-rw-r--r-- 1 jinia jinia     1060 Jan  5 14:00 LICENSE
-rw-r--r-- 1 jinia jinia  1775951 Jan  5 14:00 LICENSES.chromium.html
drwxrwxr-x 2 jinia jinia     4096 Jan  5 14:00 locales
-rw-r--r-- 1 jinia jinia   262947 Jan  5 14:00 natives_blob.bin
-rw-r--r-- 1 jinia jinia   140979 Jan  5 14:00 pdf_viewer_resources.pak
drwxrwxr-x 3 jinia jinia     4096 Jan  5 14:00 resources
-rw-r--r-- 1 jinia jinia  1448208 Jan  5 14:00 snapshot_blob.bin
<b>-rwxr-xr-x 1 jinia jinia 83392984 Jan  5 14:00 <i>startup</i></b>
-rw-r--r-- 1 jinia jinia   151829 Jan  5 14:00 ui_resources_200_percent.pak
-rw-r--r-- 1 jinia jinia        7 Jan  5 14:00 version
-rw-r--r-- 1 jinia jinia    57761 Jan  5 14:00 views_resources_200_percent.pak
jinia@jin:~/Documents/GitHub/first$
jinia@jin:~/Documents/GitHub/first$
jinia@jin:~/Documents/GitHub/first$ <b>./release-builds/startup-linux-x64/startup</b>
</pre>


실행이 안되는 경우는 실행가능 파일로 변경한다. 
<pre>
chmod +x ./release-builds/startup-linux-x64/startup
</pre>
