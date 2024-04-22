# VLSI-LAB-EXPERIMENTS
# SIMULATE AND SYNTHESIS OF LOGIC GATES ,ADDERS AND SUBTRACTORS
AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

APPARATUS REQUIRED: Vivado™ ML 2023.2

PROCEDURE:

Open Vivado: Launch Xilinx Vivado software on your computer.

Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design.

Logic Diagram :

Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)



Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)



VERILOG CODE:

```
module fulladder(sum,cout, a,b,c);
input a,b,c;
output sum,cout;
  wire w1,w2,w3,w4,w5;
  xor x1(w1,a,b);
  xor x2(sum,w1,c);  
  and a1(w2,a,b);
  and a2(w3,b,c);
  and a3(w4,a,c);
  
  or o1(w5,w2,w3);
  or o2(cout,w5,w4);
    
endmodule
```
OUTPUT

 simulation
![image](https://github.com/Thulasiraman04/VLSI-LAB-EXP-1/assets/161105890/ff3329b9-5e88-4858-bf3b-a7492d98ce1d)

Elaborated Design:

![image](https://github.com/Thulasiraman04/VLSI-LAB-EXP-1/assets/161105890/feec878a-0f0e-4345-b0e2-33a5457e3430)

#2:-

FULL_SUBTRAC
TOR:-

Code:

```
module full_sub(borrow,diff,a,b,c);
output borrow,diff;
input a,b,c;
wire w1,w4,w5,w6;
xor (diff,a,b,c);
not n1(w1,a);
and a1(w4,w1,b);
and a2(w5,w1,c);
and a3(w6,b,c);
or o1(borrow,w4,w5,w6);
endmodule
```
OUTPUT:-

Simulation:

![image](https://github.com/Thulasiraman04/VLSI-LAB-EXP-1/assets/161105890/42b1845c-4323-44ba-9735-2f6440a3e59b)

Elaborated Design:
![image](https://github.com/Thulasiraman04/VLSI-LAB-EXP-1/assets/161105890/522a8ac1-48ce-41fb-b108-a1e91f9b9dda)
#3:-

HALF_ADDER:-

Code:
```
module half_adder(a,b,sum,carry);
input a,b;
output sum,carry; // sum and carry
or(sum,a,b);
and(carry,a,b);
endmodule
```
OUTPUT:-

Simulation
![image](https://github.com/Thulasiraman04/VLSI-LAB-EXP-1/assets/161105890/9cadabae-71cd-46c6-868e-af113be50495)
Elaborated Design:

![image](https://github.com/Thulasiraman04/VLSI-LAB-EXP-1/assets/161105890/38117d35-a836-4f27-a1ce-7ce48e5a1ba0)
#4 HALF_SUBTRACTOR:-

Code:
```
module halfsubtractor( D,Bo,A,B);
input A,B;
output D,Bo;
wire w1;
xor (D,A,B);
not (w1,B);
and (Bo,B,w1);
endmodule
```
OUTPUT:-

Simulation:

![image](https://github.com/Thulasiraman04/VLSI-LAB-EXP-1/assets/161105890/9829a38c-b7b6-45cb-9c0c-8a53fa744f6b)
 Elaborated Design:

![image](https://github.com/Thulasiraman04/VLSI-LAB-EXP-1/assets/161105890/46c52585-0d0b-45c7-bce3-846e0ea3e3bc)

#5 LOGIC_GATES:-

Code:
```
module logicgates(a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate);
input a,b;
output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate;
and(andgate,a,b);
or(orgate,a,b);
xor(xorgate,a,b);
nand(nandgate,a,b);  
nor(norgate,a,b);
xnor(xnorgate,a,b);
not(notgate,a);
endmodule
````

OUTPUT:

Simulation:

![image](https://github.com/Thulasiraman04/VLSI-LAB-EXP-1/assets/161105890/fee1107f-8527-4a44-91b2-33483581e99a)

Elaborated Design:

![image](https://github.com/Thulasiraman04/VLSI-LAB-EXP-1/assets/161105890/90ff5810-bedc-4046-a492-c9b16ec0a63f)

#6

RIPPLE_CARRY_Adder(4-BIT):-

Code:
```
module rippe_adder(S, Cout, X, Y,Cin);
input [3:0] X, Y;// Two 4-bit inputs
input Cin;
output [3:0] S;
output Cout;
wire wl, w2, w3;

fulladder u1(S[0], w1,X[0], Y[0], Cin);
fulladder u2(S[1], w2,X[1], Y[1], w1);
fulladder u3(S[2], w3,X[2], Y[2], w2);
fulladder u4(S[3], Cout,X[3], Y[3], w3);
endmodule
module fulladder(S, Co, X, Y, Ci);
input X, Y, Ci;
output S, Co;
wire w1,w2,w3;
//Structural code for one bit full adder 
xor G1(wl, X, Y);
xor G2(S, w1, Ci);
and G3(w2, w1, Ci);
and G4(w3, X, Y);
or  G5(Co, w2, w3);
endmodule
```
OUTPUT:-

Simulation:

![image](https://github.com/Thulasiraman04/VLSI-LAB-EXP-1/assets/161105890/b8f7fc15-327b-468b-88f6-a705a83c8201)
Elaborated Design:

![image](https://github.com/Thulasiraman04/VLSI-LAB-EXP-1/assets/161105890/8d2e03cb-8dc2-4d39-a09e-9eafd16f1940)

#7

RIPPLE_CARRY_ADDER(8-BIT):-

Code:
```
module fulladder(sum,cout, a,b,c);
input a,b,c;
output sum,cout;
  wire w1,w2,w3,w4,w5;
  xor x1(w1,a,b);
  xor x2(sum,w1,c);  
  and a1(w2,a,b);
  and a2(w3,b,c);
  and a3(w4,a,c);
  
  or o1(w5,w2,w3);
  or o2(cout,w5,w4);
    
endmodule

module rippe_adder(S,Cout,X,Y,Cin);
input [7:0] X,Y;
input Cin;
output [7:0] S;
output Cout;
wire w1,w2,w3,w4,w5,w6,w7;
fulladder u1(S[0],w1,X[0],Y[0],Cin);
fulladder u2(S[1],w2,X[1],Y[1],w1);
fulladder u3(S[2],w3,X[2],Y[2],w2);
fulladder u4(S[3],w4,X[3],Y[3],w3);
fulladder u5(S[4],w5,X[4],Y[4],w4);
fulladder u6(S[5],w6,X[5],Y[5],w5);
fulladder u7(S[6],w7,X[6],Y[6],w6);
fulladder u8(S[7],Cout,X[7],Y[7],w7);
endmodule

module fulladder(S,CO,X,Y,Ci);
input X,Y,Ci;
output S,CO;
wire w1,w2,w3;
xor G1(w1,X,Y);
xor G2(S,w1,Ci);
and G3(w2,X,Ci);
and G4(w3,X,Y);
or G5(CO,w3,w3);
endmodule
```
OUTPUT:-

Simulation:

![image](https://github.com/Thulasiraman04/VLSI-LAB-EXP-1/assets/161105890/c24e4b1c-2a88-4213-928c-16ac05cf71c0)

Elaborated Design:


![image](https://github.com/Thulasiraman04/VLSI-LAB-EXP-1/assets/161105890/3d261896-a279-4e0a-9ab5-84672f3abb20)


RESULT : The simulation and synthesis of Logic Gates, Adders and Subtractor using Vivadoo Software are successfully verified
