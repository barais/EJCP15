Internet of Things with Intel Edison
=======

Intel Edison is a tiny computer, developed by Intel. This computer can be connected in wifi, so it's a great tool to work on the **Internet of Things** (or IoT).

![Intel Edison](http://www.seeedstudio.com/depot/images/102990161%201.jpg)


#Your own component in typescript on top of MRAA

This project provides a simple example of  Kevoree Component written in typescript. This component use  MRAA to get value from Edison.

[Source code for the component](https://github.com/barais/EJCP15/blob/master/7.IotWithEdison/examples/src/headstempcomp/lib/HeadsTempEdisonComp.ts)

To build your project

```sh
npm install
grunt
```

To run your component, copy gen folder to edison using scp.

```sh
cd gen/src/headstempcomp
npm install mraa
npm install
grunt kevoree
```


Copy this example and build a simple component that get data from sensors in taking information from MRAA.
