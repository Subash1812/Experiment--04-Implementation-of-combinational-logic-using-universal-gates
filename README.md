# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram
## Procedure
## Program:
/*
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: SUBASH CHANDRA BOSE R
RegisterNumber:  22009106
*/
```
USING NAND OPERATION

module fourexp(A,B,C,D,F);  
input A,B,C,D;  
output F;  
wire P,Q,R;  
assign P = C&(~B)&(~A);  
assign Q = D&(~C)&(~A);  
assign R = (~C)&B&(~A);  
assign F = (~P&~Q&~R);  
endmodule  

USING NOR OPERATION

module fourexp(A,B,C,D,F);
input A,B,C,D;
output F;
wire P,Q,R,S;
assign P = C&(~B)&A;
assign Q = D&(~C)&A;
assign R = C&(~B)&A;
assign S = ~(P|Q|R);
assign F = ~S;
endmodule
```
## RTL realization


## Output:
## RTL

NAND
![image](https://user-images.githubusercontent.com/123537051/215270227-82b105d5-7c81-4e2f-b01e-7e520c95d0ac.png)

NOR
![image](https://user-images.githubusercontent.com/123537051/215270263-373bbe7f-2a43-4b21-ba9a-b78cf17e00e9.png)

## Timing Diagram
NAND
![image](https://user-images.githubusercontent.com/123537051/215270370-35a160cd-80ef-49e5-b66d-5e56adbb329d.png)
NOR
![image](https://user-images.githubusercontent.com/123537051/215270380-8fd8ec52-511b-4675-a68b-bd32f0f27dc2.png)
## Truth table
![image](https://user-images.githubusercontent.com/123537051/215270438-f410cfee-4f01-48c6-bbca-3b41e325cc9f.png)
![image](https://user-images.githubusercontent.com/123537051/215270454-f95cbdce-4b11-4156-810f-61dacc4b92b2.png)

## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
