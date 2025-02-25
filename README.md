# Design and simulate 6 bit parity generator using Verilog.

# THEORY
*The parity generating technique is one of the most widely used error detection techniques for the data transmission. In digital systems, when binary data is transmitted and processed, data may be subjected to noise so that such noise can alter 0s (of data bits) to 1s and 1s to 0s.

*Hence, a Parity Bit is added to the word containing data in order to make number of 1s either even or odd. The message containing the data bits along with parity bit is transmitted from transmitter to the receiver.

 *Parity Generator is a combinational logic circuit that generates the parity bit in the transmitter. On the other hand, a circuit that checks the parity in the receiver is called Parity Checker. A combined circuit or device of parity generators and parity checkers are commonly used in digital systems to detect the single bit errors in the transmitted data.


# NETLIST DIAGRAM
![Screenshot (19)](https://github.com/sarveshjustin/Simulation-project--Digital-Electronics/assets/113497481/987cb43c-8da2-428e-8b3d-2c838e241a00)


# TIMING DIAGRAM
![Screenshot (21)](https://github.com/sarveshjustin/Simulation-project--Digital-Electronics/assets/113497481/09eb6ee8-47f0-4145-937d-ed4418d9b44f)


# PROGRAM
### To design:
```
module parity (
  input [5:0] data,
  output parity
);

  wire [5:0] xor_result;
  
  assign xor_result[0] = data[0] ^ data[1];
  assign xor_result[1] = xor_result[0] ^ data[2];
  assign xor_result[2] = xor_result[1] ^ data[3];
  assign xor_result[3] = xor_result[2] ^ data[4];
  assign xor_result[4] = xor_result[3] ^ data[5];
  assign xor_result[5] = xor_result[4] ^ xor_result[3];

  assign parity = xor_result[5];

endmodule
```

This project is done by sarvesh.s  (212222230135)
