# Display a value on IKEA's Sparsnäs

Connect an IR-LED to your Raspberry Pi and make the LED blink into the Sparsnäs IR-sensor. Now you have a remote wireless display that can show a number representing whatever you want. Use it to display a time countdown to an event. The cpu temperature. The current number of visitors on your web site. How much free space you have on your hard drive. Network latency when you're gaming. Or something else. Yeah, the number will have the letter W tagged on to it. Live with it. No you can't display negative numbers.

Either call the python script from the command line with the number that you want to display or write the number into a settings file that is checked every few seconds by the python script, continuously updating the displayed number. Preferably start the script at boot and change the number to display whenever you want by updating the settings file.

With the default setting of pulses per KWh at 10000 the highest number that is feasible to display is a few hundred. Beyond that the blink frequency gets a bit high which lowers the display accuracy. Remember that we are not transmitting the number to display as a digital number but as a time delay which can vary just so very slightly due to system load changing in the Raspberry.

To display larger numbers just use a lower pulse per KWh setting in Sparsnäs and update the python code accordingly.


# Prerequisites

Install pigpio on your Raspberry:
```
sudo apt-get install pigpio python-pigpio python3-pigpio -y
sudo systemctl enable pigpiod.service
sudo systemctl start pigpiod.service
```  
The default GPIO pin used is gpio 17 (which equals to pin 11 on a Model 3 Pi). You can of course choose to use any other pin by updating the python code.



