# FULL_ADDER_SUBTRACTOR

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

Full Adder

<img width="429" height="395" alt="388825036-4d112be1-6902-42f6-a80f-d6ffa1814c34" src="https://github.com/user-attachments/assets/f93a50f1-079d-442c-9287-302a1d3f1270" />

Full Subtractor

<img width="438" height="393" alt="388825191-affd2a74-295b-48dc-b7c5-3e2de75db7d3" src="https://github.com/user-attachments/assets/31988baf-dd28-420d-b87d-2d69672bcaac" />



**Procedure**

Write the detailed procedure here

**Program:**
Full Adder
```
module exp4(df,bo,a,b,bin);
output df;
output bo;
input a;
input b;
input bin;
wire w1,w2,w3;
assign w1=a^b;
assign w2=(~a&b);
assign w3=(~w1&bin);
assign df=w1^bin;
assign bo=w2|w3;
endmodule
```
Full Subtractor
```
module full_subtractor(diff, borrow, a, b, bin);
output diff;
output borrow;
input a;
input b;
input bin;
assign diff = a ^ b ^ bin;
assign borrow = (~a & b) | (~(a ^ b) & bin);
endmodule
```

**RTL Schematic**
<img width="1464" height="574" alt="Screenshot 2025-11-19 113548" src="https://github.com/user-attachments/assets/7ec47418-3a9c-44c6-87e4-233444869fc2" />
<img width="1497" height="567" alt="Screenshot 2025-11-19 114608" src="https://github.com/user-attachments/assets/098d54ad-59df-4074-add5-cec035bad9da" />

**Output Timing Waveform**
<img width="1581" height="252" alt="Screenshot 2025-11-19 113902" src="https://github.com/user-attachments/assets/e50f89a5-f38a-40cf-bd34-69b6623a4333" />

<img width="1599" height="227" alt="Screenshot 2025-11-19 114914" src="https://github.com/user-attachments/assets/e4d150ef-799f-453c-bf27-a6d16ec19317" />

**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



