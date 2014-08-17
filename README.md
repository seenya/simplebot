# SimpleBot.

## Overview

This is one of the most simple robots you can make. Features are:

* quick to put together (about an hour)
* very hackable (it can be built with cardboard or laser cut so very easily modifiable)
* can move pretty fast (at full tilt it will go about half a metre a second - faster with more juice for the servos!)
* very extendable (much of the magic happens in code and sensors can be easily fed in)
* Cheap (costs about $100 which is very cheap for your first robot)

This bot is an adaptation of the excellent [SumoBot Jr](https://github.com/makenai/sumobot-jr/) made by [Paweł Szymczykowski](http://twitter.com/makenai) but doesn't require laser cutting wood or plastic though you can if you want something a bit more long lasting.

## Capabilities

This is a tethered robot, meaning it stays connected to your computer via a USB cable. This means you can get your computer to do all the hard work to provide interface control (say a web page or an app) and processing (computer vision if you attached a webcam for example!).

This is the very first prototype, put together in about 30 minutes one evening.

![SimpleBot](img/simplebot-proto.jpg)


Once done you can reuse all of the components to make a bigger, badder, faster robot and switch the cardboard for more durable elements such as laser cut wood or plastic if you desire. We've even supplied the SVG and DXF files to do exactly that.

## Materials needed

The following are the various components you need to get hold of to make your SimpleBot:

* An Arduino - just about any type will do. We use Arduino Nanos because they are small and relatively inexpensive, but an Uno, Eleven, LeoStick or other Arduino will work just as well.
* 4xAA Battery holder - Provides the power for your motots. You'll want some batteries too - rechargables are best if you can afford them.
* Mini Breadboard - This allows you to wire things together without soldering. There's plenty of colours to choose from.
* 2x Continuous Rotation Servos - These drive the wheels. *Don't for get you need two or you'll be making a unicycle-bot*
* Jumper wire - Wire to connect everything together. A mix of MM, MF and FF is good to you can connect jumpers to different types of pins.
* Ultrasonic Range Finder (also called a ping sensor) - This allows your bot to detect how far things are away using sonar.


### Suppliers

There are a range of suppliers you can get things from. Here are a selection:

[JayCar](http://www.jaycar.com.au) provide a range of basic components but not the full range. Mostly good for basics like wire and tools.

[Freetronics](http://www.freetronics.com) are a local Melbourne hardware design business. They produce some of the highest quality electronics in the world and they do it all Open Source. They even build satellites! If you're [just after an arduino](http://www.freetronics.com/collections/arduino/products/eleven#.UjuVQxIW3S0) and not the whole bot then support an Aussie business doing high tech work.

[LittleBird Electronics](http://littlebirdelectronics.com) has been a big part of the maker community over the last few years, they carry a big range of components and they have excellent customer service. (Total price from LBE is about $90)
 
[TronixLabs](http://tronixlabs.com/) are a Melbourne-based supplier who stock enthusiast and hobbyist electronics, robotics, single-board computers etc, and you can find equivalent parts listed [here](http://tronixlabs.com/nodebots/). (Total price from TronixLabs: $65)

We'll have cardboard, cable ties and other prototyping stuff available on NBD to help build your very own bot but other things you might want to bring could include:

* Laser pointer to make an annoying cat toy.
* Stickers to bling out your bot.
* Spikes to take out others; Ben Hur or Mad Max style.
* USB WebCam if you want to give your bot some vision.
* USB cable extender if you want some range.

# SETUP

To setup your SimpleBot we're assuming you have Arduino and NodeJS installed already. If you haven't, check out the [prerequisites](https://github.com/nodebotsau/nbdau/blob/master/setup.md).

If you're using a LeoStick arduino follow the notes immediately below. If not, skip to "flashing my arduino" below.

## Set up your LeoStick

You'll need to get your Arduino IDE to be able to talk to your leostick. In the leostick folder there is a file called boards.txt - copy the content of this file into the bottom of your arduino boards.txt file. Ask about or google this before you do it.

Restart your arduino IDE and you should now see LeoStick v1.0 and LeoStick v2.0 in your lists of boards. Choose V2.0 to start as that's most likely what you have.

Try and upload blink to your LeoStick and make sure it all works.

If that works you're good to move on.

## Flashing my arduino

### Load up the simplebot/SimpleBotFirmata sketch.

1. Open the Arduino app
2. Select File -> Open from the menu
  1. Select the SimpleBotFirmata/SimpleBotFirmata.ino file from the SimpleBot repository
  2. Click Open
3. Select Tools -> Board -> &lt;Your Board&gt; from the menu
  1. The 2014 NodeBotsDay used the Arduino Nano which sometimes shows up as "Arduino Nano w/ ATmega328"
4. Plug the Arduino into your USB port
5. Select Tools -> Serial Port -> /dev/tty.usbserial.XXXX from the menu
  1. If you are unsure which to select then unplug your Arduino, check this menu item, then plug it back in and check the menu again

### Compile and upload it to your arduino.

1. Compile/Verify the code
  1. Click the Tick button in your SimpleBotFirmata Arduino window
2. Upload the code
  1. Click the Right Arrow button that sits besides the Tick button

## Assemlbing the SimpleBot

You can assemble your SimpleBot in the order that suits you best. One way would be:

1. Screw the nub/dome thing to the back of your base board 
  1. Underneath the board at the bottom of the picture below
2. Stick the breadboard at the back of your base board
3. Attach the Servos to your base board
4. It should now look like:<br/>
  ![Base With Servos](img/assembly/BaseWithServosAndArduino.png)
5. Attach the front of the bot to the base
  1. The front is the plastic piece sitting at the top of the previous picture
6. Put the wheels together
  1. Cut 4 lengths of wire that are 20cm in length
  2. Find the rest of the parts for your wheel:<br/>
    ![Wheel pieces](img/assembly/WheelUnassembled.png)
  3. Line up the wheel and the plastic hub:<br/>
    ![Wheel aligned to hub](img/assembly/WheelStep1.png)
  4. Use the wire to attach the plast hub to your wheel in a similar fashion to the way you would thread a button:<br/>
    ![Wheel threaded to hub](img/assembly/WheelStep2.png)
  5. Twist the ends of the wire together, this is what will tighten/lock the wheel to the hub:<br/>
   ![Wheel and hub finished](img/assembly/WheelStep3.png)
  6. Bend the twisted wire out of the way
7. Attach the wheel to the servos, they lock on reasonably tight
8. Push your Arduino into your breadboard and wire everything up according to the wiring diagrams:
  Schematic:<br/>
  ![SimpleBot schematic](examples/wiring/basic_wiring_schematic.png)
  Breadboard:<br/>
  ![SimpleBot Breadboard diagram](examples/wiring/basic_wiring_bb.png)

## Ultrasonic Sensor Wiring

The ultrasonic sensor has 4 pins:

1. Vcc - is attached to the positive end of the power source
2. Trig - is attached to a digital input pin (e.g. pin d6)
3. Echo - is attached to the same input pin as Trig
4. GND - is attached to the negative/ground end of the power source

### Assembling issues

* Sometimes the negative wire will be coloured black, sometimes brown, and sometimes green.

## Testing it out

Once you have it all wired up, look at the ping.js and simplebot.js files in the examples folder which you can use as a base for everything else.

### Testing issues

* Make sure that the pin numbers on your nano board match the settings in your simplebot.js file. e.g.

```javascript
var left_wheel  = new five.Servo({ pin:  9, type: 'continuous' }).to(LSTOPVAL);<br/>
var right_wheel = new five.Servo({ pin: 10, type: 'continuous' }).to(RSTOPVAL);
```

# Driving over Bluetooth

You can use bluetooth to drive the simplebot but it's not for the faint of heart. Get a bluetooth module and configure it per [this wiki entry in J5](https://github.com/rwaldron/johnny-five/wiki/JY-MCU-Bluetooth-Serial-Port-Module-Notes). This is a mandatory.

Also note that this *will* work with a leostick but you get a lot of timing errors so be patient, or switch to an Uno or something.

Once you've got your bluetooth set up, you should see it in your serial ports.

Simply go:

    node examples/simplebot.js /dev/tty.SERIALPORT

Changing the device path to whatever yours is. You should now be able to drive using wireless over bluetooth. 

If you get errors about pinMode and undefined issues that's basically a timing issue or a dropped backet over bluetooth. Told you this wasn't for the faint of heart. Try again and see what happens.

If you happen to have a playstation controller then you can use the sb-controller.js example to drive your simplebot using a console controller which is pretty cool.

# Driving using wifi

You can use a simple serial wifi module to make your SimpleBot work over wireless (increased range, no BT headaches). Check out [this gist for more details](https://gist.github.com/ajfisher/1fdbcbbf96b7f2ba73cd).
