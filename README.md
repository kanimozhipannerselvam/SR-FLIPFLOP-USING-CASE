# SR-FLIPFLOP-USING-CASE

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![300539786-0f710028-ad52-4d3e-9276-8714cf023a25](https://github.com/kanimozhipannerselvam/SR-FLIPFLOP-USING-CASE/assets/119476060/336992d6-0898-477d-9eb3-e37f638e60a6)

 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

 ![300539899-dabfc4f4-87e3-4cbc-9472-f89ee1b5ed30](https://github.com/kanimozhipannerselvam/SR-FLIPFLOP-USING-CASE/assets/119476060/c2b96bc0-57f2-41c0-a184-7abb7fc89905)

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![300540000-dd90d16c-aec5-4290-a586-e2346b1e9eb5](https://github.com/kanimozhipannerselvam/SR-FLIPFLOP-USING-CASE/assets/119476060/3b0e74b6-f34a-427a-b9fe-10f399484c11)


 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![300540120-473efad6-d70b-4ca7-aeb7-898bbfca319f](https://github.com/kanimozhipannerselvam/SR-FLIPFLOP-USING-CASE/assets/119476060/a733e591-afab-41b9-b832-f2e094283529)


 
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**
STEP 1:Type the program in Quartus software.

STEP 2:Compile and run the program.

STEP 3:Generate the RTL schematic and save the logic diagram.

STEP 4:Create nodes for inputs and outputs to generate the timing diagram.

STEP 5:For different input combinations generate the timing diagram.

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. Developed by: KANIMOZHI
RegisterNumber: 212222230060
*/
```
module ex06(q,q_bar,s,r,clk,reset);
//SR Flip Flop Behavioural Level using "case"
input s,r,clk,reset;
output reg q;
output q_bar;
always@(posedge clk)begin //for synchronous reset
if (!reset) q<=0;
else
begin
case({s,r})
2'b00:q<=q;//no change
2'b01:q<=1'b0; //write logic for reset
2'b10:q<=1'b1; //write logic for set
2'b11:q<=1'bx; //write logic for Invalid state
endcase
end
end
assign q_bar=~q;
endmodule
```

**RTL LOGIC FOR FLIPFLOPS**

![325689346-58292396-6fb6-431c-89da-0319dc9ba4b4](https://github.com/kanimozhipannerselvam/SR-FLIPFLOP-USING-CASE/assets/119476060/e3708abe-b232-41fa-9cba-7fadd99ae96e)


**TIMING DIGRAMS FOR FLIP FLOPS**

![325689433-f3ca2b2c-8ba2-4df5-b4d8-c6891317158e](https://github.com/kanimozhipannerselvam/SR-FLIPFLOP-USING-CASE/assets/119476060/90c07e81-bd46-4532-9311-41476fec4d71)



**RESULTS**
Thus the program to implement a SR flipflop using verilog and validating their functionality using their functional tables is successfully completed.
