# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 
 

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)


4-bit Count Down Counter
### Procedure
## step1
Create a new project in QuartusII software.

## step2
Name the project as uc for upcounter and dc for down counter.

## step3
Create a new verilog hdl file in the project file.

## step4
Name the module as dc and uc for down counter and up counter.

## step5
Within the module declare input and output variables.

## step6
Create a loop using if-else with condition parameter as reset value.

## step7
End the loop and module.


### PROGRAM 
```
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by: SOWMYA V
RegisterNumber: 212222110045
```
## UPCOUNTER:
```
module upcounter(D,C,B,A,CLK);
output reg D,C,B,A;
input CLK;
always @(posedge CLK)
begin
	D=(C&B&A)^D;
	C=(B&A)^C;
	B=(A^B);
	A=(1^A);
end
endmodule
```
## DOWNCOUNTER:
```
module downcounter(A,B,C,D,CLK);
input CLK;
output reg A,B,C,D;
always@(posedge CLK)
begin
	A=(((~B)&(~C)&(~D))^A);
	B=(((~C)&(~D))^B);
	C=((~D)^(C));
	D=1^(D);
end
endmodule
```

### RTL LOGIC UP COUNTER AND DOWN COUNTER  

## upcounter :
![image](https://github.com/SowmyaVisvanathan/Exp-7-Synchornous-counters-/assets/119475775/1ff9f2a2-8eda-49ad-937d-bd1a81f43d8e)

## down counter:

![image](https://github.com/SowmyaVisvanathan/Exp-7-Synchornous-counters-/assets/119475775/30f3d9be-c2f0-42f0-9466-4f124a1830a2)


### TIMING DIGRAMS FOR COUNTER  

## upcounter
![image](https://github.com/SowmyaVisvanathan/Exp-7-Synchornous-counters-/assets/119475775/ea0eef8b-9de0-4c43-906a-53ca26fb7e1b)

## downcounter

![image](https://github.com/SowmyaVisvanathan/Exp-7-Synchornous-counters-/assets/119475775/e7968b73-3ce2-49df-884a-d12540b9348a)

### TRUTH TABLE 

## upcounter

![image](https://github.com/SowmyaVisvanathan/Exp-7-Synchornous-counters-/assets/119475775/ede3b3b3-8f71-486c-b78c-d4fdc88087b0)

## downcounter

![image](https://github.com/SowmyaVisvanathan/Exp-7-Synchornous-counters-/assets/119475775/ee7f4b6f-2b0c-452e-99bf-ee1751cfc001)


### RESULTS 
Thus, The Synchornous up counter and down counter circuits are studied and the truth table for different logic gates is successfully verified.
