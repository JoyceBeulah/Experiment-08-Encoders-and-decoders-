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
/* write all the steps invloved */



### PROGRAM 
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: R.Joyce Beulah
RegisterNumber:  212222230058
*/
ENCODER
```
module encoder(x,y,z,d0,d1,d2,d3,d4,d5,d6,d7);
output x,y,z;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(x,d4,d5,d6,d7);
or(y,d2,d3,d6,d7);
or(z,d1,d3,d5,d7);
endmodule
```
DECODER
```
module deco(x,y,z,d0,d1,d2,d3,d4,d5,d6,d7);
input x,y,z;
output d0,d1,d2,d3,d4,d5,d6,d7;
wire xbar,ybar,zbar;
not (xb0ar,x);
not (ybar,y);
not (zbar,z);
and (d0,xbar,ybar,zbar);
and (d1,ybar,ybar,z);
and (d2,zbar,y,zbar);
and (d3,xbar,y,z);
and (d4,x,ybar,zbar);
and (d5,x,ybar,z);
and (d6,x,y,zbar);
and (d7,x,y,z);
endmodule
```

# RTL LOGIC  
ENCODER :
![image](https://github.com/JoyceBeulah/Experiment-08-Encoders-and-decoders-/assets/118343698/7da2d45e-c595-4791-9264-87d6726d5e0e)
DECODER :
![image](https://github.com/JoyceBeulah/Experiment-08-Encoders-and-decoders-/assets/118343698/20473989-32d6-455e-80f4-4fe7b0549dbd)







### TIMING DIGRAMS  
ENCODER :
![image](https://github.com/JoyceBeulah/Experiment-08-Encoders-and-decoders-/assets/118343698/876ff9a5-223e-452b-a1cc-3f90b011a679)
DECODER :
![image](https://github.com/JoyceBeulah/Experiment-08-Encoders-and-decoders-/assets/118343698/34f36ce5-313c-476c-a5ba-e4d641b595e7)



### TRUTH TABLE 
ENCODER:
![image](https://github.com/JoyceBeulah/Experiment-08-Encoders-and-decoders-/assets/118343698/98d00c4c-f791-4b15-9421-536ff530612b)
DECODER :
![image](https://github.com/JoyceBeulah/Experiment-08-Encoders-and-decoders-/assets/118343698/ef8b0ef3-3ada-469b-9f5b-056f13defd51)




### RESULTS 
