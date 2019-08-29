# RISC-V
RISC-V studying

## Architecture prefix
- *RV32* prefix - 32bit ISA
- *RV64* prefix - 64bit ISA
- **XLEN** - register's width

## Subset ISAs
- *I* - (RV32I) Base Integer ISA: integer compontational instructions, integer loads, integer stores, control flow.
- *M* - Multiplication and Devision extension: Multiply and devided from integer registers
- *A* - Atomic IDA: read, write modify for inter-processor synchronization
- *F* - Single-precision Floating-point extension: floating-point registers, single-precision computational instructions, and single-precision loads and stores
- *D* - Double-precision Floating-point extension: floating-point registers, double-precision computational instructions, and double-precision loads and stores
- *IMAFD* or *G* - All of the obove: general purpose scalar instruction set.

## Registers
- x0 = 0
- x1-x31 - XLEN General Purpose
- pc - Program Counter, current instruction

### Register Convention
There is no dedicatate register for stack pointer or subroutines return address. Convention is:
- x1: subroutine return address;
- x5: alternative link register;
- x2: stack pointer;

## Code formats
- bits:
  - f : function
  - d : destination register
  - c : opcode
  - i : immediate
  - s : source register 1
  - S : source register 2

- R-type - `fffffffSSSSSsssssfffdddddccccccc`
  - 0-6 - opcode
  - 7-11 - rd
  - 12-14 - funct3
  - 15-19 - rs1
  - 20-24 - rs2
  - 25-31 - funct7
- I-type - `iiiiiiiiiiiisssssfffdddddccccccc`
  - 0-6 - opcode
  - 7-11 - rd
  - 12-14 - funct3
  - 15-19 - rs1
  - 20-31 - imm[11:0]
- S-type - `iiiiiiiSSSSSsssssfffiiiiiccccccc`
  - 0-6 - opcode
  - 7-11 - imm[4:0]
  - 12-14 - funct3
  - 15-19 - rs1
  - 20-24 - rs2
  - 25-31 - imm[11:5]
- U-type - `iiiiiiiiiiiiiiiiiiiidddddccccccc`
  - 0-6 - opcode
  - 7-11 - rd
  - 12-31 - imm[31:12]
- B-type - `iiiiiiiSSSSSsssssfffiiiiiccccccc`
  - 0-6 - opcode
  - 7 - imm[11]
  - 8-11 - imm[4:1]
  - 12-14 - funct3
  - 15-19 - rs1
  - 20-24 - rs2
  - 25-30 - imm[10:5]
  - 31 - imm[12]
- J-type - `iiiiiiiiiiiiiiiiiiiidddddccccccc`
  - 0-6 - opcode
  - 7-11 - rd
  - 12-19 - imm[19:12]
  - 20 - imm[11]
  - 21-30 - imm[10:1]
  - 31 - imm[20]

  