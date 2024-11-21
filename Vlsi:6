module fsm(
    input rst,
    input clk,
    input in,
    input out
    );

reg out1;
reg [1:0]state;
assign out=out1;
always @ (posedge clk, rst)
begin
	if (rst) begin
		out1=0; state=2'b00;
	end
	else begin	
		case (state) 
		2'b00: begin
			if (in) begin
				state=2'b01;
				out1=1'b0;
			end
			else begin
				state=2'b11;
				out1=1'b1;
			end
	   end
		2'b01: begin
			if (in) begin
				state=2'b11;
				out1=1'b1;
			end
			else begin
				state=2'b10;
				out1=1'b0;
			end
		end
		2'b10: begin
			if (in) begin
				state=2'b00;
				out1=1'b0;
			end
			else begin
				state=2'b01;
				out1=1'b0;
			end
		end
		2'b11: begin
			if (in)	begin
				state=2'b11;
				out1=1'b1;
			end 
			else begin
				state=2'b10;
				out1=1'b0;
			end
		end
		endcase
	end
end
endmodule

TEST BENCH FOR FINITE STATE MACHINE:

module fsm_test;

	// Inputs
	reg rst;
	reg clk;
	reg in;
	reg out;

	// Instantiate the Unit Under Test (UUT)
	fsm uut (
		.rst(rst), 
		.clk(clk), 
		.in(in), 
		.out(out)
	);

	initial begin
		// Initialize Inputs
		rst = 0;
		clk = 0;
		in = 0;
		out = 0;

		// Wait 100 ns for global reset to finish
		#100;
        		rst = 1;
		clk = 1;
		in = 101;
	#100;
        		rst = 1;
		clk = 1;
		in = 110; 
		#100;
        		rst = 1;
		clk = 1;
		in = 101;
	#100;
        		rst = 0;
		clk = 0;
		in = 110; 
		// Add stimulus here

	end
      
endmodule
