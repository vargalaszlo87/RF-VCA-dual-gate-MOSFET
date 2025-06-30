# 🚀 RF-VCA-dual-gate-MOSFET
Voltage Controlled Amplifier with dual-gate MOSFET for FlexRadio project, but you can also use it independently. This wideband unit can be used as the first stage of an MW / SW radio. I hope the circuit and this description will helpful for you, try it in LTSpice and build it for your fun. :)

❤️ **The most important thing in FLEX-Radio project is the compromise between the thoughtful solution and the solid price.** 

# ⭐ The circuit

![image](https://github.com/user-attachments/assets/aae4cbdf-b068-447e-b932-1c078603d19b)

A widband amplifier has many problems for example gain, frequency response or impedance in full range. If you see the gain works very well, the frequency response will to narrow or rugged and etc. Therefore, it's not easy to find the balance. Let's try it! This circuit has more classical solutions, but it has many useful functions for example Over-Voltage Protection. **Attention!** This circuit has not real ESD protection! 🥇 It has simple but intelligent surge protection. :)
 
## The first part

In this configuration, this circuit can also be used with a stick or long wire antenna in range 0.5MHz to 10.0MHz. Therefore, we must pay close attention for higher input voltage because the pins of FETs are very sensitive. See it:

![image](https://github.com/user-attachments/assets/869b88dc-ef5f-4f53-b2c9-b8c5a19f63f6)

**Simple but very important!** Choosing the best diode type is not trivial. The diode must be higher voltage tolerant with very small capacity and very high speed. So, it's heavy. We must find a well solution for those problems with THT parts (in HAM world that is basic need). 

🚀 **My solution for those problems** are the 1N5711 Germanium diode (VHF/UHF schottky) with a small parallel capacity. 

The typical capacitance of this diode is very small, 2-4 pF. The maximal voltage is 70V. 

📐 **But how it works?**

If come a higher voltage impulse or higher signal from an other circuit unit, than the resistor limits the current and the parallel diode discharge the overvoltage. Unfortunately, the diode has a short dead time before it works properly, therefore we use a very small parallel capacitance that responds immediately to the high frequency impulse. Those diodes and this small capacitance do not degrade the frequency response and the impedance and limit the voltage to 0.2-0.3V (as a Germanium PN junction).

⚛️ If you want to transpose the impedance to 50 ohms, choose a smaller resistor (about ~10 ohms).

## The second part

**Very important thing!** If the impedance of the amplifier is not the same across the full frequency range, the power of the signal from the antenna to the amplifier will vary. So we need to use a transistor stage that is less sensitive to frequency changes. ❤️ That is the **Common-Gate** amplifier.

![image](https://github.com/user-attachments/assets/1edb7014-1d43-451e-95d0-8a0e5c23d2f7)

What is the problem normally? If we were to use a commonly used amplifier type, such as a common-source or common-drain amplifier, then the parasitic capacitance of the gate-source causes a change in the impedance or frequency response as the frequency increases. This circuit with those parameters makes relative low level of change of input impedance. In the full frequency range the impedance-changing less than 0.1kohm and the avarage is 2.1kohm. ⭐ The impedance around 2k ohms is well match for the long-wire antenna and it works also good with simple stick-antenna.

The output impedance of the common-gate amplifier is also good for the following dual-gate amplifier.

## The third part

🚀 **Very intresting and very useful!** This circuit is most similar to a vacuum-tube circuit.

![image](https://github.com/user-attachments/assets/b6a49f9a-2c7f-4ece-9271-370576bd1d89)

 This MOSFET has two gates, so you can control this on the two electrodes at the same time. Therefore, you can make with this: 
 - a mixer circuit
 - automatic gain control
 - voltage control amplifier

📐 This circuit implements a voltage control amplifier. Normally the Gate 1 is the way of signal (RF or HF) and the Gate 2 controls the gain. 

# ⭐ Simulations

**This plot shows the Amplitude and phase chart at a control voltage of 2.0V**

![image](https://github.com/user-attachments/assets/6509a6a2-a42a-4f72-a6e7-992d0747dd01)

- f0 = 2.034MHz
- f_a = 534kHz
- f_b = 6.87MHz

**and at a control voltage of 0.1V**

![image](https://github.com/user-attachments/assets/3a832a92-2d24-40e4-9a4d-0228779a1bd8)

- f0 = 2.06MHz
- f_a = 369kHz
- f_b = 9.62MHz



