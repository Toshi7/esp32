
## For Ubuntu 

- Install [Arduino IDE](https://www.arduino.cc/en/Main/Software)
  - https://www.arduino.cc/en/Guide/Linux

- unzip the file by typing 
```
$ tar xvfJ arduino-1.8.5-linux64.tar.xz
```
- You need jdk to run Arduino IDE
```
$ sudo apt-get install openjdk-8-jre
```
- Environment setting
```
$ vim ~/.bashrc
```
- Add these two in very bottom
```
$ export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64
$ export PATH=$PATH:$JAVA_HOME/bin
```
```
$ source ~/.bashrc
```
- You can also write it in /etc/profile
Reference - [java開発ためのLinux環境のシステム環境変数の設定方法](https://51flya.com/linux/380.html) 
- If the way you change path in .bashrc and can't even execute ls command, you can type this and change your .bashrc back.
```
export PATH=/bin:/usr/bin:/usr/local/bin:/sbin:/usr/sbin
```
Reference - [After editing .bashrc commands return 'command could not be located because '/bin' is not included in the PATH'](https://askubuntu.com/questions/688318/after-editing-bashrc-commands-return-command-could-not-be-located-because-bi)

Reference - [bashrcへJAVA_HOMEの設定を追加する](http://forco.hateblo.jp/entry/2015/04/05/035621)  
Reference - [[Linux]PATHの設定方法](http://devb.hatenablog.com/entry/20101203/1291391256)
- Check the PATH and JAVA_HOME by typing thse below
```
$ echo $PATH
$ echo $JAVA_HOME
```
Execute command below to install Arduino IDE
```
$ ./install.sh
```

Reference - [1](sudo apt-get install openjdk-8-jre)

### Intalling Arduino core

- Go to [Setting up your arduino ide to connect to esp32](https://github.com/espressif/arduino-esp32#installation-instructions)
  - Choose [Instructions for Debian/Ubuntu Linux](https://github.com/espressif/arduino-esp32/blob/master/docs/arduino-ide/debian_ubuntu.md)
  - Execute this command below 
    ```
    sudo usermod -a -G dialout $USER && \
    sudo apt-get install git && \
    wget https://bootstrap.pypa.io/get-pip.py && \
    sudo python get-pip.py && \
    sudo pip install pyserial && \
    mkdir -p ~/Arduino/hardware/espressif && \
    cd ~/Arduino/hardware/espressif && \
    git clone https://github.com/espressif/arduino-esp32.git esp32 && \
    cd esp32 && \
    git submodule update --init --recursive && \
    cd tools && \
    python3 get.py
    ```
    
- Change the Board and Port
- [Reference](https://www.mgo-tec.com/arduino-core-esp32-install)
