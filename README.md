# T-FLIPFLOP-POSEDGE

**AIM:**

To implement  T flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**T Flip-Flop**

T flip-flop is the simplified version of JK flip-flop. It is obtained by connecting the same input ‘T’ to both inputs of JK flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of T flip-flop is shown in the following figure.

![image](https://github.com/sanjevrm/T-FLIPFLOP-POSEDGE/assets/155142423/8e5e90a6-b0b1-45c1-87b0-f095b9767c4e)


 
This circuit has single input T and two outputs Qtt & Qtt’. The operation of T flip-flop is same as that of JK flip-flop. Here, we considered the inputs of JK flip-flop as J = T and K = T in order to utilize the modified JK flip-flop for 2 combinations of inputs. So, we eliminated the other two combinations of J & K, for which those two values are complement to each other in T flip-flop. The following table shows the state table of T flip-flop.

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, T flip-flop can be used for one of these two functions such as Hold, & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of T flip-flop. Inputs Present State Next State

![image](https://github.com/sanjevrm/T-FLIPFLOP-POSEDGE/assets/155142423/f52c8a83-b866-43c9-b84f-c8bab7d125f6)


 
From the above characteristic table, we can directly write the next state equation as Q(t+1)=T′Q(t)+TQ(t)′ ⇒Q(t+1)=T⊕Q(t)

**Procedure**

1.Define Module: Define a Verilog module for the T flip-flop with inputs (T, CLK) and outputs (Q, Q_bar).

2.Declare Inputs and Outputs: Declare input and output ports for the module.

3.Implement Flip-Flop Logic: Write Verilog code to implement the T flip-flop logic based on its functional table. Use a synchronous always @(posedge CLK) block to trigger the flip-flop on the positive edge of the clock signal.

4.Simulate Using Testbench: Write a Verilog testbench to simulate the behavior of the T flip-flop under different input conditions.

5.Apply Input Stimuli: In the testbench, apply various combinations of input stimuli (T, CLK) to cover all possible input states.

6.Verify Output Behavior: Verify that the output behavior of the T flip-flop matches the expected behavior defined by its functional table.

7.Check for Race Conditions: Ensure that there are no race conditions or undefined states in the design by analyzing the timing and sequence of input changes.

**PROGRAM**
```
Program for flipflops and verify its truth table in quartus using Verilog programming.
Developed by:Sanjev R M
RegisterNumber: 212223040186
```
```verilog
module tflipflop( input clk, rst_n, input t,
output reg q,
output q_bar
);
always@(posedge clk) 
begin 
if(!rst_n)
q<=0;
else 
begin
q<=(t?~q:q);
end
end
assign q_bar = ~q;
endmodule
```

**RTL LOGIC FOR FLIPFLOPS**
![image](https://github.com/sanjevrm/T-FLIPFLOP-POSEDGE/assets/155142423/c7432148-c08c-4c68-9c68-869cd3f018c7)



**TIMING DIGRAMS FOR FLIP FLOPS**
![image](https://github.com/sanjevrm/T-FLIPFLOP-POSEDGE/assets/155142423/a44500b5-3061-46b8-bef9-b3d953810b7b)



**RESULTS**

Thus the program to implement a T flipflop using verilog and validating their functionality using their functional tables is successfully completed.
