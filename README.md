# WHATPowerOutlet
W.irelessH.omeA.utomation and T.elemetry.   This will function as a wall outlet.

This draws power from the outlet's power for use by the microcontroller.
This is a transformerless power supply that uses a P-Channel FET to only connect power to the circuit when the 
voltage is below about 20v, and disconnect supply power when it is above this voltage.  this allows a 1000uF 25v
capacitor to deliver a (rough) DC voltage to the Voltage regulator, which drops the voltage to about 12v.

If a regulator tried to just reduce the input line voltage in an analog manner, the Power dissipation would be very large.
By operating the FET either full-on or full off, the power dissipation is reduced. When it is full on, the Source to Drain
voltage is low.  Since Power = Voltage * current, the voltage is low, so the power is minimal.  When it is off, the Source to Drain 
current is low (almost 0).  Since Power = Voltage * current, the power it must dissipate is very low.

The dis-advantages of this are that the voltage is pretty noisy. I use a 1000uF to maintain voltage while the FET is off.
I believe a choke inline with the power would help smooth the current (and thus the voltage) significantly.

