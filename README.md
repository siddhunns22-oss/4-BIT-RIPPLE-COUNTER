# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**

1.Open Quartus Prime and create a new project.

2.Create a new Verilog HDL File and enter the code for the 4-bit Ripple Counter.

3.Save the file with a .v extension and set it as the Top-Level Entity.

4.Compile the design using Processing → Start Compilation.

5.Verify that the compilation completes without errors.

6.Open Tools → Netlist Viewers → RTL Viewer to view the RTL schematic.

7.Create a waveform file and add the clock (clk) and output (q[3:0]) signals.

8.Apply a clock waveform and run the simulation.

9.Observe the timing diagram and verify that the counter counts from 0000 to 1111 in binary.

**PROGRAM**

module EXP12(q, clk, reset); 
output [3:0] q;
input clk, reset;
T_FF tffo(q[0], clk, reset); 
T_FF tff1(q[1], q[0], reset); 
T_FF tff2(q[2], q[1], reset); 
T_FF tff3(q[3], q[2], reset); 
endmodule
module D_FF(q, d, clk, reset); 
output q;
input d, clk, reset;
reg q;
always @(posedge reset or negedge clk)
 if (reset)
q = 1'b0;
 else
q = d;
endmodule
module T_FF(q, clk, reset);
output q;
input clk, reset;
wire d;
D_FF dff0(q, d, clk, reset);
not n1(d, q); 
endmodule
 Developed by: SIDDHARTH N N 
 RegisterNumber: 212225240148
*/

**RTL LOGIC FOR 4 Bit Ripple Counter**
<img width="1048" height="213" alt="Screenshot 2026-06-01 134146" src="https://github.com/user-attachments/assets/44c91c11-1a7b-4f00-9e92-7c13b6bc848e" />

**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
<img width="1319" height="659" alt="Screenshot 2026-06-01 134254" src="https://github.com/user-attachments/assets/7f5fa7a2-e346-442b-9551-64f28bdf6d37" />

**RESULTS**
Thus the program to implement 4-bit ripple counter has been executed successfully.
