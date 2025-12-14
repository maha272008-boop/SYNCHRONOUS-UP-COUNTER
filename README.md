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

/* write all the steps invloved */

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

## Developed by:MAHALAKSHMI P 
## RegisterNumber:25017517
*/
```
Synchronous counter
------------------------------------------------------
module Syn_Co (
    input  wire clk,       // clock input
    input  wire rst,       // synchronous reset
    output reg  [2:0] q   // 3-bit counter output
);

initial begin
     q <= 3'b000;
	 end

always @(posedge clk) 
begin
q <= 3'b000;
    if (rst) 
        q <= 3'b000;       // reset counter to 0
    else
        q <= q + 1;        // increment counter
end

endmodule

```
**RTL LOGIC UP COUNTER**
<img width="1011" height="540" alt="image" src="https://github.com/user-attachments/assets/362d48a2-1f78-4988-9840-282be22ad60e" />



**TIMING DIAGRAM FOR IP COUNTER**
<img width="1057" height="188" alt="image" src="https://github.com/user-attachments/assets/c6507ace-6721-45cc-baad-70be68b23d45" />
**TRUTH TABLE**
<img width="492" height="512" alt="image" src="https://github.com/user-attachments/assets/4638e0e5-7d16-4665-a8a8-2a4d1302577a" />

**RESULTS**
 Thus,implemented the synchronous-up-counter using verilog and validating their functionality using functional table
