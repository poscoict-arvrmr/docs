electron-react-boilerplate 라는 GitHub 프로젝트의 package.json 이해.. 

```
  "scripts": {
    "build": "concurrently \"npm run build-main\" \"npm run build-renderer\"",
    "build-dll": "cross-env NODE_ENV=development node --trace-warnings -r babel-register ./node_modules/webpack/bin/webpack --config webpack.config.renderer.dev.dll.js --colors",
    "build-main": "cross-env NODE_ENV=production node --trace-warnings -r babel-register ./node_modules/webpack/bin/webpack --config webpack.config.main.prod.js --colors",
    "build-renderer": "cross-env NODE_ENV=production node --trace-warnings -r babel-register ./node_modules/webpack/bin/webpack --config webpack.config.renderer.prod.js --colors",
    "dev": "cross-env START_HOT=1 node -r babel-register ./internals/scripts/CheckPortInUse.js && cross-env START_HOT=1 npm run start-renderer-dev",
    "electron-rebuild": "electron-rebuild --parallel --force --types prod,dev,optional --module-dir app",
    "flow": "flow",
    "flow-typed": "rimraf flow-typed/npm && flow-typed install --overwrite || true",
    "lint": "eslint --cache --format=node_modules/eslint-formatter-pretty .",
    "lint-fix": "npm run lint -- --fix",
    "lint-styles": "stylelint app/*.css app/components/*.css --syntax scss",
    "lint-styles-fix": "stylefmt -r app/*.css app/components/*.css",
    "package": "npm run build && build --publish never",
    "package-all": "npm run build && build -mwl",
    "package-linux": "npm run build && build --linux",
    "package-win": "npm run build && build --win --x64",
    "postinstall": "node -r babel-register internals/scripts/CheckNativeDep.js && npm run flow-typed && npm run build-dll && electron-builder install-app-deps && node node_modules/fbjs-scripts/node/check-dev-engines.js package.json",
    "prestart": "npm run build",
    "start": "cross-env NODE_ENV=production electron ./app/",
    "start-main-dev": "cross-env HOT=1 NODE_ENV=development electron -r babel-register ./app/main.dev",
    "start-renderer-dev": "cross-env NODE_ENV=development node --trace-warnings -r babel-register ./node_modules/webpack-dev-server/bin/webpack-dev-server --config webpack.config.renderer.dev.js",
    "test": "cross-env NODE_ENV=test BABEL_DISABLE_CACHE=1 node --trace-warnings -r babel-register ./internals/scripts/RunTests.js",
    "test-all": "npm run lint && npm run flow && npm run build && npm run test && npm run test-e2e",
    "test-e2e": "cross-env NODE_ENV=test BABEL_DISABLE_CACHE=1 node --trace-warnings -r babel-register ./internals/scripts/RunTests.js e2e",
    "test-watch": "npm test -- --watch"
  },
```

# npm install

