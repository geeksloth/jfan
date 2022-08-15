# JFAN (Automatic Jetson Fan Controller)
This is an extended version of [Pyrestone's jetson-fan-ctl](https://github.com/Pyrestone/jetson-fan-ctl). Adding some helpful configuration, e.g. FAN_MIN_SPEED, to PREVENT the fan stop working at a very low temperature (but still consume power without spinning).


## Installation
1. [Optional] Install **python3** if it is not installed.
```bash
sudo apt-get install python3-dev
```
2. Clone this repo
```bash
git clone https://github.com/geeksloth/jfan.git && cd jfan
```
3. Install by running:
```bash
sudo ./install.sh
```
4. [Optional] Check if the service running currectly:
```bash
sudo service jfan status
```


## Customization
Modify the configuration file as your desire:
```bash
sudo nano /etc/jfan/config.json
```
you will find the following lines:
```
{
  "FAN_OFF_TEMP": 35,
  "FAN_MAX_TEMP": 50,
  "FAN_MIN_SPEED": 100,
  "UPDATE_INTERVAL": 5,
  "MAX_PERF": 1
}
```
the ```"FAN_MIN_SPEED"``` stands for the 8-bit lowest to highest speed ranged from ```0-255```.
After modification finished, press ```ctrl + x``` and hit ```x``` to save and then restart the service:
```bash
sudo service jfan restart
```

To check everything is going fine:
```bash
sudo service jfan status
```

For the original script and description, please visit [Pyrestone's jetson-fan-ctl](https://github.com/Pyrestone/jetson-fan-ctl) page.
