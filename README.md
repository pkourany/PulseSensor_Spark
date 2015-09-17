PulseSensor Library adapted for Spark Core by Paul Kourany, June 2015 from:

# Pulse Sensor Amped 1.4
=====


## Now for Particle Core and Photon !!!
------

This code is for Pulse Sensor Amped by Joel Murphy and Yury Gitman
    www.pulsesensor.com 
	
    >>> Pulse Sensor purple wire goes to Analog Pin A2 (see PulseSensor_Spark.h for details) <<<
	
Pulse Sensor sample aquisition and processing happens in the background via a hardware Timer interrupt. 2mS sample rate.
PWM on selectable pins A0 and A1 will not work when using this code, because the first allocated timer is TIMR2!
The following variables are automatically updated:
Signal :    int that holds the analog signal data straight from the sensor. updated every 2mS.
IBI  :      int that holds the time interval between beats. 2mS resolution.
BPM  :      int that holds the heart rate value, derived every beat, from averaging previous 10 IBI values.
QS  :       boolean that is made true whenever Pulse is found and BPM is updated. User must reset.
Pulse :     boolean that is true when a heartbeat is sensed then false in time with pin13 LED going out.

This code is designed with output serial data to Processing sketch "PulseSensorAmped_Processing-xx"
The Processing sketch is a simple data visualizer. 
All the work to find the heartbeat and determine the heartrate happens in the code below.
Pin D7 LED (onboard LED) will blink with heartbeat.
If you want to use pin D7 for something else, specifiy different pin in Interrupt.h
It will also fade an LED on pin fadePin with every beat. Put an LED and series resistor from fadePin to GND.
Check here for detailed code walkthrough:
http://pulsesensor.myshopify.com/pages/pulse-sensor-amped-arduino-v1dot1

New to v1.5 (Sept 2015)

Works with Paritcle Core and Photon!

New to v1.4
-------

ASCII Serial Monitor Visuals - See the User's Pulse & BPM via the Serial port.
Open a serial monitor for this ASCII visualization.

To Turn On ASCII Visualizer:

```// Regards Serial OutPut  -- Set This Up to your needs
static boolean serialVisual = false;   // Set to 'false' by Default. 
```

to:

```// Regards Serial OutPut  -- Set This Up to your needs
static boolean serialVisual = true;   // Re-set to 'true' to do ASCII Visual Pulse  : ) 
```

That's it's! Upload and open your Serial Monitor.

Pulse Sensor Amped 1.4    by Joel Murphy and Yury Gitman   http://www.pulsesensor.com
