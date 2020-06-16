# first_time
Checking if the code works

module PWM(
input clock,
input [5:0]speed,
input reset,
output PWM_wave
    );
endmodule

reg [21:0] counter; // we are counting up to 1,666,667s
reg [21:0] width; 
reg PWM_out;

initial begin
counter = 0;
width = 0;
PWM_out = 0;
end 

always@(posedge clock) begin
   if (reset)
       counter <= 0;
   else 
       counter <= counter + 1;
   
   if (counter < width)
       PWM_out <= 1;
    else
       PWM_out <= 0;
       
 always @ (*) begin
      case(speed)
//speed   //width               // duty cycle %

6'd0	: width = 22'd0;	    //0%
6'd1	: width = 22'd26042;	//1.5625%
6'd2	: width = 22'd52084;	//3.125%
6'd3	: width = 22'd78126;	//4.6875%
6'd4	: width = 22'd104168;	//6.25%
6'd6	: width = 22'd156252;	//9.375%
6'd7	: width = 22'd182294;	//10.9375%
6'd8	: width = 22'd208336;	//12.5%
6'd9	: width = 22'd234378;	//14.0625%
6'd10	: width = 22'd260420;	//15.625%
6'd11	: width = 22'd286462;	//17.1875%
6'd12	: width = 22'd312504;	//18.75%
6'd13	: width = 22'd338546;	//20.3125%
6'd15	: width = 22'd390630;	//23.4375%
6'd16	: width = 22'd416672;	//25%
6'd17	: width = 22'd442714;	//26.5625%
6'd18	: width = 22'd468756;	//28.125%
6'd19	: width = 22'd494798;	//29.6875%
6'd20	: width = 22'd520840;	//31.25%
6'd21	: width = 22'd546882;	//32.8125%
6'd22	: width = 22'd572924;	//34.375%
6'd23	: width = 22'd598966;	//35.9375%
6'd24	: width = 22'd625008;	//37.5%
6'd25	: width = 22'd651050;	//39.0625%
6'd26	: width = 22'd677092;	//40.625%
6'd27	: width = 22'd703134;	//42.1875%
6'd28	: width = 22'd729176;	//43.75%
6'd29	: width = 22'd755218;	//45.3125%
6'd30	: width = 22'd781260;	//46.875%
6'd31	: width = 22'd807302;	//48.4375%
6'd32	: width = 22'd833344;	//50%
6'd33	: width = 22'd859386;	//51.5625%
6'd34	: width = 22'd885428;	//53.125%
6'd35	: width = 22'd911470;	//54.6875%
6'd36	: width = 22'd937512;	//56.25%
6'd37	: width = 22'd963554;	//57.8125%
6'd38	: width = 22'd989596;	//59.375%
6'd39	: width = 22'd1015638;	//60.9375%
6'd40	: width = 22'd1041680;	//62.5%
6'd41	: width = 22'd1067722;	//64.0625%
6'd42	: width = 22'd1093764;	//65.625%
6'd43	: width = 22'd1119806;	//67.1875%
6'd44	: width = 22'd1145848;	//68.75%
6'd45	: width = 22'd1171890;	//70.3125%
6'd46	: width = 22'd1197932;	//71.875%
6'd47	: width = 22'd1223974;	//73.4375%
6'd48	: width = 22'd1250016;	//75%
6'd49	: width = 22'd1276058;	//76.5625%
6'd50	: width = 22'd1302100;	//78.125%
6'd51	: width = 22'd1328142;	//79.6875%
6'd52	: width = 22'd1354184;	//81.25%
6'd53	: width = 22'd1380226;	//82.8125%
6'd54	: width = 22'd1406268;	//84.375%
6'd55	: width = 22'd1432310;	//85.9375%
6'd56	: width = 22'd1458352;	//87.5%
6'd57	: width = 22'd1484394;	//89.0625%
6'd58	: width = 22'd1510436;	//90.625%
6'd59	: width = 22'd1536478;	//92.1875%
6'd60	: width = 22'd1562520;	//93.75%
6'd61	: width = 22'd1588562;	//95.3125%
6'd62	: width = 22'd1614604;	//96.875%
6'd63	: width = 22'd1640646;	//98.4375%
     
endcase
end 
      
assign PWM_wave = PWM_out;
  
endmodule

