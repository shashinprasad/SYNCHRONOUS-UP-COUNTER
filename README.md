### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**


**4 bit synchronous UP Counter**


If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.



**Procedure**

1.Initialize the shift register to a known state (e.g., all zeros).

2.Input a bit serially into the shift register.

3.Shift the contents of the register one position to the right (or left).

4.Output the shifted bit from the last stage of the register.

5.Repeat steps 2-4 for each bit you want to input and shift.




**PROGRAM**


Developed by: shashin prasad s

RegisterNumber:212222230144


```
module ex11(out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(!rstn)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```


**RTL LOGIC UP COUNTER**


![325875062-66fc43d1-92e2-44d8-aa13-34c31b4f100a](https://github.com/shashinprasad/SYNCHRONOUS-UP-COUNTER/assets/129143499/7982bc82-76f8-4aa6-a545-5d9e7600c0dc)



**TIMING DIAGRAM FOR IP COUNTER**

![325875075-4e8c3b6a-4598-4ed3-b666-6ded1c19437a](https://github.com/shashinprasad/SYNCHRONOUS-UP-COUNTER/assets/129143499/459ffda9-3bfb-4f27-b891-445a6a841fe9)




**TRUTH TABLE**
![325875099-865fb0d4-c01e-48fa-9753-c277cc1e6f6a](https://github.com/shashinprasad/SYNCHRONOUS-UP-COUNTER/assets/129143499/1badade1-0920-4031-8c1c-9bffc3c4db56)



**RESULTS**



Hence a 4 bit synchronous up counter is implemented correctly
