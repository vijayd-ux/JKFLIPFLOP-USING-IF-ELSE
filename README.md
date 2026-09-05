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

/* write all the steps invloved */

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. Developed by:  VIJAY D RegisterNumber: 212225230300
*/
```
module JK (q, qb, j, k, clock, reset);

input j, k, clock, reset;
output reg q, qb;

always @(posedge clock)
begin
    if (!reset)
    begin
        q <= 0;
        qb <= 1;
    end
    else
    begin
        if (j == 0 && k == 0)
        begin
            q <= q;
            qb <= qb;
        end
        else if (j == 0 && k == 1)
        begin
            q <= 0;
            qb <= 1;
        end
        else if (j == 1 && k == 0)
        begin
            q <= 1;
            qb <= 0;
        end
        else if (j == 1 && k == 1)
        begin
            q <= ~q;
            qb <= ~qb;
        end
    end
end

endmodule
```
**RTL LOGIC FOR FLIPFLOPS**
<img width="1917" height="1077" alt="image" src="https://github.com/user-attachments/assets/a95e73e6-edde-4465-8701-fdae9ef87a8e" />


**TIMING DIGRAMS FOR FLIP FLOPS**
<img width="1302" height="621" alt="image" src="https://github.com/user-attachments/assets/bfbe0219-ae0b-4d0e-af23-b7fa41d30a85" />


**RESULTS**

Thus, the JK Flip-Flop was successfully implemented using Verilog HDL with an if-else behavioral description, and its functionality was verified according to the JK flip-flop functional table. The flip-flop performed hold, set, reset, and toggle operations correctly for the corresponding input combinations.
