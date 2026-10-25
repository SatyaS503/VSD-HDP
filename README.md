Week 1

Tools Installation

Yosys

<img width="1286" height="807" alt="image" src="https://github.com/user-attachments/assets/2fdb8b89-0bc5-4bfc-b290-947e3bd2f81f" />

IVerilog
<img width="1277" height="800" alt="image" src="https://github.com/user-attachments/assets/c2b9b511-46af-4e6a-9927-3ddb309471af" />

GTK Wave
<img width="1282" height="800" alt="image" src="https://github.com/user-attachments/assets/cba61654-30b3-4d1b-84d6-f57e39b31c46" />

Week 2 

Iverilog

good_mux.v


module good_mux (input i0 , input i1 , input sel , output reg y);
always @ (*)
begin
	if(sel)
		y <= i1;
	else 
		y <= i0;
end
endmodule

tb_good_mux.v


`timescale 1ns / 1ps
module tb_good_mux;
	// Inputs
	reg i0,i1,sel;
	// Outputs
	wire y;

        // Instantiate the Unit Under Test (UUT)
	good_mux uut (
		.sel(sel),
		.i0(i0),
		.i1(i1),
		.y(y)
	);

	initial begin
	$dumpfile("tb_good_mux.vcd");
	$dumpvars(0,tb_good_mux);
	// Initialize Inputs
	sel = 0;
	i0 = 0;
	i1 = 0;
	#300 $finish;
	end

always #75 sel = ~sel;
always #10 i0 = ~i0;
always #55 i1 = ~i1;
endmodule


GTKWAVE

<img width="2934" height="1666" alt="A3BE3041-4B85-4934-9E5E-CAAF59D22036" src="https://github.com/user-attachments/assets/402e94af-e245-449e-ac9a-c29074c9da90" />





