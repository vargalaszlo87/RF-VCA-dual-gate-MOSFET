# 🚀 RF-VCA-dual-gate-MOSFET
Voltage Controlled Amplifier with dual-gate MOSFET for FlexRadio project, but you can also use it independently. This wideband unit can be used as the first stage of an MW / SW radio. I hope the circuit and this description will helpful for you, try it in LTSpice and build it for your fun. :)

❤️ **The most important thing in FLEX-Radio project is the compromise between the thoughtful solution and the solid price.** 

# ⭐ The circuit

A widband amplifier has many problems for example gain, frequency response or impedance in full range. If you see the gain works very well, the frequency response will to narrow or rugged and etc. Therefore, it's not easy to find the balance. Let's try it! This circuit has two classical parts, but it has many useful functions for example Over-Voltage Protection.

## The first part

In this configuration, this circuit can also be used with a stick or long wire antenna in range 0.5MHz to 10.0MHz. Therefore, we must pay close attention for electrostatic discharges and any high input voltage because the pins of FETs are very sensitive. See it:

![image](https://github.com/user-attachments/assets/09d537b0-92c0-492d-81f6-b3136f87ac7f)

**Simple but very important!** Choosing the best diode type is not trivial. The diode must be high voltage tolerant with very small capacity and very hight speed. So, it's heavy. We must find a well solution for those problems with THT parts (in HAM world that is basic need). 

**My solution for those problems** are the 1N5711 Germanium diode with a small parallel capacity.


