// 2x1Multiplexers-->#3,  4x1 multiplexers-->#3, AND_Gate-->#3,  Full_Adders-->#3  .



// Here, I've created a module for 2x1 multiplexer called M2, has 4 parameters.
module M2(in0 , in1 , s , out) ; 
// At this 2x1 MUX we've 3-inputs called "in0, in1, s", so I've created them
input in0, in1, s ;
// At this 2x1 MUX we've 1-outputs called "out" to be the ouput of this 2x1 MUX, so I've created it
output out ;
// I've created a 3-wires called "O1, O2, O3", to be as variables to link between gates. 
wire O1, O2, O3 ; 
// I've a gate "AND" and called it "instr1", takes 2-inputs called "in1, s" and store the result to output called "O1" 
and instr1(O1, in1, s) ;
// Here I assinged O2 to be NOT of "s" to it.  
assign O2 = ~s ; 
// I've a gate "AND" and called it "instr3", takes 2-inputs called "in0, O2" and store the result to output called "O3" 
and instr3(O3, in0, O2) ; 
// I've a gate "OR" and called it "instr4", takes 2-inputs called "O1, O3" and store the result to output called "out" 
or instr4(out, O1, O3) ; 
// Here, I've ended the module called M2
endmodule




// Here, I've created a module for 4x1 multiplexer called M4, has 7 parameters.
module M4(in0, in1, in2, in3, s0, s1, out) ;
// At this 4x1 MUX we've 6-inputs called "in0, in1, in2, in3, s0, s1", so I've created them 
input in0, in1, in2, in3, s0, s1 ; 
// At this 4x1 MUX we've 1-outputs called "out" to be the ouput of this 4x1 MUX, so I've created it
output out ; 
// I've created a 6-wires called "s0G, s1G, O1, O2, O3, O4", to be as variables to link between gates.
wire s0G, s1G, O1, O2, O3, O4 ; 
// Here I assinged s0G to be NOT of "~s0" to it.
assign s0G = ~s0 ; 
// Here I assinged s1G to be NOT of "~s1" to it.
assign s1G = ~s1 ; 
// Here I assinged O1 to be the AND of 3-bits called "in0, s0G, s1G" to it.
assign O1 = in0 & s0G & s1G ; 
// Here I assinged O2 to be the AND of 3-bits called "in1, s0, s1G" to it.
assign O2 = in1 & s0 & s1G ;
// Here I assinged O3 to be the AND of 3-bits called "in2, s0G, s1" to it.
assign O3 = in2 & s0G & s1 ;
// Here I assinged O4 to be the AND of 3-bits called "in3, s0, s1" to it.
assign O4 = in3 & s0 & s1 ; 
// I've a gate "OR" and called it "instr7", takes 4-inputs called "O1, O2, O3, O4" and store the result to output called "out"
or instr7(out, O1, O2, O3, O4) ; 
// Here, I've ended the module called M4
endmodule




// Here, I've created a module for full adder called full_adder, has 5 parameters.
module full_adder(in0, in1, in2, sum, carry);
// At this full adder we've 3-inputs called "in0, in1, in2", so I've created them
input in0, in1, in2; 
// At this  full adder we've 2-outputs called "sum, carry" to be the ouput of this full adder, so I've created it
output sum, carry ; 
// I've created a 3-wires called "s1, c1, c2", to be as variables to link between gates. 
wire s1, c1, c2;
// I've a gate "XOR", takes 2-inputs called "in0, in1" and store the result to output called "s1"
xor(s1, in0, in1) ; 
// I've a gate "AND", takes 2-inputs called "in0, in1" and store the result to output called "c1"
and(c1, in0, in1) ; 
// I've a gate "XOR", takes 2-inputs called "s1, in2" and store the result to output called "sum"
xor(sum, s1, in2) ; 
// I've a gate "AND", takes 2-inputs called "s1, in2" and store the result to output called "c2"
and(c2, s1, in2) ; 
// I've a gate "OR", takes 4-inputs called "c1, c2" and store the result to output called "carry"
or(carry, c1, c2) ; 
// Here, I've ended the module called full_adder
endmodule



// Here, I've created a module for a circuit called "circuit", has 14 parameters.
module circuit(A0 , A1 , A2 , B0 , B1 , B2 , s0 , s1 , D0 , D1 , D2, carry) ; 
// At this circuit we've 8-inputs called "A0, A1, A2, B0, B1, B3, s0, s1", so I've created them
input A0 , A1 , A2 , B0 , B1 , B2 , s0 , s1 ;
// At this circuit we've 4-outputs called "D0, D1, D2, carry" to be the ouput of this circuit, so I've created it
output D0 , D1 , D2, carry ;
// I've created a 9-wires called "w, l0, l1, l2, m0, m1, m2, c1, c2", to be as variables to link between gates. 
wire w , l0 , l1 , l2 , m0 , m1 , m2 , c1 , c2  ;
// Create a variable called "one" to assing 1-bit with value "1" 
assign one = 1 ; 
// Create a variable called "zero" to assing 1-bit with value "0" 
assign zero = 0 ; 
// I've a gate "AND", takes 2-inputs called "s0, s1" and store the result to output called "w"
and( w, s0 , s1) ;
// Here I connect the compenents between each other at 2x1 MUX 
M2 L0(.in0(A0) , .in1(~B0) ,.s(w) , .out(l0)) ;  
// Here I connect the compenents between each other at 4x1 MUX
M4 M0( .in0(one), .in1(B0) , .in2(~B0) , .in3(zero) , .s0(s0) , .s1(s1) , .out(m0)) ;    
// Here I connect the compenents between each other at full_adder
full_adder F0( .in0(l0), .in1(m0) , .in2(s1) , .sum(D0) , .carry(c1) ) ; 


