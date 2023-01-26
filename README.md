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
Developed by: Naresh.V
RegisterNumber: 22008873 
*/

PROGRAM

i)ENCODER:

module exp8(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);

output a,b,c;

input d0,d1,d2,d3,d4,d5,d6,d7;

or(a,d4,d5,d6,d7);

or(b,d2,d3,d6,d7);

or(c,d1,d3,d5,d7);

endmodule

ii)DECODER:

module dec(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);

output d0,d1,d2,d3,d4,d5,d6,d7;

input a,b,c;

assign d0=(~a & ~b & ~c) ;

assign d1=(~a & ~b &c);

assign d2=(~a & b &~c);

assign d3=(~a & b &c);

assign d4=(a &~b&~c);

assign d5=(a &~b&c);

assign d6=(a&b&~c);

assign d7=(a&b&c);

endmodule




### RTL LOGIC  

Encoder

![image](https://user-images.githubusercontent.com/119393642/214846263-f02ed1eb-9b99-4aa6-9df9-d4c9129e5a9a.png)

Decoder

![image](https://user-images.githubusercontent.com/119393642/214846418-7080cbb9-f5b2-4e81-b3a8-fd7e50837d53.png)



### TIMING DIGRAMS  

Encoder

![image](https://user-images.githubusercontent.com/119393642/214846420-6e6222bd-5779-4488-b842-b4b12a7be7c1.png)
![image](https://user-images.githubusercontent.com/119393642/214846455-b5af1234-c2f7-48ad-bdef-e2e81914ef94.png)
![image](https://user-images.githubusercontent.com/119393642/214846481-6e217d1c-a599-4f10-9410-2da45764d992.png)

Decoder

![image](https://user-images.githubusercontent.com/119393642/214846566-dee4ede6-2fc2-4449-8bb6-468c760c7912.png)

### TRUTH TABLE 

Encoder
![image](https://user-images.githubusercontent.com/119393642/214846647-b4ea3f1c-5b9c-468f-9a8c-33d727511a02.png)

Decoder

![image](https://user-images.githubusercontent.com/119393642/214846681-faf0877a-5466-4315-904f-f11d1e854492.png)

### RESULTS 
Thus 8 to 3 Encoder and 3to8 Decoder are implemented successfully using verilog and validate its outputs
