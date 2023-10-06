## Developed by: SANTHOSH S
## RegisterNumber: 212222100047
## Experiment--04-Half-Subtractor-and-Full-subtractor

## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:

To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.
## Equipments Required:
Hardware – PCs, Cyclone II , USB flasher
Software – Quartus prime
## Theory

Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.
## Half Subtractor Full Subtractor
## Half Subtractor

The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed. half-subtractor9
![image](https://github.com/MrSanthosh-dev/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/117916573/f0a85d45-4434-48d5-bcbb-291748140905)

Sum = X'Y+XY' = X ⊕ Y Carry=X'Y
## Full Subtractor

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. full-subtractor6
![image](https://github.com/MrSanthosh-dev/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/117916573/5f1de127-7906-4540-9df4-88611ce2c27e)

Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin
## Procedure:-

  1. Create a New Project:
```
  *Open Quartus and create a new project by selecting "File" > "New Project Wizard."
  *Follow the wizard's instructions to set up your project, including specifying the project name, location, and target device (FPGA).
```
  2. Create a New Design File:
```
  *Once the project is created, right-click on the project name in the Project Navigator and select "Add New File."
  *Choose "Verilog HDL File" or "VHDL File," depending on your chosen hardware description language.
```
  3. Write the Combinational Logic Code:
```
  *Open the newly created Verilog or VHDL file and write the code for your combinational logic.
```
  4.Compile the Project:
```
  *To compile the project, click on "Processing" > "Start Compilation" in the menu.
  *Quartus will analyze your code, synthesize it into a netlist, and perform optimizations based on your target FPGA device.
```
  5. Analyze and Fix Errors:*
```
  *If there are any errors or warnings during the compilation process, Quartus will display them in the Messages window.
  *Review and fix any issues in your code if necessary.
  *View the RTL diagram.
```
6.Verification:
```
  *Click on "File" > "New" > "Verification/Debugging Files" > "University Program VWF".
  *Once Waveform is created Right Click on the Input/Output Panel > " Insert Node or Bus" > Click on Node Finder > Click On "List" > Select All.
  *Give the Input Combinations according to the Truth Table amd then simulate the Output Waveform.
```
## Program:
## Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
## Developed by: SANTHOSH S
## RegisterNumber: 212222100047
## Half subtractor:
```
module half(a,b,s,c);
input a,b;
output s,c;
assign s = a^b;
assign c = ~a&b;
endmodule
```
## Full subtractor:
```
module fsub(a,b,bin,diff,borrow);
input a,b,bin;
output diff,borrow;
assign diff = a^b^bin;
assign borrow = ~a&b | ~(a^b)&bin;
endmodule
```

## Output:
## Truthtable:
## Half subtractor:

![image](https://github.com/MrSanthosh-dev/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/117916573/a9626fb5-6cb0-487e-a8b1-1870adfcbd55)
## Full subtractor:
![image](https://github.com/MrSanthosh-dev/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/117916573/873ed9d9-47f4-443e-b18d-4e797038c3da)

## RTL realization
## Half subtractor:

![image](https://github.com/MrSanthosh-dev/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/117916573/4cbc4bcd-e756-4b11-9bc4-4883f9b3f8e4)
## Full subtractor:
![image](https://github.com/MrSanthosh-dev/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/117916573/f94da79e-64c6-40ac-8742-a655f0cead0f)

## Timing diagram:
## Half subtractor:
![image](https://github.com/MrSanthosh-dev/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/117916573/33353fcc-63a8-4617-8dc5-0e10123144ae)


## Full subtractor:

![image](https://github.com/MrSanthosh-dev/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/117916573/0c66cc50-8a07-44b5-b7ca-448884113ee1)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
