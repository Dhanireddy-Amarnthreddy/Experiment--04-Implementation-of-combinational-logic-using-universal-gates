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
Developed by: D.Amarnath 
RegisterNumber:212221240012  
*/
```
##USING NAND
module comblogic(a,b,c,d,f);
input a,b,c,d;
output F;
wire f1,f2,f3;
assign f1 = (~c&~b&~a);
assign f2 = (~d&~c&~a);
assign f3 = (c&~(~b)&~a);
assign F= f1&~f2&~f3;
endmodule
##USING NOR
module comblogic(a,b,c,d,f);
input a,b,c,d;
output F;
wire f1,f2,f3,f4;
assign f1 = c&(~b)&a;
assign f2 = d&(~c)&a;
assign f3 = c&(~b)&a;
assign f4 = ~(f1|f2|f3);
not(F,f4);
endmodule
```
## RTL realization
## Output:
## Program 1
## RTL
![rtl1](https://user-images.githubusercontent.com/94165103/192567224-ada1541e-e61b-4234-9824-a52c7d2c66ed.jpg)
## Timing Diagram
![td1](https://user-images.githubusercontent.com/94165103/192567466-f0e28c9e-fad2-4258-b658-f75fc8d1ae38.jpg)
### Truth table
![truth1](https://user-images.githubusercontent.com/94165103/192567722-90e27bde-89bb-43f1-a2c9-fb096a30a66a.jpg)

## program 2
## RTL
![rr](https://user-images.githubusercontent.com/94165103/192568121-d6d6b3c8-0469-492f-991e-28e7c9241737.jpg)

## Timming diagram
![td2](https://user-images.githubusercontent.com/94165103/192568433-4fc7adb6-5f85-44e8-b7a8-9975f8f41f0f.jpeg)
## Truth table
![truth 2](https://user-images.githubusercontent.com/94165103/192569873-b764f934-0f0e-492d-9d57-473283eabfca.jpg)

## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.

Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
