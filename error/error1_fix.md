docs/error/error1.md

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
[0] Hash: 41d16586f231e570ff50
[0] Version: webpack 3.10.0
[0] Time: 2996ms
[0]                  Asset     Size  Chunks             Chunk Names
[0]     ./app/main.prod.js  62.6 kB       0  [emitted]  main
[0] ./app/main.prod.js.map   246 kB       0  [emitted]  main
[0] [./app/main.dev.js] ./app/main.dev.js 3.14 kB {0} [built]
[0] [./app/menu.js] ./app/menu.js 5.82 kB {0} [built]
[0]     + 32 hidden modules
[1] Hash: 7ce3aca70a0070ac482a
[1] Version: webpack 3.10.0
[1] Time: 2935ms
[1]                                  Asset      Size  Chunks                    Chunk Names
[1]   674f50d287a8c48dc19ba404d20fe713.eot    166 kB          [emitted]         
[1]   912ec66d7572ff821749319396470bde.svg    444 kB          [emitted]  [big]  
[1]   b06871f281fee6b241d60582ae9369b9.ttf    166 kB          [emitted]         
[1] af7ae505a9eed503f8b8e6982036873e.woff2   77.2 kB          [emitted]         
[1]  fee66e712a8a08eef5805a46892932ad.woff     98 kB          [emitted]         
[1]                       renderer.prod.js   10.1 kB       0  [emitted]         main
[1]                              style.css   32.1 kB       0  [emitted]         main
[1]                   renderer.prod.js.map   17.7 kB       0  [emitted]         main
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
[1]     + 25 hidden modules
[1] Child extract-text-webpack-plugin node_modules/extract-text-webpack-plugin/dist node_modules/css-loader/index.js??ref--2-1!app/components/Counter.css:
[1]        2 modules
[1] Child extract-text-webpack-plugin node_modules/extract-text-webpack-plugin/dist node_modules/css-loader/index.js??ref--2-1!app/components/Home.css:
[1]        2 modules
[1] Child extract-text-webpack-plugin node_modules/extract-text-webpack-plugin/dist node_modules/css-loader/index.js??ref--1-2!app/app.global.css:
[1]      5 assets
[1]     [./node_modules/css-loader/index.js?{"minimize":true}!./app/app.global.css] ./node_modules/css-loader?{"minimize":true}!./app/app.global.css 698 bytes {0} [built]
[1]         + 9 hidden modules
[0] npm run build-main exited with code 0
[1] npm run build-renderer exited with code 0
  • electron-builder version=19.52.1
  • loaded configuration file=package.json ("build" field)
  • electron-rebuild not required if you use electron-builder, please consider to remove excess dependency from devDependencies

To ensure your native dependencies are always matched electron version, simply add script `"postinstall": "electron-builder install-app-deps" to your `package.json`
  • writing effective config file=release/electron-builder.yaml
  • no native production dependencies
  • packaging       platform=linux arch=x64 electron=1.7.10 appOutDir=release/linux-unpacked
Downloading tmp-18082-1-SHASUMS256.txt-1.7.10
[============================================>] 100.0% of 2.96 kB (2.37 kB/s)
  • building        target=AppImage arch=x64 file=release/electron-react-boilerplate-1.0.0-x86_64.AppImage
  • downloading     path=/home/jinia/.cache/electron-builder/appimage/appimage-9.0.3 url=https://github.com/electron-userland/electron-builder-binaries/releases/download/appimage-9.0.3/appimage-9.0.3.7z
  • building embedded block map file=release/electron-react-boilerplate-1.0.0-x86_64.AppImage
  • downloading     path=/home/jinia/.cache/electron-builder/block-map-builder/block-map-builder-v0.2.0-x64 url=https://github.com/develar/block-map-builder/releases/download/v0.2.0/block-map-builder-v0.2.0-linux-x64.7z
  • building        target=deb arch=x64 file=release/electron-react-boilerplate_1.0.0_amd64.deb
  • downloading     path=/home/jinia/.cache/electron-builder/fpm/fpm-1.9.2-2.3.1-linux-x86_64 url=https://github.com/electron-userland/electron-builder-binaries/releases/download/fpm-1.9.2-2.3.1-linux-x86_64/fpm-1.9.2-2.3.1-linux-x86_64.7z
jinia@jin:~/Documents/GitHub/electron-react-boilerplate$ 
```

release 디렉토리에 파일이 생성되어 있음. 이걸 실행하면 됨.

```
jinia@jin:~/Documents/GitHub/electron-react-boilerplate/release$ ls -al
total 101300
drwxr-xr-x  3 jinia jinia     4096 Jan  9 18:33 .
drwxrwxr-x 12 jinia jinia     4096 Jan  9 18:32 ..
-rw-r--r--  1 jinia jinia      454 Jan  9 18:05 electron-builder.yaml
-rw-r--r--  1 jinia jinia 41658332 Jan  9 18:33 electron-react-boilerplate_1.0.0_amd64.deb
-rwxr-xr-x  1 jinia jinia 62047705 Jan  9 18:25 electron-react-boilerplate-1.0.0-x86_64.AppImage
-rw-r--r--  1 jinia jinia      416 Jan  9 18:33 latest-linux.yml
drwxr-xr-x  4 jinia jinia     4096 Jan  9 18:21 linux-unpacked
jinia@jin:~/Documents/GitHub/electron-react-boilerplate/release$ ls linux-unpacked/ -al
total 130460
drwxr-xr-x 4 jinia jinia     4096 Jan  9 18:21 .
drwxr-xr-x 3 jinia jinia     4096 Jan  9 18:33 ..
-rw-r--r-- 1 jinia jinia    24844 Dec 18 19:24 blink_image_resources_200_percent.pak
-rw-r--r-- 1 jinia jinia       15 Dec 18 19:24 content_resources_200_percent.pak
-rw-r--r-- 1 jinia jinia 12032534 Dec 18 19:24 content_shell.pak
-rwxr-xr-x 1 jinia jinia 83392984 Dec 18 19:32 electron-react-boilerplate
-rw-r--r-- 1 jinia jinia 10130560 Dec 18 19:24 icudtl.dat
-rw-r--r-- 1 jinia jinia  2980664 Dec 18 19:32 libffmpeg.so
-rwxr-xr-x 1 jinia jinia 21136056 Dec 18 19:32 libnode.so
-rw-r--r-- 1 jinia jinia     1060 Dec 18 19:21 LICENSE.electron.txt
-rw-r--r-- 1 jinia jinia  1775951 Dec 18 19:23 LICENSES.chromium.html
drwxr-xr-x 2 jinia jinia     4096 Jan  9 18:21 locales
-rw-r--r-- 1 jinia jinia   262947 Dec 18 19:24 natives_blob.bin
-rw-r--r-- 1 jinia jinia   140979 Dec 18 19:26 pdf_viewer_resources.pak
drwxr-xr-x 2 jinia jinia     4096 Jan  9 18:21 resources
-rw-r--r-- 1 jinia jinia  1448208 Dec 18 19:24 snapshot_blob.bin
-rw-r--r-- 1 jinia jinia   151829 Dec 18 19:24 ui_resources_200_percent.pak
-rw-r--r-- 1 jinia jinia    57761 Dec 18 19:24 views_resources_200_percent.pak
jinia@jin:~/Documents/GitHub/electron-react-boilerplate/release$ 
jinia@jin:~/Documents/GitHub/electron-react-boilerplate/release$ ./linux-unpacked/electron-react-boilerplate 
```


