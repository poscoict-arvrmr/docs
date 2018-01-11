
npm run dev on windows 7 (32bit).
- does not show React, Redux tab on developter tools. Shows the tabs until Devtron.

<pre>
> electron-react-boilerplate@0.12.0 start-main-dev C:\Users\박 소선\Desktop\demo\elect-react-bp-test
> cross-env HOT=1 NODE_ENV=development electron -r babel-register ./app/main.dev

(node:11288) DeprecationWarning: Chunk.modules is deprecated. Use Chunk.getNumberOfModules/mapModules/forEachModule/containsModule instead.
    at C:\Users\박 소선\Desktop\demo\elect-react-bp-test\node_modules\extract-text-webpack-plugin\index.js:271:25
    at C:\Users\박 소선\Desktop\demo\elect-react-bp-test\node_modules\async\dist\async.js:3096:16
    at eachOfArrayLike (C:\Users\박 소선\Desktop\demo\elect-react-bp-test\node_modules\async\dist\async.js:1055:9)
    at eachOf (C:\Users\박 소선\Desktop\demo\elect-react-bp-test\node_modules\async\dist\async.js:1103:5)
    at Object.eachLimit (C:\Users\박 소선\Desktop\demo\elect-react-bp-test\node_modules\async\dist\async.js:3158:5)
    at ExtractTextPlugin.<anonymous> (C:\Users\박 소선\Desktop\demo\elect-react-bp-test\node_modules\extract-text-webpack-plugin\index.js:268:10)
    at Compilation.applyPluginsAsyncSeries (C:\Users\박 소선\Desktop\demo\elect-react-bp-test\node_modules\webpack\node_modules\tapable\lib\Tapable.js:206:13)
    at Compilation.seal (C:\Users\박 소선\Desktop\demo\elect-react-bp-test\node_modules\webpack\lib\Compilation.js:605:8)
    at applyPluginsParallel.err (C:\Users\박 소선\Desktop\demo\elect-react-bp-test\node_modules\webpack\lib\Compiler.js:504:17)
    at C:\Users\박 소선\Desktop\demo\elect-react-bp-test\node_modules\webpack\node_modules\tapable\lib\Tapable.js:289:11

Failed to fetch extension, trying 4 more times
Failed to fetch extension, trying 4 more times
Failed to fetch extension, trying 3 more times
Failed to fetch extension, trying 3 more times
Failed to fetch extension, trying 2 more times
Failed to fetch extension, trying 2 more times
Failed to fetch extension, trying 1 more times
Failed to fetch extension, trying 0 more times
{ Error: spawn UNKNOWN
    at exports._errnoException (util.js:1050:11)
    at ChildProcess.spawn (internal/child_process.js:319:11)
    at exports.spawn (child_process.js:390:9)
    at run (C:\Users\諛??뚯꽑\Desktop\demo\elect-react-bp-test\node_modules\cross-unzip\index.js:31:13)
    at forWin32 (C:\Users\諛??뚯꽑\Desktop\demo\elect-react-bp-test\node_modules\cross-unzip\index.js:17:3)
    at C:\Users\諛??뚯꽑\Desktop\demo\elect-react-bp-test\node_modules\electron-devtools-installer\dist\downloadChromeExtension.js:43:34
    at <anonymous> code: 'UNKNOWN', errno: 'UNKNOWN', syscall: 'spawn' }
Failed to fetch extension, trying 1 more times
Failed to fetch extension, trying 0 more times
</pre>


## looking for solutions 
- https://github.com/chentsulin/electron-react-boilerplate/issues/268
    - <i>electron-devtools-installer is a problem</i> :: I have it installed
    - <i>cannot connect chrome store</i> :: via normal chrome process, it opens on my laptop
- https://github.com/chentsulin/electron-react-boilerplate/issues/377
    - <i>try PORT=1212 npm run dev</i> :: couldn't find a command to use instaed of PORT=1212 on windows..
    - <i>electron-devtools-installer and corp proxy not working nice together</i> :: probably my problem at this point..
 

