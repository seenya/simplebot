# Flashing your Aduino

To flash your Arduino follow these steps:
1. Open the Arduino app
2. Select File -> Open from the menu
  1. Select the SimpleBotFirmata/SimpleBotFirmata.ino file from the SimpleBot repository
  2. Click Open
3. Select Tools -> Board -> <Your Board> from the menu
  1. The 2014 NodeBotsDay used the Arduino Nano which sometimes shows up as "Arduino Nano w/ ATmega328"
4. Plug the Arduino into your USB port
5. Select Tools -> Serial Port -> /dev/tty.usbserial.XXXX from the menu
  1. If you are unsure which to select then unplug your Arduino, check this menu item, then plug it back in and check the menu again
6. Compile/Verify the code
  1. Click the Tick button in your SimpleBotFirmata Arduino window
7. Upload the code
  1. Click the Right Arrow button that sits besides the Tick button


