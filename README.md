# TSPC Latch
The True Single Phase Clock circuit technique operates using a single clock and does not require the local inversion of clock.They are known for being power-efficient due to this single-phase clocking mechanism.      
The fundamental stages of TSPC are  SP, PP, SN, and PN.
The first letter S and P denotes the logic  type:
S:Non-Precharged Logic.
P:Precharged Logic..
The second letter denotes the type of clocked devices:
P:P-type.
N:N-type.
![image](https://github.com/KeerthanaUmesh/TSPC_Latch/assets/147648970/5fb6d1d6-2896-4d4f-8318-df19b421cfb3)
 ##### (source:“Low-Power CMOS Circuits: Technology, Logic Design and CAD Tools” by Christian Piguet)

## Non-Precharged Tspc Latch
It does not require precharging of its internal nodes prior to  storing data. The single clock controls the operation of its transistors.This simplifies the latch design and reduces power consumption.Its functionality is governed solely by a single clock signal, eliminating the need for a separate precharge phase typically found in precharged TSPC latches. This design feature simplifies the latch structure and enhances its efficiency, making it advantageous for applications requiring low power consumption and high-speed operation. 

### SN-Type Latch
It efficiently stores and retrieves data based on the timing of a single clock signal, offering simplicity and low power consumption in digital circuitry.It is a positive type latch(which is a level triggered device)
It’s working is as follows:
When clock is low(CLK=LOW), the latch is in the hold state, preserving its previous state values.
When clock is high(CLK=HIGH) , the latch enters the transparent state, allowing the output to mirror the input signal.
### D-Latch
A D latch made with NAND gates stores one bit of data. It consists of two cross-coupled NAND gates forming a memory section and two control NAND gates. When clock is high (CLK=HIGH), it captures data from the D input. The latch holds its state when clock is disabled (Clock=LOW).

## Implementation using Cadence Virtuoso

### TSPC-SN Type
![image](https://github.com/KeerthanaUmesh/TSPC_Latch/assets/147648970/1a68ed59-e437-4ceb-807f-2194b33bd924)
<center> Schematic of TSPC Latch-SN type with VDD=1.8v </center>
