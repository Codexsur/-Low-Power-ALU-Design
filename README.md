# Low-Power ALU Design

A 32-bit Arithmetic Logic Unit implementing multiple power optimization techniques for energy-efficient computing.

## Features

- **16 Operations**: ADD, SUB, MULT, DIV, AND, OR, XOR, NOT, Shifts, Rotates, Comparisons
- **4 Design Variants**: Baseline, Clock-Gated, Multi-VT, Power-Gated
- **Power Savings**: Up to 40% dynamic power reduction, 90% leakage reduction in sleep mode

## Quick Start

```bash
# Simulate with Icarus Verilog
iverilog -o alu_sim rtl/alu_baseline.v tb/alu_tb.v
vvp alu_sim
gtkwave alu_waveform.vcd
```

## Results

| Design | Dynamic Power | Leakage Power | Savings |
|--------|---------------|---------------|---------|
| Baseline | 12.5 mW | 450 μW | - |
| Clock-Gated | 8.2 mW | 450 μW | 34% ↓ |
| Multi-VT | 12.5 mW | 285 μW | 37% ↓ |
| Power-Gated | 7.8 mW | 45 μW | 90% ↓ |

## Power Techniques

- **Clock Gating**: Disables clock to idle units
- **Multi-VT**: Mixed threshold voltages for leakage reduction  
- **Power Gating**: Complete shutdown with state retention

## File Structure

```
├── rtl/          # Verilog source files
├── tb/           # Testbenches
├── synthesis/    # Synthesis scripts
└── docs/         # Reports and diagrams
```

## License

MIT