```npm install``` 을 하면 package.json 파일에 근거에서 module들이  locally하게 설치된다.  
npm install 은 default 로 ```node-gyp rebuild```이 실행되는것 같다.( https://docs.npmjs.com/misc/scripts 참고 )  
package.json 의 script 파트에 prepublish, prepare, prepublishOnly 가 없으므로. postinstall 부분이 실행되는것 같다.  
Pre and post commands with matching names will be run for those as well (e.g. premyscript, myscript, postmyscript).
라는 문구로 봐서는 preinstall postinstall 을 package.json에서 찾아서 해당 command가 실행되는 것 같다.   

**postinstall** 이 있으니까 다음 command가 순서대로 실행될 것이다.  
<pre>
node -r babel-register internals/scripts/CheckNativeDep.js 
&& npm run <b>flow-typed</b> 
&& npm run <b>build-dll</b> 
&& electron-builder install-app-deps 
&& node node_modules/fbjs-scripts/node/check-dev-engines.js package.json
</pre>

**flow-typed** 이 있으니까 다음 command가 순서대로 실행될 것이다.  
<pre>
rimraf flow-typed/npm 
&& flow-typed install --overwrite 
|| true
</pre>

rimraf 모듈은 주어진 path에 있는 파일을 폴더를 지우는 모듈이다.  
그래서 *flow-typed/npm* 에 있는 것들을 지울 것이다.( ./node_modules/.bin/rimraf ./flow-typed/npm/ )  

flow-typed 모듈은 flow와 함께 사용할 3rd-party 라이브러리 인터페이스 정의 저장소란다.  
flow-typed is a repository of third-party library interface definitions for use with Flow.  
flow는 JavaScript코드를 위한 static type checker 란다. ( https://flow.org/ 참고 )

리눅스에서는 다중명령어(세미콜론, 파이브, &&, ||)가 있단다.( http://brownbears.tistory.com/205 참고 )  
더블앤퍼센트(&&)는 첫번째 명령이 에러없이 정상 종료해야 두번째 명령을 수행한다.  
더블버티칼바(||)는 첫번째 명령의 결과 에러가 발생해야 각각의 모든 명령을 수행한다

**build-dll** 이 있으니까 다음 command가 실행될 것이다. 
<pre>
cross-env NODE_ENV=development 
node --trace-warnings -r babel-register 
./node_modules/webpack/bin/webpack --config webpack.config.renderer.dev.dll.js --colors
</pre>

electron-builder 모듈은 좀 더 봐야 할 듯 하고. 일단 ```./node_modules/.bin/electron-builder -h```을 실행해보면. example 이 보인다. 
install-app-deps 모듈도 같이 사용되었다. ```./node_modules/.bin/install-app-deps -h```을 실행해보면 같이 사용하라는듯 하다. 
https://www.npmjs.com/package/electron-builder#quick-setup-guide 에 postinstall 에 추가하란 이야기도 있다. 

```./node_modules/.bin/electron-builder --armv7l```으로 실행해보았으나 실패함. 


# npm run build

```npm run build``` 를 하면 npm run build-main 과 npm run build-render 가 concurrently하게 진행됨. 

<pre>
./node_modules/.bin/concurrently "npm run <b>build-main</b>" "npm run <b>build-renderer</b>"
</pre>

**build-main** 이 있으니까 다음 command가 실행될 것이고.
<pre>
cross-env NODE_ENV=production 
node --trace-warnings -r babel-register 
./node_modules/webpack/bin/webpack --config webpack.config.main.prod.js --colors
</pre>

**build-render** 도 있으니 다음 command가 실행될 것이고.
<pre>
cross-env NODE_ENV=production 
node --trace-warnings -r babel-register 
./node_modules/webpack/bin/webpack --config webpack.config.renderer.prod.js --colors
</pre>

# npm run dev

```npm run dev``` 를 하면 다음 command가 순서대로 실행 될 것이다.  

<pre>
cross-env START_HOT=1 node -r babel-register ./internals/scripts/CheckPortInUse.js 
&& cross-env START_HOT=1 npm run <b>start-renderer-dev</b>
</pre>

```./node_modules/.bin/cross-env START_HOT=1 node -r babel-register ./internals/scripts/CheckPortInUse.js``` 실행하고  
```./node_modules/.bin/cross-env START_HOT=1 npm run start-renderer-dev``` 을 실행하는 것과 같음  
(&& waits for the first command to finish before starting the second command and a watcher task will never finish.)
&& 연산자를 통해서 첫번째 명령어가 끝나야 두번재 명령어를 시작함. 두번째 명령어에는 ```npm run start-renderer-dev``` 이 있음. 

node를 -r 옵션과 같이 사용하면 preload 하고자 하는 module 를 지정할 수 있음. -r module_name 은 반복할 수 있음. 
babel-register 모듈을 로딩한 후에 CheckPortInUse.js 를 실행한다는 소리임. preload가 없으면 import chalk from 'chalk' 구문에서 에러가 났음. 

**start-renderer-dev**
<pre>
cross-env NODE_ENV=development 
node --trace-warnings -r babel-register 
./node_modules/webpack-dev-server/bin/webpack-dev-server --config webpack.config.renderer.dev.js
</pre>

webpack.config.renderer.dev.js 파일에서 child process를 생성하는 코드가 있음. child_process.spawn(command,args,options)에 관해서는 node 문서를 참고할것.
npm run start-main-dev 로 child process를 생성함. 

**start-main-dev** 

<pre>
cross-env HOT=1 NODE_ENV=development 
electron -r babel-register ./app/main.dev
</pre>

```./node_modules/.bin/cross-env HOT=1 NODE_ENV=development electron -r babel-register ./app/main.dev```




cross-env 다음에 key=value 를 여러개 넣을수 있음. space를 구분자로해서. 
node [옵션]

electron 도 -r 옵션을 주고 실행할 수 있음. 



```npm run start``` 를 하면 npm run prestart 하고, npm run start 하고, npm run poststart 를 실행하는듯하다. 
(https://docs.npmjs.com/misc/scripts 참고)
