# Bluetooth device (BLE or not) scanner for EDOMI home automation 

* Class BTdaemon purpose: Scan Bluetooth devices on the network and notify a controller when registered devices are in range<br/>

Can work with Bluetooth LE (BLE) or normal (BT) devices<br/>
Controller is any system having an http API to settle devices ON & OFF<br/>
Primary controller configured with this script is EDOMI - but it can easily be adapted<br/>
EDOMI Remote API is used to control tag widgets<br/>
This script can run on a Raspberry PI 3 or any other Raspberry equipped with the BLE USB adapter.<br/>
This script is intended to run in CLI mode as a background daemon (via pcntl_fork())<br/>
$ php BTdaemon.php<br/>

*	Configuration:<br/>
Debug mode is selected when an instance of this class is created $ble = new BLE(debug_mode)<br/>
It is advised to start in debug mode to check everything is fine, then turn debug off<br/>
$ php BTdaemon.php start -> Start daemon<br/>
$ php BTdaemon.php stop -> Stop daemon<br/>
$ php BTdaemon.php conf -> Start configuration of your Bluetooth devices and EDOMI Remote API calls<br/>

*	Tested with:<br/>
Raspberry PI 3 - Raspbian Stretch<br/> 
BLE devices: Gigaset g-Tag, Gigaset Keeper<br/>
BT devices: none so far<br/>

* Link with the EDOMI<br/>
Define a Remote iKO per BT device you want to track<br/>
When started in configuration mode, the script will ask for the list of Bluetooth devices to monitor (via their BT Mac address)<br/>
For each registered devices, the EDOMI Remote iKO will be asked and stored into a BLE.ini file<br/>

* Optionally a log file is generated to keep track of devices entering or leaving the adapter scan range<br/>

* More information via EDOMI forum (German forum)<br/>
https://knx-user-forum.de/forum/projektforen/edomi<br/>
User: jonofe<br/>

<img src=https://github.com/jonofe/Bluetooth-scanner/blob/master/images/keeper1.jpg>
<img src=https://github.com/jonofe/Bluetooth-scanner/blob/master/images/gtag.jpg>
  