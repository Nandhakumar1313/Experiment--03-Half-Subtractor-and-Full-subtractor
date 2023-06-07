# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
It can be implemented using two half subtractors and one OR gate as: Giving one half subtractor the inputs A and B that gives outputs Diff1 and B1. Giving second half subtractor inputs Bin and Diff1 from first subtractor that gives outputs B2 and D (difference for the full subtractor).


## Program:
```
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by:G.R.NANDHAKUMAR 
RegisterNumber:212222100029
```
## HALF SUBTRACTOR
```
module HalfSubtractor(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire x;
xor (Diff, A,B);
not(x,A);
and(Borrow,x,B);
endmodule
```
## FULL SUBTRACTOR
```
module FullSubtractor(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule


```

## Output:
##  RTL realization
## HALF SUBTRACTOR
![Screenshot (155)](https://github.com/Nandhakumar1313/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/120230694/06595f4b-b457-489a-9e96-0cd519816b64)

## FULL SUBTRACTOR
![Screenshot (156)](https://github.com/Nandhakumar1313/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/120230694/3455426c-324f-4ca2-a289-5262fa852476)





## Timing diagram 

## HALF SUBTRACTOR
![Screenshot (157)](https://github.com/Nandhakumar1313/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/120230694/5810debd-0c78-4eff-ad8d-df06aba28045)

## FULL SUBTRACTOR
![Screenshot (158)](https://github.com/Nandhakumar1313/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/120230694/9b82e0f7-f593-4508-9a7c-2cebceb5421c)

## Truthtable
## HALF SUBTRACTOR
![HSTT](https://user-images.githubusercontent.com/120230694/232977257-40ef21e8-1660-4abe-8502-146addf8c65a.png)

## FULL SUBTRACTOR
![FSTT](https://user-images.githubusercontent.com/120230694/232977285-6f9c2b1f-490a-4b3a-9a4b-0230795ec178.png)




## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
