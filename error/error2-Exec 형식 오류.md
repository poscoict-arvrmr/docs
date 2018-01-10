
LG15UB47Q 노트북에서 electron-react-boilerplate 를 가지고 ```npm run package``` 를 실행해서 
그 결과물을 라즈베리로 가져왔음. 

```
pi@raspberrypi:~/Downloads/second $ ls -al
합계 60612
drwxr-xr-x 3 pi pi     4096  1월 10 09:42 .
drwxr-xr-x 5 pi pi     4096  1월 10 09:36 ..
-rwxr-xr-x 1 pi pi 62047705  1월 10 09:37 electron-react-boilerplate-1.0.0-x86_64.AppImage
drwxr-xr-x 4 pi pi     4096  1월 10 09:42 linux-unpacked
pi@raspberrypi:~/Downloads/second $ ls -al linux-unpacked/
합계 189740
drwxr-xr-x 4 pi pi     4096  1월 10 09:42 .
drwxr-xr-x 3 pi pi     4096  1월 10 09:42 ..
-rw-r--r-- 1 pi pi     1060 12월 18 19:21 LICENSE.electron.txt
-rw-r--r-- 1 pi pi  1775951 12월 18 19:23 LICENSES.chromium.html
-rw-r--r-- 1 pi pi    24844 12월 18 19:24 blink_image_resources_200_percent.pak
-rw-r--r-- 1 pi pi       15 12월 18 19:24 content_resources_200_percent.pak
-rw-r--r-- 1 pi pi 12032534 12월 18 19:24 content_shell.pak
-rwxr-xr-x 1 pi pi 83392984 12월 18 19:32 electron-react-boilerplate
-rw-r--r-- 1 pi pi 10130560 12월 18 19:24 icudtl.dat
-rw-r--r-- 1 pi pi  2980664 12월 18 19:32 libffmpeg.so
-rwxr-xr-x 1 pi pi 21136056 12월 18 19:32 libnode.so
-rw-r--r-- 1 pi pi 60696222  1월 10 09:39 linux-unpacked.zip
drwxr-xr-x 2 pi pi     4096  1월  9 18:21 locales
-rw-r--r-- 1 pi pi   262947 12월 18 19:24 natives_blob.bin
-rw-r--r-- 1 pi pi   140979 12월 18 19:26 pdf_viewer_resources.pak
drwxr-xr-x 2 pi pi     4096  1월  9 18:21 resources
-rw-r--r-- 1 pi pi  1448208 12월 18 19:24 snapshot_blob.bin
-rw-r--r-- 1 pi pi   151829 12월 18 19:24 ui_resources_200_percent.pak
-rw-r--r-- 1 pi pi    57761 12월 18 19:24 views_resources_200_percent.pak
pi@raspberrypi:~/Downloads/second $ 
```

Exec 형식 오류메시지와 함께 실패

```
pi@raspberrypi:~/Downloads/second $ ./electron-react-boilerplate-1.0.0-x86_64.AppImage 
bash: ./electron-react-boilerplate-1.0.0-x86_64.AppImage: cannot execute binary file: Exec 형식 오류
pi@raspberrypi:~/Downloads/second $ cd linux-unpacked/
pi@raspberrypi:~/Downloads/second/linux-unpacked $ ls
pi@raspberrypi:~/Downloads/second/linux-unpacked $ ./electron-react-boilerplate 
bash: ./electron-react-boilerplate: cannot execute binary file: Exec 형식 오류
pi@raspberrypi:~/Downloads/second/linux-unpacked $ uname -a
Linux raspberrypi 4.9.73-v7+ #1072 SMP Sun Dec 31 19:37:41 GMT 2017 armv7l GNU/Linux
```
