# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure
Step-1: create module encoder and decoder. Step-2: Get inputs and outputs for encoders and decoders. Step-3: perform or operation for encoder and and logic for decoders. Step-4: perform RTL LOGIC and get waveform. Step-5: End the module.



### PROGRAM 
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: prakash.R
RegisterNumber: 212222240074

ENCODER:
module enc(a0,a1,a2,y0,y1,y2,y3,y4,y5,y6,y7);
input y0,y1,y2,y3,y4,y5,y6,y7;
output a0,a1,a2;
or(a0,y7,y5,y3,y1);
or(a1,y7,y6,y3,y2);
or(a2,y7,y6,y5,y4);
endmodule 

DECODER:
module dec (a0,a1,a2,y0,y1,y2,y3,y4,y5,y6,y7);
input a0,a1,a2;
output y0,y1,y2,y3,y4,y5,y6,y7;
wire a0bar,a1bar,a2bar;
not(a0bar,a0);
not(a1bar,a1);
not(a2bar,a2);
and(y0,a0bar,a1bar,a2bar);
and(y1,a0,a1bar,a2bar);
and(y2,a0bar,a1,a2bar);
and(y3,a0,a1,a2bar);
and(y4,a0bar,a1bar,a2);
and(y5,a0,a1bar,a2);
and(y6,a0bar,a1,a2);
and(y7,a0,a1,a2);
endmodule





### RTL LOGIC  

![1](https://github.com/sarveshjustin/Experiment-08-Encoders-and-decoders-/assets/113497481/c1514df8-7b17-4a19-8a0b-8ff94d89c46c)
![2](https://github.com/sarveshjustin/Experiment-08-Encoders-and-decoders-/assets/113497481/2b7006d5-6c69-431e-ba66-a13fe2fe22ef)







### TIMING DIGRAMS  
![3](https://github.com/sarveshjustin/Experiment-08-Encoders-and-decoders-/assets/113497481/d9318a08-278d-4fba-bf90-4c8fe574fc1f)
![4](https://github.com/sarveshjustin/Experiment-08-Encoders-and-decoders-/assets/113497481/fbbb0d0e-f244-48ef-b2bb-3d035d5257af)

### TRUTH TABLE 

![5](https://github.com/sarveshjustin/Experiment-08-Encoders-and-decoders-/assets/113497481/da79cf4a-fc50-40d6-98f0-2c9f75265295)
![6](https://github.com/sarveshjustin/Experiment-08-Encoders-and-decoders-/assets/113497481/85363d28-c137-4bb1-bddf-692ddc43ffda)





### RESULTS 
Thus,program to design encoder and decoder is successfully completed.
