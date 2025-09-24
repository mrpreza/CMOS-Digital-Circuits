# CMOS-Digital-Circuits
CMOS digital circuits in SPICE: 1-bit comparator/adder &amp; D flip-flop with timing analysis. 180nm technology, educational &amp; research ready.


## 📋 Overview

This repository contains HSPICE netlists for fundamental digital circuits commonly used in VLSI design and semiconductor engineering. The circuits are designed using 180nm CMOS technology and include comprehensive timing analysis and power measurement capabilities.

## 🔧 Circuits Included

### 1. 1-bit Comparator + Adder (T-Spice1.sp)
A complete 1-bit arithmetic logic unit that performs both comparison and addition operations.

**Features:**
- **Comparison Logic**: Greater Than (GT), Equal To (EQ), Less Than (LT) outputs
- **Addition Logic**: Sum (S) and Carry Out (CO) outputs  
- **Technology**: 180nm CMOS process
- **Supply Voltage**: 1.8V
- **Gate Implementation**: NAND, NOR, XNOR, and Inverter subcircuits

**Functionality:**
- EQ = A XNOR B (equality comparison)
- GT = A AND ~B (A greater than B)
- LT = ~A AND B (A less than B) 
- S = A XOR B (sum output)
- CO = A AND B (carry output)

### 2. D Flip-Flop (mc.sp)
A master-slave D flip-flop implementation for sequential logic applications.

**Features:**
- **Clocked Operation**: Positive edge-triggered
- **Technology**: 180nm CMOS process
- **Supply Voltage**: 1.8V
- **Master-Slave Architecture**: Prevents race conditions
- **Complementary Clock Inputs**: CLK and NCLK

## 🛠 Technology Specifications

- **Process**: TSMC 180nm CMOS technology
- **Supply Voltage**: 1.8V
- **NMOS Width**: 4-6 units (scalable)
- **PMOS Width**: 8-18 units (scalable) 
- **Channel Length**: 2 units (180nm)
- **Load Capacitance**: 10fF per output

## 📊 Simulation Features

### Timing Analysis
- **Propagation Delay**: Rise and fall time measurements
- **Setup/Hold Time**: Critical timing parameters
- **Clock-to-Q Delay**: Sequential circuit timing
- **Transition Times**: 10%-90% rise/fall measurements

### Power Analysis
- **Static Power**: Leakage current measurement
- **Dynamic Power**: Switching energy calculation
- **Total Energy**: Integrated power consumption
- **Current Integration**: Complete power profiling

### Test Vectors
- **Pulse Generators**: Configurable input stimuli
- **Clock Generation**: Precise timing control
- **Load Modeling**: Realistic output loading

## 🚀 Getting Started

### Prerequisites
- HSPICE simulator or compatible SPICE simulator
- TSMC 180nm technology library (`mosistsmc180.lib`)
- Waveform viewer (e.g., WaveView, CosmosScope)

### Running Simulations

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/spice-circuits
   cd spice-circuits
   ```

2. **Run the 1-bit Comparator/Adder simulation:**
   ```bash
   hspice T-Spice1.sp
   ```

3. **Run the D Flip-Flop simulation:**
   ```bash
   hspice mc.sp
   ```

4. **View results:**
   - Check `.lis` files for measurement results
   - Open `.tr0` files in waveform viewer for signal analysis

### Customization

#### Modifying Device Sizes
```spice
.param N = 4    # NMOS width multiplier
.param P = 8    # PMOS width multiplier  
.param L = 2    # Channel length
```

#### Adjusting Supply Voltage
```spice
.param SUPPLY = 1.8    # Supply voltage in volts
```

#### Changing Simulation Time
```spice
.TRAN 10ps 120ns    # Time step and total simulation time
```

## 📈 Performance Metrics

### Typical Results (180nm, 1.8V, 27°C)

#### 1-bit Comparator/Adder
- **Propagation Delay**: ~200-500ps
- **Rise/Fall Time**: ~100-300ps  
- **Power Consumption**: ~1-10μW (depending on activity)
- **Load Driving**: 10fF per output

#### D Flip-Flop
- **Clock-to-Q Delay**: ~300-800ps
- **Setup Time**: ~100-200ps
- **Hold Time**: ~50-100ps
- **Power per Toggle**: ~1-5pJ

## 📁 File Structure

```
├── T-Spice1.sp          # 1-bit Comparator + Adder netlist
├── mc.sp                # D Flip-Flop netlist  
├── mosistsmc180.lib     # Technology library (not included)
├── README.md            # This file
└── results/             # Simulation output directory
    ├── *.lis           # Measurement results
    ├── *.tr0           # Transient waveform data
    └── *.ic0           # Initial conditions
```

## 🔍 Analysis Capabilities

### Signal Integrity
- **Noise Margins**: High/Low noise immunity
- **Fan-out Analysis**: Drive strength characterization  
- **Process Variation**: Corner analysis support

### Power Optimization
- **Device Sizing**: Width/Length optimization
- **Voltage Scaling**: Supply voltage effects
- **Activity Factor**: Power vs switching frequency

### Timing Optimization  
- **Critical Path**: Delay optimization
- **Clock Skew**: Timing closure analysis
- **Setup/Hold**: Margin analysis

## 📚 Educational Use

These circuits are excellent for:
- **VLSI Design Courses**: Hands-on CMOS circuit design
- **Semiconductor Physics**: Device behavior understanding
- **Digital Logic**: Gate-level implementation study
- **CAD Tools**: SPICE simulation methodology
- **Research**: Foundation for advanced circuit development

## 🤝 Contributing

Contributions are welcome! Please feel free to:
- Add new circuit designs
- Improve existing netlists
- Add analysis scripts
- Enhance documentation
- Report issues or bugs

## 📄 License

This project is licensed under the MIT License 


---
