
```bash
pi@raspberrypi:~ $ sudo python3 second.py 
Traceback (most recent call last):
  File "second.py", line 4, in <module>
    import paho.mqtt.client as mqtt
ImportError: No module named 'paho'
pi@raspberrypi:~ $ 
```


```bash
pi@raspberrypi:~ $ cat second.py 
#!/usr/bin/env python
import skywriter
import signal
import paho.mqtt.client as mqtt

broker_address="127.0.0.1"
print("creating new client instance")
client = mqtt.Client("Pi")
client.connect(broker_address, 1883)

@skywriter.double_tap()
def doubletap(position):
	client.publish("gesture/state", "double tap")
	print('Double tap!', position)

@skywriter.tap()
def tap(position):
    if position=='west':
        client.publish("gesture/state", "right")
    elif position=='east':
        client.publish("gesture/state", "left")
    print('Tap!', position)
signal.pause()
pi@raspberrypi:~ $ 

```

```bash
pi@raspberrypi:~ $ pip install paho-mqtt
Collecting paho-mqtt
  Downloading paho-mqtt-1.3.1.tar.gz (80kB)
    100% |████████████████████████████████| 81kB 311kB/s 
Building wheels for collected packages: paho-mqtt
  Running setup.py bdist_wheel for paho-mqtt ... done
  Stored in directory: /home/pi/.cache/pip/wheels/20/d8/0d/acdc8f2890111b7be7de71deebef0642fb83be0313dfff0493
Successfully built paho-mqtt
Installing collected packages: paho-mqtt
Successfully installed paho-mqtt-1.3.1
pi@raspberrypi:~ $ 
```

```bash
pi@raspberrypi:~ $ sudo pip3 install paho-mqtt
Collecting paho-mqtt
  Downloading paho-mqtt-1.3.1.tar.gz (80kB)
    100% |████████████████████████████████| 81kB 352kB/s 
Building wheels for collected packages: paho-mqtt
  Running setup.py bdist_wheel for paho-mqtt ... done
  Stored in directory: /root/.cache/pip/wheels/20/d8/0d/acdc8f2890111b7be7de71deebef0642fb83be0313dfff0493
Successfully built paho-mqtt
Installing collected packages: paho-mqtt
Successfully installed paho-mqtt-1.3.1
pi@raspberrypi:~ $ 
```

