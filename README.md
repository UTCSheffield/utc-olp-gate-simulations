# 8-Bit Full Adder Circuit Simulator

An interactive web-based digital circuit simulator that visualizes an 8-bit ripple carry adder built from full adder gates.

## Overview

This project provides a real-time visual simulation of an 8-bit full adder circuit. You can enter two 8-bit numbers and observe how the circuit computes their sum and carry-out signal. The simulation displays the logic gates and their state changes as the computation progresses.

## Features

- **Interactive Circuit Simulation**: Watch logic gates in real-time as calculations happen
- **Hex/Binary Input**: Enter values in hexadecimal format
- **Carry-In Control**: Include a carry-in bit with the button control
- **Visual Monitoring**: Monitor signal states throughout the circuit
- **Fixed/Live Mode**: Toggle between fixed and animated visualization modes
- **Playback Controls**: Start, stop, and navigate through signal timing diagrams
- **Circuit Export**: Serialize and reload circuit configurations

## How to Use

1. **Enter Values**: Use the input fields labeled "a" and "b" to enter two 8-bit values in hexadecimal
2. **Set Carry-In**: Click the "cin" button to include a carry-in bit
3. **Run Simulation**: Click the ▶️ play button to start the simulation
4. **View Results**: The "sum" field shows the 8-bit result, and "cout" lamp indicates the carry-out
5. **Monitor Timing**: Use the monitor panel at the bottom to view signal timing diagrams
6. **Adjust View**: Use the +/- buttons to zoom in/out of the timing diagrams, and arrow buttons to navigate

## Technical Details

### Architecture

The circuit implements a **ripple carry adder** topology, chaining 8 individual full adder cells together. Each full adder takes:
- Two input bits (a, b)
- A carry-in bit (cin)

And produces:
- A sum bit (sum)
- A carry-out bit (cout)

The carry-out of each stage becomes the carry-in of the next stage, creating the ripple effect.

### Source Files

- **8bitfulleradder.sv**: Verilog HDL source code defining the circuit logic
- **8bitfulladder.json**: JavaScript Object Notation representation of the circuit (auto-generated from the Verilog)
- **index.html**: Web interface for the simulator
- **script.js**: JavaScript code handling user interactions
- **style.css**: Styling for the web interface

## Original Project

This circuit simulator is built on top of two key projects:

1. **Verilog 8-bit Ripple Carry Adder**
   - Source: [VLSI Master Blog - Verilog Code for 8-bit Ripple Carry Adder](https://vlsimaster.wordpress.com/2013/01/26/verilog-code-for-8-bit-ripple-carry-adder-and-testbench/)
   - The original Verilog HDL implementation of the ripple carry adder

2. **Digital.js Circuit Simulator**
   - Source: [DigitalJS - Digital Circuit Simulator](https://digitaljs.tilk.eu/)
   - A JavaScript library for simulating digital circuits
   - Provides the interactive visualization engine that converts Verilog to interactive simulations
   - Used to generate the JSON representation from the .sv file

## How It Works

1. The Verilog source file (`8bitfulleradder.sv`) defines the circuit logic
2. DigitalJS converts the Verilog into an interactive JSON representation (`8bitfulladder.json`)
3. The web interface loads this JSON and renders it using the DigitalJS visualization library
4. User inputs are fed into the circuit simulation
5. Real-time monitoring displays the propagation of signals through the gates

## Development

To modify the circuit:
1. Edit `8bitfulleradder.sv` to change the Verilog logic
2. Use DigitalJS's online tool to convert the updated .sv file to JSON
3. Update `8bitfulladder.json` with the new circuit definition
4. Refresh the page to see the changes

## Browser Requirements

- A modern web browser with JavaScript enabled
- Recommended: Chrome, Firefox, Safari, or Edge (latest versions)

## License

See [LICENSE](LICENSE) for details on the licensing of this project.

---

**Note**: This is an educational project demonstrating digital circuit simulation. The circuit simulation may not be suitable for production hardware design - always verify with proper HDL simulation tools before implementing circuits in hardware.
