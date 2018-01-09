
"electron-react-boilerplate"
-> no such file or directory


```
jinia@jin:~/Documents/GitHub/electron-react-boilerplate$ npm run package

> electron-react-boilerplate@0.13.0 package /home/jinia/Documents/GitHub/electron-react-boilerplate
> npm run build && build --publish never


> electron-react-boilerplate@0.13.0 build /home/jinia/Documents/GitHub/electron-react-boilerplate
> concurrently "npm run build-main" "npm run build-renderer"

[0] 
[0] > electron-react-boilerplate@0.13.0 build-main /home/jinia/Documents/GitHub/electron-react-boilerplate
[0] > cross-env NODE_ENV=production node --trace-warnings -r babel-register ./node_modules/webpack/bin/webpack --config webpack.config.main.prod.js --colors
[0] 
[1] 
[1] > electron-react-boilerplate@0.13.0 build-renderer /home/jinia/Documents/GitHub/electron-react-boilerplate
[1] > cross-env NODE_ENV=production node --trace-warnings -r babel-register ./node_modules/webpack/bin/webpack --config webpack.config.renderer.prod.js --colors
[1] 
[0] Hash: a71289037ce1b3b5a2a6
[0] Version: webpack 3.10.0
[0] Time: 3997ms
[0]                  Asset     Size  Chunks             Chunk Names
[0]     ./app/main.prod.js  95.3 kB       0  [emitted]  main
[0] ./app/main.prod.js.map   413 kB       0  [emitted]  main
[0] [./app/main.dev.js] ./app/main.dev.js 3.14 kB {0} [built]
[0] [./app/menu.js] ./app/menu.js 5.82 kB {0} [built]
[0]     + 44 hidden modules
[0] npm run build-main exited with code 0
[1] Hash: 5e0eb472cc47a25a2727
[1] Version: webpack 3.10.0
[1] Time: 7812ms
[1]                                  Asset      Size  Chunks                    Chunk Names
[1]   674f50d287a8c48dc19ba404d20fe713.eot    166 kB          [emitted]         
[1]   912ec66d7572ff821749319396470bde.svg    444 kB          [emitted]  [big]  
[1]   b06871f281fee6b241d60582ae9369b9.ttf    166 kB          [emitted]         
[1] af7ae505a9eed503f8b8e6982036873e.woff2   77.2 kB          [emitted]         
[1]  fee66e712a8a08eef5805a46892932ad.woff     98 kB          [emitted]         
[1]                       renderer.prod.js    207 kB       0  [emitted]         main
[1]                              style.css   32.1 kB       0  [emitted]         main
[1]                   renderer.prod.js.map    590 kB       0  [emitted]         main
[1]                          style.css.map  86 bytes       0  [emitted]         main
[1] [./app/actions/counter.js] ./app/actions/counter.js 836 bytes {0} [built]
[1] [./app/app.global.css] ./app/app.global.css 41 bytes {0} [built]
[1] [./app/containers/App.js] ./app/containers/App.js 1.49 kB {0} [built]
[1] [./app/containers/CounterPage.js] ./app/containers/CounterPage.js 1.05 kB {0} [built]
[1] [./app/containers/HomePage.js] ./app/containers/HomePage.js 1.45 kB {0} [built]
[1] [./app/containers/Root.js] ./app/containers/Root.js 1.66 kB {0} [built]
[1] [./app/index.js] ./app/index.js 1.97 kB {0} [built]
[1] [./app/reducers/counter.js] ./app/reducers/counter.js 415 bytes {0} [built]
[1] [./app/reducers/index.js] ./app/reducers/index.js 548 bytes {0} [built]
[1] [./app/routes.js] ./app/routes.js 1.89 kB {0} [built]
[1] [./app/store/configureStore.js] ./app/store/configureStore.js 251 bytes {0} [built]
[1] [./app/store/configureStore.prod.js] ./app/store/configureStore.prod.js 897 bytes {0} [built]
[1] [./node_modules/css-loader/index.js?{"minimize":true}!./app/app.global.css] ./node_modules/css-loader?{"minimize":true}!./app/app.global.css 698 bytes [built]
[1] [./node_modules/webpack/buildin/module.js] (webpack)/buildin/module.js 517 bytes {0} [built]
[1]     + 127 hidden modules
[1] Child extract-text-webpack-plugin node_modules/extract-text-webpack-plugin/dist node_modules/css-loader/index.js??ref--2-1!app/components/Counter.css:
[1]        2 modules
[1] Child extract-text-webpack-plugin node_modules/extract-text-webpack-plugin/dist node_modules/css-loader/index.js??ref--2-1!app/components/Home.css:
[1]        2 modules
[1] Child extract-text-webpack-plugin node_modules/extract-text-webpack-plugin/dist node_modules/css-loader/index.js??ref--1-2!app/app.global.css:
[1]      5 assets
[1]     [./node_modules/css-loader/index.js?{"minimize":true}!./app/app.global.css] ./node_modules/css-loader?{"minimize":true}!./app/app.global.css 698 bytes {0} [built]
[1]         + 9 hidden modules
[1] npm run build-renderer exited with code 0
  • electron-builder version=19.52.1
  • loaded configuration file=package.json ("build" field)
  • writing effective config file=release/electron-builder.yaml
  • installing production dependencies platform=linux arch=x64 appDir=/home/jinia/Documents/GitHub/electron-react-boilerplate/app
Error: /usr/bin/node exited with code 1
Output:

> electron-react-boilerplate@1.0.0 postinstall /home/jinia/Documents/GitHub/electron-react-boilerplate/app
> npm run electron-rebuild


> electron-react-boilerplate@1.0.0 electron-rebuild /home/jinia/Documents/GitHub/electron-react-boilerplate/app
> node -r babel-register ../internals/scripts/ElectronRebuild.js


Error output:
✖ Rebuild Failed

An unhandled error occurred inside electron-rebuild
ENOENT: no such file or directory, lstat '/home/jinia/Documents/GitHub/electron-react-boilerplate/app/node_modules'

Error: ENOENT: no such file or directory, lstat '/home/jinia/Documents/GitHub/electron-react-boilerplate/app/node_modules'
child_process.js:644
    throw err;
    ^

Error: Command failed: ../node_modules/.bin/electron-rebuild --parallel --force --types prod,dev,optional --module-dir .
✖ Rebuild Failed

An unhandled error occurred inside electron-rebuild
ENOENT: no such file or directory, lstat '/home/jinia/Documents/GitHub/electron-react-boilerplate/app/node_modules'

Error: ENOENT: no such file or directory, lstat '/home/jinia/Documents/GitHub/electron-react-boilerplate/app/node_modules'

    at checkExecSyncError (child_process.js:601:13)
    at execSync (child_process.js:641:13)
    at Object.<anonymous> (/home/jinia/Documents/GitHub/electron-react-boilerplate/internals/scripts/ElectronRebuild.js:12:1)
    at Module._compile (module.js:635:30)
    at loader (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/babel-register/lib/node.js:144:5)
    at Object.require.extensions.(anonymous function) [as .js] (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/babel-register/lib/node.js:154:7)
    at Module.load (module.js:554:32)
    at tryModuleLoad (module.js:497:12)
    at Function.Module._load (module.js:489:3)
    at Function.Module.runMain (module.js:676:10)
npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! electron-react-boilerplate@1.0.0 electron-rebuild: `node -r babel-register ../internals/scripts/ElectronRebuild.js`
npm ERR! Exit status 1
npm ERR! 
npm ERR! Failed at the electron-react-boilerplate@1.0.0 electron-rebuild script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.
npm WARN Local package.json exists, but node_modules missing, did you mean to install?
npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! electron-react-boilerplate@1.0.0 postinstall: `npm run electron-rebuild`
npm ERR! Exit status 1
npm ERR! 
npm ERR! Failed at the electron-react-boilerplate@1.0.0 postinstall script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.
npm WARN Local package.json exists, but node_modules missing, did you mean to install?

    at checkExecSyncError (child_process.js:601:13)
    at execSync (child_process.js:641:13)
    at Object.<anonymous> (/home/jinia/Documents/GitHub/electron-react-boilerplate/internals/scripts/ElectronRebuild.js:12:1)
    at Module._compile (module.js:635:30)
    at loader (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/babel-register/lib/node.js:144:5)
    at Object.require.extensions.(anonymous function) [as .js] (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/babel-register/lib/node.js:154:7)
    at Module.load (module.js:554:32)
    at tryModuleLoad (module.js:497:12)
    at Function.Module._load (module.js:489:3)
    at Function.Module.runMain (module.js:676:10)
    at ChildProcess.childProcess.once.code (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/builder-util/src/util.ts:241:14)
    at Object.onceWrapper (events.js:317:30)
    at emitTwo (events.js:126:13)
    at ChildProcess.emit (events.js:214:7)
    at maybeClose (internal/child_process.js:925:16)
    at Process.ChildProcess._handle.onexit (internal/child_process.js:209:5)
From previous event:
    at spawn (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/builder-util/src/util.ts:200:3)
    at installDependencies (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/src/util/yarn.ts:87:3)
    at /home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/src/util/yarn.ts:17:11
    at Generator.next (<anonymous>)
    at runCallback (timers.js:789:20)
    at tryOnImmediate (timers.js:751:5)
    at processImmediate [as _immediateCallback] (timers.js:722:5)
From previous event:
    at installOrRebuild (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/out/util/yarn.js:31:21)
    at /home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/src/packager.ts:433:7
    at Generator.next (<anonymous>)
From previous event:
    at Packager.installAppDependencies (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/out/packager.js:483:11)
    at /home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/src/packager.ts:347:20
    at Generator.next (<anonymous>)
From previous event:
    at Packager.doBuild (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/out/packager.js:419:11)
    at /home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/src/packager.ts:299:52
    at Generator.next (<anonymous>)
    at /home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/graceful-fs/graceful-fs.js:99:16
    at /home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/graceful-fs/graceful-fs.js:43:10
    at FSReqWrap.oncomplete (fs.js:135:15)
From previous event:
    at Packager._build (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/out/packager.js:363:11)
    at /home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/src/packager.ts:261:23
    at Generator.next (<anonymous>)
    at runCallback (timers.js:789:20)
    at tryOnImmediate (timers.js:751:5)
    at processImmediate [as _immediateCallback] (timers.js:722:5)
From previous event:
    at Packager.build (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/out/packager.js:319:11)
    at /home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder/src/builder.ts:310:40
    at Generator.next (<anonymous>)
From previous event:
    at _build (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder/out/builder.js:61:21)
    at build (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder/src/builder.ts:280:10)
    at then (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder/src/cli/cli.ts:49:4)
    at runCallback (timers.js:789:20)
    at tryOnImmediate (timers.js:751:5)
    at processImmediate [as _immediateCallback] (timers.js:722:5)
From previous event:
    at Object.args [as handler] (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder/src/cli/cli.ts:49:4)
    at Object.runCommand (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/yargs/lib/command.js:228:22)
    at Object.parseArgs [as _parseArgs] (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/yargs/yargs.js:1041:24)
    at Object.get [as argv] (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/yargs/yargs.js:957:21)
    at Object.<anonymous> (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder/src/cli/cli.ts:43:15)
    at Module._compile (module.js:635:30)
    at Object.Module._extensions..js (module.js:646:10)
    at Module.load (module.js:554:32)
    at tryModuleLoad (module.js:497:12)
    at Function.Module._load (module.js:489:3)
    at Function.Module.runMain (module.js:676:10)
    at startup (bootstrap_node.js:187:16)
    at bootstrap_node.js:608:3
npm ERR! code ELIFECYCLE
npm ERR! errno 1
npm ERR! electron-react-boilerplate@0.13.0 package: `npm run build && build --publish never`
npm ERR! Exit status 1
npm ERR! 
npm ERR! Failed at the electron-react-boilerplate@0.13.0 package script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.
jinia@jin:~/Documents/GitHub/electron-react-boilerplate$ 

```
