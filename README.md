# JKFLIPFLOP-USING-IF-ELSE

**AIM:** 

To implement  JK flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**JK Flip-Flop**

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/a649c30b-232b-4558-b188-fd6c09845180)


This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/c4360742-e8a8-4937-b089-c46c0433f9a3)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/6c275261-a6d5-4c37-a3a7-1e88ca11c4cd)

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.
 
![image](https://github.com/naavaneetha/JKFLIPFLOP-USING-IF-ELSE/assets/154305477/5174f41b-0ce0-4329-a372-6d1943ea6673)

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

**Procedure**
Step 1: Open Quartus II in your laptop.

Step 2: Write code to implement SR flipflop using Verilog and validating their functionality using their functional tables.

Step 3: Run compilation to check for errors.

Step 4: Open waveform output and load input values.

Step 5: Run simulation to get the output.

Step 6: Open in RTL viewers to get RTL diagram output.


**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming.
Developed by: Jai Harish R 
RegisterNumber:24006817
*/
```
module JK_FLIP_FLOP(j, k, clk, rst, q, qbar);
 input j;
 input k;
 input clk;
 input rst;
 output q;
 output qbar;
reg q;
reg qbar;
always @ (posedge(clk) or posedge(rst)) begin
if (rst==1'b1)
begin
q=1'b0;
qbar=1'b1;
end
else if (j==1'b0 && k==1'b0)
begin
q=q;
qbar=qbar;
end
else if (j==1'b0 && k==1'b1)
begin
q=1'b0;
qbar=1'b1;
end
else if (j==1'b1 && k==1'b0)
begin
q=1'b1;
qbar=1'b0;
end
else
begin
q=~q;
qbar=~qbar;
end
end
endmodule
```

**RTL LOGIC FOR FLIPFLOPS**
![{25E0F7D4-2816-4857-BAE0-178FFF352BD5}](https://github.com/user-attachments/assets/783fbee4-928d-45b6-8d12-2a2ddf0dce1f)

**TIMING DIGRAMS FOR FLIP FLOPS**
![image](https://github.com/user-attachments/assets/85fb152e-fca1-4e2e-ac46-7cc91707c384)

**RESULTS**
The observation of the simulation results and confirm the successful execution of the program.
