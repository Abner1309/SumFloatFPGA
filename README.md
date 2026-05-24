# Floating-Point Adder on FPGA Board

## 🌐​ Overview:
This project is based on coding an Intel FPGA board with the aim of correctly and safely implementing a simplified floating-point adder.

## 🤔​ What Is An FPGA Board:
An FPGA (Field-Programmable Gate Array) is essentially a "blank" integrated circuit that can be completely reconfigured by the developer after it has been manufactured.

Unlike a common processor in your computer or cell phone, which comes with pre-defined and immutable circuit factories, an FPGA allows you to create your own digital hardware from scratch.

## 🔥​ Motivation:
The presented project is based on the development of four VHDL codes that will be used to implement a floating-point adder on the Intel/Altera/TerAsic DE10-Lite board, using the board's switches (ranging from 0 to 9) as inputs and the LEDs present in the six seven-segment displays as outputs. Regarding the importance of this project, it's worth noting that these adders are fundamental in the arithmetic processing units of modern processors, such as CPUs and GPUs. They play a vital role in the overall system performance, especially in tasks involving intensive calculations. Furthermore, designing a floating-point adder involves dealing with challenges such as rounding, normalization, and exception handling (such as overflow and underflow).

## 🔢​ Number Structure:
The DE10-Lite license plate will receive a number that has the following elements:

* Sign (+ or -)
* Zero (0)
* Period (.)
* Mantissa (Number)
* Letter E
* Exponent (Number)

Example: An example of this format would be the number shown below, which expresses a positive result where the mantissa and the exponent are hexadecimal numbers.
```
+0.53E2
```

## 🔨​ How It Works:
The floating-point adder implementation is basically divided into three distinct stages: data reception, data processing, and finally, data output on the six seven-segment displays. Data reception is handled by the file “fp_adder_test.vhd”, where the signs, exponents, and mantissas of the two numbers are received from a loop. The values ​​are entered into the switches (SW), the KEY0 button activates the clock, and the KEY1 button resets the data input. After receiving this data, arithmetic operations are performed in the “fp_adder.vhd” file, where the signs, exponents, and mantissas of the two numbers are processed to generate a response that conforms to the normalization rules. After this initial processing, the data is sent to the “hex_to_sseg.vhd” file, where further processing determines which LEDs will light up on each seven-segment display. Finally, the file “disp_mux.vhd” correctly turns on the LEDs. Therefore, it can be inferred that:

* Input: “fp_adder_test.vhd”
* Processing: “fp_adder.vhd”
* Output: “disp_mux.vhd” and “hex_to_sseg.vhd”
