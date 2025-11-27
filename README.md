# FULL_ADDER_SUBTRACTOR
### Name:G SANJAY
### Reg No:212224230243
Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**

FULL ADDER

![image](https://github.com/user-attachments/assets/393c5811-b153-4f68-b063-bf81e7320ea7)

FULL SUBTRACTOR

![image](https://github.com/user-attachments/assets/85f24e14-8db7-4b0a-ae39-fbc0338e14bb)


**Procedure**

1. Type the program in Quartus software.

2. Compile and run the program.

3. Generate the RTL schematic and save the logic diagram.

4. Create nodes for inputs and outputs to generate the timing diagram.

5. For different input combinations generate the timing diagram.



**Program:**


```
module fulladdsub(a,b,c,sum,carry,diff,borrow);

input a,b,c;

output sum,carry,diff,borrow;

wire w1,w2,w3;

assign sum=a^b^c;

assign w1=a&b;

assign w2=b&c;

assign w3=c&a;

assign carry=w1|w2|w3;

wire w4, w5, w6, w7;

xor g1(diff, a, b, c);

not g2(w4, a);          

and g3(w5, w1, c);    

and g4(w6, w1, b);     

and g5(w7, b, c);     

or g6(borrow, w5, w6, w7); 

endmodule
```

**RTL Schematic**

<img width="743" alt="Screenshot 2024-11-22 144000" src="https://github.com/user-attachments/assets/2e7b8c62-9675-4ec4-bb50-74ce1f5c2b5a">


**Output Timing Waveform**

<img width="956" alt="Screenshot 2024-11-22 144446" src="https://github.com/user-attachments/assets/6f3513e6-dcd9-4619-8dbe-0e7658c1d9d7">




**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



