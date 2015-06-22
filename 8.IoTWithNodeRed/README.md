Internet of Things with Intel Edison
=======

Intel Edison is a tiny computer, developed by Intel. This computer can be connected in wifi, so it's a great tool to work on the **Internet of Things** (or IoT).

![Intel Edison](http://www.seeedstudio.com/depot/images/102990161%201.jpg)

> This tutorial is written using Linux x64

[TOC]


###  Read an analog input ###

We're now going to see how to read an analog input of any sensor connected on the board.

First, plug your component (any sensor, really, that's not important, personally, I'm using a Rotary Angle Sensor,  [this one](https://software.intel.com/en-us/iot/hardware/sensors/grove-rotary-angle-sensor)).

Then, create a new file in the file root (**/home/root**). This will be the script.
Name it **analog.js** (This is just an example, the name isn't important at all, it just has to be a .js file).

Open it with your text editor. Now you can start programming on your board ! Exciting huh ?

So with the following script, you can display the values of the analog sensor plugged on the A0 input :

```js
    var m = require('mraa'); //require mraa
	console.log('MRAA Version: ' + m.getVersion()); //write the mraa version to the console

	var analogPin0 = new m.Aio(0); //setup access analog inpuput pin 0
	var analogValue = analogPin0.read(); //read the value of the analog pin
	var analogValueFloat = analogPin0.readFloat(); //read the pin value as a float
		console.log(analogValue); //write the value of the analog pin to the console
		console.log(analogValueFloat.toFixed(5)); //write the value in the float format
```

You can get the entire script [here](https://github.com/intel-iot-devkit/mraa/tree/master/examples/javascript), with some others too. Don't hesitate to check them.



Then, save the file and execute it via the Linux terminal :

```sh
    node analog.js
```

This will display the current value of the sensor !

> You can stop any node process by typing ctrl-c


##  Node-RED##
###  Installation###

This library is very useful. It allows you to create some applications related to the web. With this, your board can do some researches on different websites, send some emails, SMS or even tweets. You can literally do everything with this library, in particularly by creating your own components.
More informations [here](http://nodered.org/).

To install Node-RED, run ;

  ```sh
    npm install -g node-red
    node-red
```

Then type :

```
    ifconfig
```

And get the IP adress of your board. You can now use node-RED in your navigator by typing this adress in the search bar, with the 1880 port. (ex : 192.168.1.147:1880 for me)

###  Read an analog input###

We've seen how to read an analog value with the MRAA library. This is useful, but not as much as Node-RED !
With Node-RED, we can also read any analog sensor value, but we can use these values to create web applications !

> I'm now following another tutorial, you can find it [here](http://www.rs-online.com/designspark/electronics/eng/blog/wiring-the-internet-of-things-with-intel-edison-and-node-red).

First, I encourage you to learn how to use Node-RED, this shouldn't be very complicated.
You can use [this tutorial.](http://nodered.org/docs/getting-started/first-flow.html) It will show you how to create your firsts applications (or "flows") with Node-RED.

Once you've done that, we can start talking seriously ! ;-)

To read analog values with Node-RED, you need to download a now node.

Download these [two files.](https://github.com/abopen/node-red/tree/master/nodes)

Place them in the following directory : ***/usr/lib/node_modules_node-red/nodes***

Start (or restart) Node-RED.
You should now see a new node on the sidebar, named **"mraaAnalogRead"**. This node will allow you to read any analog value of any analog sensor plugged on your board.
