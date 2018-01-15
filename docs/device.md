#CodalDevice

##Overview

Although the runtime is built from lots of small components, we also provide an easy to use pre-packaged collection of the commonly used components
all in one place. This makes it much easier to start programming your micro:bit in C.

This grouping is provided by a C++ class called `CodalDevice`.  The `CodalDevice` class has a number of
member variables, that operate as device drivers to control the most commonly used features of the micro:bit.

There is an instance of the `CodalDevice` class created as a global variable in all the sample programs, called `device`:

>    device {<br/>
>    &emsp;&emsp;[.i2c](device/i2c.md),<br/>
>    &emsp;&emsp;[.serial](device/serial.md),<br/>
>    &emsp;&emsp;[.MessageBus](device/messageBus.md),<br/>
>    &emsp;&emsp;[.buttonA](device/button.md),<br/>
>    &emsp;&emsp;[.buttonB](device/button.md),<br/>
>    &emsp;&emsp;[.buttonAB](device/button.md),<br/>
>    &emsp;&emsp;[.accelerometer](device/accelerometer.md),<br/>
>    &emsp;&emsp;[.thermometer](device/thermometer.md),<br/>
>    &emsp;&emsp;[.io](device/io.md),<br/>
>    }

You can use dot operator '.' to any of these resources inside device to access any of the functions they provide. There is a complete list of the
functions available under the `device` menu item in the navigation bar at the top of the page.

For example, if we needed to scroll some text across the display, we simply would write the following:

```cpp
device.display.scroll("HELLO!");
```

Similarly, if we wanted to send some text over serial, we could write the following
code:

```cpp
for(int i = 3; i > 0; i--)
{
    device.serial.printf("%d...", i);
    device.sleep(1000);
}

// or alternatively...
device.serial.send("Code!");
```

The runtime also contains a scheduler, which uses lightweight threads (called fibers)
to control the rate of execution.

To place the current fiber into a power efficient <a href="#sleep">sleep</a> write the following:
```cpp
// where X is an integer in milliseconds for the amount of time you would like to sleep for.
device.sleep(X);
```

##Message Bus ID

> None

##Message Bus Events

> None

#API
[comment]: <> ({"className":"CodalDevice"})
[comment]: <> ({"end":"CodalDevice"})
