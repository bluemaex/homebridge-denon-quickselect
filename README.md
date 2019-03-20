# homebridge-denon-quickselect

This is a homebridge plugin to quickly activate a quickselect on your Denon Receiver.

In order to make this useful, you should preset them once with the DenonAVR App.

### usage

Add as many accessoires as you want to your homebridge ``config.json`` in the way like this

```js
"accessories": [
    {
      "accessory": "denon-quickselect",
      "name": "AppleTV",
      "quickselect": 2,
      "host": "192.168.178.14",
      "zone": 1
    }
]
```` 

- Don't forget to add the IP address or the hostname of your receiver into the host parameter!
- For some models like (Denon X1400H) the ip alone does not work, you may need to specify the port too (like 192.168.178.14:8080) see [this issue for more details](https://github.com/bluemaex/homebridge-denon-quickselect/issues/3)
- Name is what will be shown inside homekit

#### optional pingUrl

There is one additional option that is called ``pingUrl``, you can use this to send any HTTP GET request for either logging, or waking up devices or whatever you want to do.

For example if you have an AppleTV that is in sleep mode and you want to wake it up when you activate the QuickSelect you could add this following line to your accessory: 

```js
  "pingUrl": "http://your.apple.tv.ip:3689/",
````

Et voila.
