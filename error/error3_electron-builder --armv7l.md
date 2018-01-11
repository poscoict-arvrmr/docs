
<pre>
jinia@jin:~/Documents/GitHub/electron-react-boilerplate$ ./node_modules/.bin/electron-builder --armv7l
  • electron-builder version=19.52.1
  • loaded configuration file=package.json ("build" field)
  • writing effective config file=release/electron-builder.yaml
  • installing production dependencies platform=linux arch=armv7l appDir=/home/jinia/Documents/GitHub/electron-react-boilerplate/app
  • packaging       platform=linux arch=armv7l electron=1.7.10 appOutDir=release/linux-armv7l-unpacked
  • building        target=AppImage arch=armv7l file=release/electron-react-boilerplate-1.0.0-armv7l.AppImage
Error: Exit code: 1. Command failed: /home/jinia/.cache/electron-builder/appimage/appimage-9.0.3/linux-x64/appimagetool --runtime-file /home/jinia/.cache/electron-builder/appimage/appimage-9.0.3/runtime-armv7l --no-appstream /home/jinia/Documents/GitHub/electron-react-boilerplate/release/__appImage-armv7l /home/jinia/Documents/GitHub/electron-react-boilerplate/release/electron-react-boilerplate-1.0.0-armv7l.AppImage
Using architecture ARM
Deleting pre-existing .DirIcon
Creating .DirIcon symlink based on information from desktop file
Generating squashfs...
Unable to load provided runtime file

WARNING: zsyncmake is missing, please install it if you want to use binary delta updates
/home/jinia/Documents/GitHub/electron-react-boilerplate/release/__appImage-armv7l should be packaged as /home/jinia/Documents/GitHub/electron-react-boilerplate/release/electron-react-boilerplate-1.0.0-armv7l.AppImage

Using architecture ARM
Deleting pre-existing .DirIcon
Creating .DirIcon symlink based on information from desktop file
Generating squashfs...
Unable to load provided runtime file

    at /home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/builder-util/src/util.ts:122:16
    at ChildProcess.exithandler (child_process.js:282:5)
    at emitTwo (events.js:126:13)
    at ChildProcess.emit (events.js:214:7)
    at maybeClose (internal/child_process.js:925:16)
    at Socket.stream.socket.on (internal/child_process.js:346:11)
    at emitOne (events.js:116:13)
    at Socket.emit (events.js:211:7)
    at Pipe._handle.close [as _onclose] (net.js:554:12)
From previous event:
    at exec (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/builder-util/src/util.ts:85:3)
    at /home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/src/targets/AppImageTarget.ts:107:5
    at Generator.next (<anonymous>)
    at /home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/graceful-fs/graceful-fs.js:99:16
    at /home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/graceful-fs/graceful-fs.js:43:10
    at FSReqWrap.oncomplete (fs.js:135:15)
From previous event:
    at AppImageTarget.build (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/out/targets/AppImageTarget.js:186:11)
    at taskManager.addTask.default.map.it (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/src/platformPackager.ts:121:67)
From previous event:
    at LinuxPackager.packageInDistributableFormat (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/src/platformPackager.ts:121:23)
    at /home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/src/platformPackager.ts:116:10
    at Generator.next (<anonymous>)
    at runCallback (timers.js:789:20)
    at tryOnImmediate (timers.js:751:5)
    at processImmediate [as _immediateCallback] (timers.js:722:5)
From previous event:
    at LinuxPackager.pack (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/out/platformPackager.js:195:11)
    at /home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/electron-builder-lib/src/packager.ts:355:24
    at Generator.next (<anonymous>)
    at xfs.stat (/home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/fs-extra-p/node_modules/fs-extra/lib/mkdirs/mkdirs.js:56:16)
    at /home/jinia/Documents/GitHub/electron-react-boilerplate/node_modules/graceful-fs/polyfills.js:287:18
    at FSReqWrap.oncomplete (fs.js:153:5)
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
jinia@jin:~/Documents/GitHub/electron-react-boilerplate$ 

</pre>
