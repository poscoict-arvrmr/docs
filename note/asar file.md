
npm run package 를 실행하면.. 다음과 같은 로그를 통해 어떤 파일이 생성되었는지 확인할 수 있음. 
<pre>
• electron-builder version=19.52.1
• loaded configuration file=package.json ("build" field)
• writing effective config file=release/electron-builder.yaml
• installing production dependencies platform=linux arch=x64 appDir=/home/jinia/Documents/GitHub/electron-react-boilerplate/app
• packaging       platform=linux arch=x64 electron=1.7.10 appOutDir=<b>release/linux-unpacked</b>
• building        target=AppImage arch=x64 file=<b>release/electron-react-boilerplate-1.0.0-x86_64.AppImage</b>
• building embedded block map file=release/electron-react-boilerplate-1.0.0-x86_64.AppImage
• building        target=deb arch=x64 file=release/electron-react-boilerplate_1.0.0_amd64.deb
</pre>


실행파일인 AppImage를 실행하면... app.html을 로딩한다.
<pre>
  console.log('찍혀라[main.dev]', __dirname);
  mainWindow.loadURL(`file://${__dirname}/app.html`);
</pre>

```__dirname``` 값이 뭔지 알아 내려고 console log를 추가해봄 (main.dev.js 파일의 전후 로그추가함)

<pre>
jinia@jin:~/Documents/GitHub/electron-react-boilerplate$ <b>./release/electron-react-boilerplate-1.0.0-x86_64.AppImage </b>
찍혀라[main.dev] production
찍혀라[main.dev] ready 되면 BrowserWindow 생성해야지
찍혀라[main.dev] <b>/tmp/.mount_electrVqlwVQ/app/resources/app.asar</b>
찍혀라[main.dev] 로딩이 되어나벼
jinia@jin:~/Documents/GitHub/electron-react-boilerplate$ 
```
</pre>


<b>release/linux-unpacked</b> 위치에서 file과 폴더 중에 app.asar 파일이 있는지 확인된다.

<pre>
jinia@jin:~/Documents/GitHub/electron-react-boilerplate$ asar list ./release/linux-unpacked/resources/app.asar 
/app.html
/main.prod.js
/main.prod.js.map
/package.json
/dist
/dist/674f50d287a8c48dc19ba404d20fe713.eot
/dist/912ec66d7572ff821749319396470bde.svg
/dist/af7ae505a9eed503f8b8e6982036873e.woff2
/dist/b06871f281fee6b241d60582ae9369b9.ttf
/dist/fee66e712a8a08eef5805a46892932ad.woff
/dist/renderer.prod.js
/dist/renderer.prod.js.map
/dist/style.css
/dist/style.css.map
</pre>


npm run dev 로 시작하거나 npm run start로 시작하면. __dirname 값이 
/home/jinia/Documents/GitHub/electron-react-boilerplate/app  으로 나온다. 

```
찍혀라[main.dev] development
찍혀라[main.dev] 뭘 설치하나벼
찍혀라[main.dev] ready 되면 BrowserWindow 생성해야지
찍혀라[main.dev] /home/jinia/Documents/GitHub/electron-react-boilerplate/app
찍혀라[main.dev] 로딩이 되어나벼
```

```
찍혀라[main.dev] production
찍혀라[main.dev] ready 되면 BrowserWindow 생성해야지
찍혀라[main.dev] /home/jinia/Documents/GitHub/electron-react-boilerplate/app
찍혀라[main.dev] 로딩이 되어나벼
```

