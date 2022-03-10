# **Lab 5**
## *Eclipse, Mosquitto and Eclipse Paho*
 ```ssh
$ brew install mosquitto
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab5/Images/install-mosquitto.png)

 ```ssh
$ brew services start mosquitto
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab5/Images/start-mosquitto.png)

 ```ssh
$ mosquitto_sub -h localhost -v -t test/topic &
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab5/Images/mosquitto-sub.png)

 ```ssh
$ mosquitto_pub -h localhost -t test/topic -m "Hello"
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab5/Images/mosquitto-pub.png)

 ```ssh
 $ sudo pip3 install -U paho-mqtt
 $ git clone https://github.com/eclipse/paho.mqtt.python.git
 $ cd ~/iot/lesson5
 $ python3 client.py
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab5/Images/install-paho.png)
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab5/Images/clone-eclipse.png)
 ![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab5/Images/client-py.png)

  ```ssh
$ python3 sub.py
$ python3 pub.py
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab5/Images/pub-sub.png)

```ssh
$ python3 sub-multiple.py
$ python3 pub-multiple.py
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab5/Images/pub-sub-multiple.png)

  ```ssh
$ python3 subcpu.py
$ python3 pubcpu.py
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab5/Images/pub-sub-cpu.png)

```ssh
$ nano subraspi.py
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab5/Images/nano-subraspi.png)

```ssh
$ nano pubraspi.py
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab5/Images/nano-pubraspi.png)

```ssh
$ python3 subraspi.py
$ python3 pubraspi.py
```
![This is an image](https://github.com/cupokoffi8/CPE-322/blob/main/Labs/Lab5/Images/pub-sub-raspi.png)
