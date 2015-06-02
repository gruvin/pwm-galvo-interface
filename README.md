###A two channel 0-3.3V PWM to +/-5VDC converter for use with laser galvanometers

This interface board takes two raw PWM (0-3.3V) inputs from a microcontroller, low pass filters 
them and translates the analogue result into two +/-5VDC, balanced outputs -- the latter being 
what many laser galvanometer drivers require as inputs. Power (+/-15VDC) is acquired from one 
of the two galvanometer driver boards.

![https://raw.githubusercontent.com/gruvin/pwm-galvo-interface/master/images/laser-galvo-interface-3d.png]
(https://raw.githubusercontent.com/gruvin/pwm-galvo-interface/master/images/laser-galvo-interface-3d.png)

The above image is about double actual size, on my iMac 27" screen. (109DPI)

This design (using DipTrace) has been built and tested. It works surprisingly well. I run the PCM frequency 
at between 800KHz and 1MHz on the PWM input side (from an Arduino or Maximite, for example) and the results 
at the other end of the galvanometer interface, mirrors, laser etc is pretty darn good. 

The high frequency PWM allows an order of magnitude higher laser direction precision. However, the board will 
work down to around 200KHz -- and lower if the LPF capacitance is increased. But then the laser starts to make 
rounded corners, instead of crisp, sharp turns of the kind I need for a project in mind.

Having completed this exercise, I now intend removing all the analogue electronics of the galvanometer 
interface itself and making my own PID controller, fully digital -- except the galvanometers themselves, 
of course. There will no longer be a need for this board. But it was well worth the experiment.