// Here I connect the compenents between each other at 2x1 MUX 
M2 L1(.in0(A1) , .in1(~B1) ,.s(w) , .out(l1)) ;
// Here I connect the compenents between each other at 4x1 MUX
M4 M1( .in0(one), .in1(B1) , .in2(~B1) , .in3(zero) , .s0(s0) , .s1(s1) , .out(m1)) ; 
// Here I connect the compenents between each other at full_adder
full_adder F1( .in0(l1), .in1(m1) , .in2(c1) , .sum(D1) , .carry(c2) ) ;


// Here I connect the compenents between each other at 2x1 MUX 
M2 L2(.in0(A2) , .in1(~B2) ,.s( w) , .out(l2)) ;
// Here I connect the compenents between each other at 4x1 MUX
M4 M2( .in0(one), .in1(B2) , .in2(~B2) , .in3(zero) , .s0(s0) , .s1(s1) , .out(m2)) ; 
// Here I connect the compenents between each other at full_adder
full_adder F2( .in0(l2), .in1(m2) , .in2(c2) , .sum(D2) , .carry(carry) ) ;


// Here, I've ended the module called circuit
endmodule



// Here the test bench for 40-test_cases, I tested the full circuit to be sure everything is working well, and all is good.
module circuit_test;
// I've created a 8-variables of type "reg" called "A0 , A1 , A2 , B0 , B1 , B2 , s0 , s1", to be as inputs of the tested circuit.
reg A0 , A1 , A2 , B0 , B1 , B2 , s0 , s1 ;
// I've created a 4-variables of type wire called "D0 , D1 , D2, carry", to be as outputs of the tested circuit. 
wire D0 , D1 , D2, carry;
// Here is, I called the circuit module and called it "cir", this "cir" has a 12-parameters
circuit cir(A0 , A1 , A2 , B0 , B1 , B2 , s0 , s1 , D0 , D1 , D2, carry) ; 
// Here is, the word "initial" syntax to set the the 0-sec for a first step for test bench
initial
// Here is, the word "begin" syntax to start the steps of sec for test bench.
begin
// Here is, the word "$monitor" to show at the screen the current time or current sec, the inputs and the outputs at each sec    
$monitor($time, " A0=%b, A1=%b, A2=%b, B0=%b, B1=%b, B2=%b, s1=%b, s0=%b, D0=%b, D1=%b, D2=%b, carry=%b", A0 , A1 , A2 , B0 , B1 , B2 , s1 , s0 , D0 , D1 , D2, carry);
// Here is, I set all the inputs to "zero" at the beginning of test bench at 0-sec.
A0=0; A1=0; A2=0; B0=0; B1=0; B2=0; s0=0; s1=0 ; 
// Here, I created a loop to iterate through the 40-test_bench, then start the loop. 
for (integer i=0; i<40; i=i+1)begin
// Here, every "10" sec, all the inputs generate randomly at each iteration. 
#10 A0<=$random; A1<=$random; A2<=$random; B0<=$random; B1<=$random; B2<=$random; s0<=$random; s1<=$random ;
// Here, the loop has been ended after finishing 40 iterations.
end
// Here, the "monitor" has been finished. 
$finish;
// Here, the sec has been ended.
end
// Here, to end the circuit_test module 
endmodule







/*   it's useless for the test bench but it's usefull for me, Here I tested the 2x1 MUX to be sure that each compenents working well
module M2_test;
reg in0, in1, s;
wire out;
M2 mux(in0, in1, s, out) ; 
initial
begin
$monitor($time, " in0=%b, in1=%b, s=%b, out=%b", in0, in1, s, out);
in0=0; in1=0; s=0; 
for (integer i=0; i<40; i=i+1)begin
#10 in0<=$random; in1<=$random; s<=$random;
end
$finish;
end
endmodule
*/

/* it's useless for the test bench but it's usefull for me, here I tested the 4x1 MUX to be sure that each compenents working well,  
module M4_test;
reg in0, in1, in2, in3, s0, s1;
wire out;
M4 mux(in0, in1, in2, in3, s0, s1, out) ; 
initial
begin
$monitor($time, " in0=%b, in1=%b, in2=%b, in3=%b, s0=%b, s1=%b, out=%b", in0, in1, in2, in3, s0, s1, out);
in0=0; in1=0; in2=0; in3=0; s0=0; s1=0 ; 
for (integer i=0; i<40; i=i+1)begin
#10 in0<=$random; in1<=$random; in2<=$random; in3<=$random; s0<=$random; s1<=$random; ;
end
$finish;
end
endmodule
*/


/*  it's useless for the test bench but it's usefull for me, here I tested the full_adder to be sure that each compenents working well
module full_adder_test;
reg in0, in1, in2 ;
wire sum, carry;
full_adder fullAdder(in0, in1, in2, sum, carry) ; 
initial
begin
$monitor($time, " in0=%b, in1=%b, in2=%b, sum=%b, carry=%b", in0, in1, in2, sum, carry);
in0=0; in1=0; in2=0;
for (integer i=0; i<4; i=i+1)begin
#10 in0<=$random; in1<=$random; in2<=$random;
end
$finish;
end
endmodule
*/





