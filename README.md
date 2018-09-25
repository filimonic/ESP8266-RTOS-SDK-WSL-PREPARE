# Install WSL:

Run Powershell.exe under Administrator

Run command:
```
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```
Reboot

# Install Debian WSL

Go to https://www.microsoft.com/en-us/p/debian-gnu-linux/9msvkqc78pk6

Click Get

# Run Debian WSL

Create a user for Debian WSL

Create password for your user

# Make your SUDO session ok:
```
echo "${USER} ALL=(ALL) NOPASSWD:ALL" | sudo tee /etc/sudoers.d/${USER}
```
# Go	 
```
echo '#!/bin/sh' > ~/esp8266i.sh
echo 'mkdir ~/esp' >> ~/esp8266i.sh
echo 'sudo apt-get -y update' >> ~/esp8266i.sh
echo 'sudo apt-get -y upgrade' >> ~/esp8266i.sh
echo "echo 'sudo chmod --changes 666 /dev/ttyS*' >> ~/.profile" >> ~/esp8266i.sh
echo 'sudo apt-get -y install git build-essential bison flex libncurses-dev gperf python python-serial' >> ~/esp8266i.sh
echo 'cd ~/esp' >> ~/esp8266i.sh
echo 'git clone https://github.com/espressif/ESP8266_RTOS_SDK.git' >> ~/esp8266i.sh
echo 'wget https://dl.espressif.com/dl/xtensa-lx106-elf-linux64-1.22.0-88-gde0bdc1-4.8.5.tar.gz' >> ~/esp8266i.sh
echo 'tar -zxf xtensa-lx106-elf-linux64-1.22.0-88-gde0bdc1-4.8.5.tar.gz' >> ~/esp8266i.sh
echo 'rm -f xtensa-lx106-elf-linux64-1.22.0-88-gde0bdc1-4.8.5.tar.gz' >> ~/esp8266i.sh
echo "echo 'export IDF_PATH=~/esp/ESP8266_RTOS_SDK' >> ~/.profile" >> ~/esp8266i.sh
echo "echo 'export PATH=\$PATH:~/esp/xtensa-lx106-elf/bin' >> ~/.profile" >> ~/esp8266i.sh
chmod +x ~/esp8266i.sh
~/esp8266i.sh
rm -f ~/esp8266i.sh

```
