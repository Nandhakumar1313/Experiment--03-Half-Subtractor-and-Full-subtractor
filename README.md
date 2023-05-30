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
```py
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by:212222100029 
RegisterNumber:Nandhakumar G R 

module half_sub(x, y, d, b, x1);
input x,y;
output x1, d, b;
xor(d, x, y);
not(x1, x);
and(b, x1, y);
endmodule

module full_sub(x, y, z, d, b, x1, x2, x3, x4, x5);
input x,y,z;
output d, b, x1, x2, x3, x4 ,x5;
xor(x1, x, y);
xor(d, x1, z);
not(x2, x);
and(x3, x2, y);
and(x4, x3, z);
and(x5, y, z);
or(b, x3, x4, x5);
endmodule

```

## Output:
##  RTL realization
![Screenshot (135)](https://github.com/Nandhakumar1313/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/120230694/5d1850aa-449e-4837-8975-12d3f89c3f31)




![Screenshot (136)](https://github.com/Nandhakumar1313/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/120230694/cd685f14-8aac-46d2-983b-5b3ca4f77f31)




## Timing diagram 



![hs2](https://user-images.githubusercontent.com/120230694/232976877-9cc736e6-7a6d-40b2-bc76-83f89c8dc24a.png)

![fs2](https://user-images.githubusercontent.com/120230694/232976905-653f7fb9-de3e-4c53-a6b9-be3c261f1495.png)

## Truthtable

![HSTT](https://user-images.githubusercontent.com/120230694/232977257-40ef21e8-1660-4abe-8502-146addf8c65a.png)


![FSTT](https://user-images.githubusercontent.com/120230694/232977285-6f9c2b1f-490a-4b3a-9a4b-0230795ec178.png)




## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
