Developed by : Sandhiya

Reference No : 22007409  

AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.  

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate  
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate  

Equipments Required:  
- Hardware  
  - PCs
  - Cyclone II 
  - USB flasher
  
- Software
  - Quartus prime
  
Theory

Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

Procedure

Program:

Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming. 

PROGRAM 1:
module expfour(a,b,c,d,f);
input a,b,c,d;
output f;
wire f1,f2,f3;
assign f1 = (~c&~b&~a);
assign f2 = (~d&~c&~a);
assign f3 = (c&~(~b)&~a);
assign f= f1&~f2&~f3;
endmodule

PROGRAM 2:
module expfourtwo(a,b,c,d,f);
input a,b,c,d;
output f;
wire f1,f2,f3,f4;
assign f1 = c&(~b)&a;
assign f2 = d&(~c)&a;
assign f3 = c&(~b)&a;
assign f4 = ~(f1|f2|f3);
not(f,f4);
endmodule

RTL realization

FOR PROGRAM 1:

![1](https://user-images.githubusercontent.com/121559414/211193900-2d5d5365-dfa5-48ba-97ed-65b12c6be4aa.png)


FOR PROGRAM 2:

![2](https://user-images.githubusercontent.com/121559414/211193814-e6898f91-7652-4e0c-bb7f-f3c146e8535a.png)


Output:

TRUTH TABLE

FOR PROGRAM 1:

![3](https://user-images.githubusercontent.com/121559414/211193858-3a329e87-8c18-4607-98ab-71a53e8ef75d.png)

FOR PROGRAM 2:

![4](https://user-images.githubusercontent.com/121559414/211193932-b8c7964d-cfc0-4353-ae42-279ecea06a9a.png)


RTL

Timing Diagram

FOR PROGRAM 1:

![5](https://user-images.githubusercontent.com/121559414/211194005-3fe1b651-4d75-4acc-a308-4767b2f168ea.png)

FOR PROGRAM 2:

![6](https://user-images.githubusercontent.com/121559414/211194036-e31e04f6-c74e-444c-afbc-ec85cdff4678.png)

Result:

Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
