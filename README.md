# 🚀 RF-VCA-dual-gate-MOSFET
Voltage Controlled Amplifier with dual-gate MOSFET for FlexRadio project, but you can also use it independently. This wideband unit can be used as the first stage of an MW / SW radio. I hope the circuit and this description will helpful for you, try it in LTSpice and build it for your fun. :)

❤️ **The most important thing in FLEX-Radio project is the compromise between the thoughtful solution and the solid price.** 

# ⭐ The circuit

A widband amplifier has many problems for example gain, frequency response or impedance in full range. If you see the gain works very well, the frequency response will to narrow or rugged and etc. Therefore, it's not easy to find the balance. Let's try it! This circuit has more classical solutions, but it has many useful functions for example Over-Voltage Protection. **Attention!** Th This circuit has not real ESD protection! 🥇 It has simple but intelligent surge protection. :)
 
## The first part

In this configuration, this circuit can also be used with a stick or long wire antenna in range 0.5MHz to 10.0MHz. Therefore, we must pay close attention for higher input voltage because the pins of FETs are very sensitive. See it:

![image](https://github.com/user-attachments/assets/869b88dc-ef5f-4f53-b2c9-b8c5a19f63f6)

**Simple but very important!** Choosing the best diode type is not trivial. The diode must be high voltage tolerant with very small capacity and very hight speed. So, it's heavy. We must find a well solution for those problems with THT parts (in HAM world that is basic need). 

🚀 **My solution for those problems** are the 1N5711 Germanium diode (VHF/UHF schottky) with a small parallel capacity. 

The typical capacitance of this diode is very small, 2-4 pF. The maximal voltage is 70V. 

📐 **But how it works?**

If come a higher voltage impulse or higher signal from an other circuit unit, than the resistor limits the current and the parallel diode discharge the overvoltage. Unfortunately, the diode has a short dead time before it works properly, therefore we use a very small parallel capacitance that responds immediately to the high frequency impulse. Those diodes and this small capacitance do not degrade the frequency response and the impedance and limit the voltage to 0.2-0.3V (as a Germanium PN junction).

⚛️ If you want to transpose the impedance to 50 ohms, choose a smaller resistor (about ~10 ohms).

## The second part

**Very important thing!** If the impedance of the amplifier is not the same across the full frequency range, the power of the signal from the antenna to the amplifier will vary. So we need to use a transistor stage that is less sensitive to frequency changes. ❤️ That is the **Common-Gate** amplifier.

![image](https://github.com/user-attachments/assets/1edb7014-1d43-451e-95d0-8a0e5c23d2f7)
