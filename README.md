# Design and simulate 6 bit parity generator using Verilog.

# THEORY

# LOGIC DIAGRAM

# NETLIST DIAGRAM
![Screenshot (19)](https://github.com/sarveshjustin/Simulation-project--Digital-Electronics/assets/113497481/987cb43c-8da2-428e-8b3d-2c838e241a00)


# TIMING DIAGRAM

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

# REFERENCE

