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
#### Schematic
![tspc_latch](https://github.com/KeerthanaUmesh/TSPC_Latch/assets/147648970/63be6b0b-bc60-4cdd-8102-d05d4c3bed1a)

#### Transient Analysis
- When clk=1.8(high) and input=1.8(high) then output=1.8(high) i.e, acts as a input follower.
  ![image](https://github.com/KeerthanaUmesh/TSPC_Latch/assets/147648970/562f2fa9-480e-4788-981d-90e73724d114)

-When clk=1.8(high) and input=0(low) then output~0 (low) i.e, acts as a input follower.   
![image](https://github.com/KeerthanaUmesh/TSPC_Latch/assets/147648970/667556f5-f1a4-4f87-bd76-ac3bcf4a90b7)

-When clk=0(low) and input=1.8(high) and output~0 (low) i.e, it holds the previous value which was low.
![image](https://github.com/KeerthanaUmesh/TSPC_Latch/assets/147648970/43ba5b9d-35c0-4fc7-ac23-2ad0ed2d5ead)

-When clk=0(low) and input=0(low) and output~0 (low) i.e, it holds the previous value which was low.
![image](https://github.com/KeerthanaUmesh/TSPC_Latch/assets/147648970/98933aef-42b7-48fe-816d-5d1b517bd443)


### Traditional D latch
#### Schematic
![d_latch](https://github.com/KeerthanaUmesh/TSPC_Latch/assets/147648970/6c310b8b-2ff3-4ed5-ad64-347b45ff59f1)

#### Transient Analysis
-When clk=1.8(high) and input=1.8(high) then output=1.8 (high) i.e, acts as a input follower. 
![image](https://github.com/KeerthanaUmesh/TSPC_Latch/assets/147648970/03dd24b8-935b-4853-ac3d-ed264f8cdfc5)

-When clk=0(low) and input=1.8(high) and output~0 (low) i.e, it holds the previous value which was low.
![image](https://github.com/KeerthanaUmesh/TSPC_Latch/assets/147648970/6771178a-71bc-4a5c-b2b8-34cc75e37c6c)

## Power Analysis

**Power graph of TSPC-SN Type Latch**
![image](https://github.com/KeerthanaUmesh/TSPC_Latch/assets/147648970/b9f09df1-8457-446a-96ac-b298b08a082d)

**Average power of TSPC-SN Type Latch**
![image](https://github.com/KeerthanaUmesh/TSPC_Latch/assets/147648970/3313190a-9bba-416b-b8e9-3774aaa30773)

**D-latch Power Schematic**
![image](https://github.com/KeerthanaUmesh/TSPC_Latch/assets/147648970/cc5642e5-c796-44fe-8fe5-738e7c357a19)

**Average power of  D Latch**
![image](https://github.com/KeerthanaUmesh/TSPC_Latch/assets/147648970/b1934d25-c1f7-4ae2-b8fb-f29ed9e387c9)

## Conclusion:
D latch constructed using NAND gates consumes an average of 117.7 microwatts of power.While the TSPC-SN Type latch consumes an average of 34.93 microwatts of power.TSPC-SN Type latch consumes approximately 70.36% less power compared to the D-latch constructed using NAND gates,highlighting its superior energy efficiency and suitability for low-power digital circuitry.




