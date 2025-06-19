# ARITHMETIC-LOGIC-UNIT-ALU-

COMPANY : CODTECH IT SOLUTIONS 

NAME : ADITYA AVINASH GAIKWAD

INTERN ID :CITS0D81

DOMAIN : VLSI

DURATION : 4 WEEKS

MENTOR : NEELA SANTOSH

DESCRIPTION: 

SOFTWARE : MODELSIM

CODE- 


module alu(A,B,OP,alu_out);

input[3:0]A,B;

input[2:0]Op;

output reg[3:0]alu_out;

a;ways@(*)

begin

 case(Op)

      3'b000:alu_out=0;	
	     3'b001:alu_out=A+B;	
             3'b010:alu_out=A-B;	
             3'b011:alu_out=A&B;	
             3'b100:alu_out=A|B;	
             3'b101:alu_out=~A;	
             3'b110:alu_out=~B;	
             3'b111:alu_out=0;
	     default:alu_out=0	
    endcase
   
 
end

 endmodule
 
 //testbench
 
 module TB();
 
 reg [3:0] A, B;
 
 reg [2:0] Op;
 
 wire [3:0] alu_out;
 
alu a1(A,B,Op,alu_out);

initial

begin

 Op=3'b000;A=3'b0011;B=3'b0001;

#10

 Op=3'b001;A=3'b0011;B=3'b0001;

 #10

 Op=3'b010;A=3'b0011;B=3'b0001;

 #10

 Op=3'b011;A=3'b0011;B=3'b0001;

 #10

 end

endmodule

 

OUTPUT:

![Image](https://github.com/user-attachments/assets/b0fa628e-8c86-44a5-8537-84d497e6ea83)


At 0–10 ps:

A = 0011, B = 0001, ALU_Sel = 000

Likely performing Addition (A + B = 0100)

Output ALU_Out = 0100 = 4

At 10–20 ps:

A = 0101, B = 0011, ALU_Sel = 001

Possibly Subtraction or AND/OR (depending on your opcode)

Output ALU_Out = 0010 = 2

At 60 ps:

A = 1111, B = 1111, ALU_Sel = 111

Output ALU_Out = 0000

Output is zero, so Zero flag = 1


