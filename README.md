# Exercise-07-Multiplexer-and-De-multiplexer

# AIM
 To implement 4 X1 multiplexer and 1X4 de multiplexer using verilog and validate its outputs
## HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
## SOFTWARE REQUIRED:   Quartus prime
# THEORY 

## What are Multiplexer and Demultiplexer?
In-network transmission, both the multiplexer and demultiplexer are combinational circuits. A multiplexer selects an input from several inputs then it is transmitted in the form of a single line. An alternative name of the multiplexer is MUX or data selector. A demultiplexer uses one input signal and generates many. So it is known as Demux or data distributor.

## What is a Multiplexer?
The multiplexer is a device that has multiple inputs and single line output. The select lines determine which input is connected to the output, and also increase the amount of data that can be sent over a network within a certain time. It is also called a data selector.

The single-pole multi-position switch is a simple example of a non-electronic circuit of the multiplexer, and it is widely used in many electronic circuits. The multiplexer is used to perform high-speed switching and is constructed by electronic components.

![image](https://user-images.githubusercontent.com/36288975/170912485-73c395c7-23c0-4e78-a53d-a2f0d07d9662.png)
          Figure-01 multiplexer block diagram 

Multiplexers are capable of handling both analog and digital applications. In analog applications, multiplexers are made up of relays and transistor switches, whereas in digital applications, the multiplexers are built from standard logic gates. When the multiplexer is used for digital applications, it is called a digital multiplexer.

4-to-1 Multiplexer
The 4X1 multiplexer comprises 4-input bits, 1- output bit, and 2- control bits. The four input bits are namely 0, D1, D2, and D3, respectively; only one of the input bits is transmitted to the output. The o/p ‘q’ depends on the value of control input AB. The control bit AB decides which of the i/p data bit should transmit the output. The following figure shows the 4X1 multiplexer circuit diagram using AND gates. For example, when the control bits AB =00, then the higher AND gates are allowed while remaining AND gates are restricted. Thus, data input D0 is transmitted to the output ‘q”
![image](https://user-images.githubusercontent.com/36288975/170912568-3598c60a-5035-41f3-b0c4-ccedba13aca5.png)


Figure2 4X1 multiplexer 
If the control input is changed to 11, then all gates are restricted except the bottom AND gate. In this case, D3 is transmitted to the output, and q=D0. If the control input is changed to AB =11, all gates are disabled except the bottom AND gate. In this case, D3 is transmitted to the output, and q = D3. The best example of a 4X1 multiplexer is IC 74153. In this IC, the o/p is the same as the i/p. Another example of a 4X1 multiplexer is IC 45352. In this IC, the o/p is the compliment of the i/p


## What is Demultiplexer?
De-multiplexer is also a device with one input and multiple output lines. It is used to send a signal to one of the many devices. The main difference between a multiplexer and a de-multiplexer is that a multiplexer takes two or more signals and encodes them on a wire, whereas a de-multiplexer does reverse to what the multiplexer does.
![image](https://user-images.githubusercontent.com/36288975/170912606-a30e4b74-1726-4430-b245-2c3c3d9c232d.png)
Figure 3 De-multiplexer 
1-4 Demultiplexer
The 1-to-4 demultiplexer comprises 1- input bit, 4-output bits, and control bits. The 1X4 demultiplexer circuit diagram is shown below.![image](https://user-images.githubusercontent.com/36288975/170912683-00fb746a-1d45-4023-91d1-3a70b841073c.png)

![image](https://user-images.githubusercontent.com/36288975/170912741-7cbd52af-7e0d-4be3-b5c6-6fb9c4eca7c9.png)

Figure4 1X4 De-multiplexer 
The i/p bit is considered as Data D. This data bit is transmitted to the data bit of the o/p lines, which depends on the AB value and the control i/p.

When the control i/p AB = 01, the upper second AND gate is permitted while the remaining AND gates are restricted. Thus, only data bit D is transmitted to the output, and Y1 = Data.

If the data bit D is low, the output Y1 is low. IF data bit D is high, the output Y1 is high. The value of the output Y1 depends upon the value of data bit D, the remaining outputs are in a low state.

If the control input changes to AB = 10, then all the gates are restricted except the third AND gate from the top. Then, data bit D is transmitted only to the output Y2; and, Y2 = Data. . The best example of 1X4 demultiplexer is IC 74155.

 
 
# Procedure

1.Start the module using module projname().

2.Declare the inputs and outputs along with the select lines according to the multiplexer and demultiplexer.

3.Use wire to assign intermediate outputs.

4.Use and,or and not gates to get the desired output.

5.End the module.

6.Generate RTL realization and timing diagrams.



# PROGRAM 

Program for flipflops  and verify its truth table in quartus using Verilog programming.

Developed by: JOEL P

RegisterNumber: 212222230057
```py
**Multiplexer**
module mul(d0,d1,d2,d3,a,b,q);
input d0,d1,d2,d3,a,b;
output q;
wire l,m,n,o,abar,bbar;
not(abar,a);
not(bbar,b);
and(l,d0,abar,bbar);
and(m,d1,abar,b);
and(n,d2,a,bbar);
and(o,d3,a,b);
or(q,l,m,n,o);
endmodule

**Demultiplexer**
module demul(d,a,b,y0,y1,y2,y3);
input d,a,b;
output y0,y1,y2,y3;
wire abar,bbar;
not(abar,a);
not(bbar,b);
and(y0,d,abar,bbar);
and(y1,abar,b,d);
and(y2,a,bbar,d);
and(y3,a,b,d);
endmodule
```
# RTL LOGIC  
## Multiplexer

![243699769-604c1769-9ffd-470b-8055-1d73df5a386d](https://github.com/collinsjoel10/Exercise-07-Multiplexer-and-De-multiplexer/assets/118626456/e96fe70e-29d7-4a4c-9a44-7a123afd4902)


## Demultiplexer

![02](https://github.com/collinsjoel10/Exercise-07-Multiplexer-and-De-multiplexer/assets/118626456/06616b3e-f5be-4de9-b964-a845b4cacf87)



# TIMING DIGRAMS

## Multiplexer

![03](https://github.com/collinsjoel10/Exercise-07-Multiplexer-and-De-multiplexer/assets/118626456/2593ea96-c120-437c-9261-22dff4dd35f9)


## Demultiplexer

![04](https://github.com/collinsjoel10/Exercise-07-Multiplexer-and-De-multiplexer/assets/118626456/a654e8ca-a5a6-4076-89da-c0f14b102525)



# TRUTH TABLE 

## Multiplexer

![image](https://github.com/collinsjoel10/Exercise-07-Multiplexer-and-De-multiplexer/assets/118626456/3d1ece5e-3705-49c4-aa8c-2c0d6ef4cb02)


## Demultiplexer

![image](https://github.com/collinsjoel10/Exercise-07-Multiplexer-and-De-multiplexer/assets/118626456/8081cbc3-5a2a-47c7-a246-386f527a783f)


# RESULTS 
Hence 4x1 Multiplexer and 1x4 Demultiplexer is been implemented and verified using verilog programming and its output are validated.

