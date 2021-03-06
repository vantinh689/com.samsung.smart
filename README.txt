To install the device, the TV(s) must be turned on and on the same network as the Homey.

Searching for the TV(s) might take up to 30 seconds.  If the TV is not found, the IP address can be set manually.

To be able to turn the TV on, it must support wake-on-lan / wake-on-wireless.

Device: Samsung:

For newer TVs, that respond to http://TV-IP-ADDRESS:8001/api/v2/

Device: Samsung (encrypted):

For H, HU, J, JU and JS models, that respond to http://TV-IP-ADDRESS:8001/ms/1.0/

Device: Samsung (legacy):

For older TVs, that respond to port 55000.


Details about actions:

Change channel:

The 'Change channel' action will send a list of number-keys for the channel number, and finally the 'Enter'-key.  The default delay between each key is 1250 ms, but this can be changed in 'Advanced settings'.

Example: switch to channel '123':

Will send this list of keys: 'Key 1', 'Key 2', 'Key 3', 'Enter'.


Send list of keys:

With the 'Send list of keys' action it is possible to send a list of keys, with a short delay between each key.  The default delay between each key is 100 ms, but this can be changed in 'Advanced settings'.  If the delay is too low, the TV might not respond.

For the list of keys, see [here](./keys.md). 

To send the same key several times, add a *X after the key, where X is the number of times for the key.  To add an extra delay before the next key, just add a number between 1 - 9999. The number is milliseconds.

Example: Send 'Home', 'Left' and 'Enter':

KEY_HOME,KEY_LEFT,KEY_ENTER

Example: Set the aspect ratio, increase the volume 10 times, wait 2.5 seconds (2500 ms) and then press play:

KEY_16_9,KEY_VOLUP*10,2500,KEY_PLAY


Launch video on YouTube (Samsung, Samsung Encrypted):

To use the 'Launch video on YouTube' action, the YouTube _video id_ must be provided, which is a 11 character long string.  The video id for this link on YouTube:

https://www.youtube.com/watch?v=aqz-KE-bpKQ

is aqz-KE-bpKQ


Details about Advanced settings:

IP address:

The IP address of the TV.

Can be updated manually if the TV was not found or if the IP address of the TV has changed. 

For the "Samsung (encrypted)" - device, it is not possible to change the IP address.


Secure connection (Samsung):

Used to enable a secure connection to the TV. Normally this is set correctly when adding the device.

Frame TV support:

To be able to turn off 'The Frame', enable this.


Polling interval for TV status:

Interval between each time the status of the TV (on / off) is checked, in seconds.

A value lower than 10 seconds will disable the polling.


Delay between keys:

The delay in milliseconds between each key is sent, for the 'Send list of keys' - action.

Default is 100 ms. 

If the value is too low, some or all of the commands might be ignored by the TV.


Delay between channel keys:

The delay in milliseconds between each key is sent, for the 'Change channel' - action. 

Default is 1250 ms.


SmartThings API:

To use the SmartThings API, your TV must be logged into your Samsung account.

Go to https://account.smartthings.com/tokens to generate a token with device access.

Go to advanced settings for the Samsung device, enable SmartThings API and enter the token.

This will enable the 'Set input source' - action.


Acknowledgements:

Thanks to https://github.com/natalan/samsung-remote for solution to support older Samsung TVs.

Thanks to https://github.com/tavicu/homebridge-samsung-tizen for solution to pair with newer Samsung TVs.

Thanks to https://github.com/tdudek/samsung-remote-models-2014-and-newer and https://github.com/kkapitan/homebridge-homesung for solution to pair with H, HU, J, JU and JS models. 


Disclaimer:

Use at your own risk. I accept no responsibility for any damages caused by using this app.

Some TVs use a different type of pairing, and are therefore not supported at the moment.
