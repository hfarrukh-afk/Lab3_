# Lab3_
Hamza Farrukh
PART 1: 

1) I²C addresses of the accelerometer & magnetometer (show R/W bit too)
•	Accelerometer (7-bit SAD): 0011001b (0x19) → Read: 00110011b (0x33), Write: 00110010b (0x32). STMicroelectronics
•	Magnetometer (7-bit SAD): 0011110b (0x1E) → Read: 00111101b (0x3D), Write: 00111100b (0x3C). STMicroelectronics

2) What is the “sub-address (SUB)”? How is it different from the I²C device address?

The SUB is the 8-bit internal register address you send after the device address; its MSB enables auto-increment (1 = burst across consecutive registers), while the lower 7 bits select the register. The I²C device address (SAD) chooses which chip (accel vs mag) you’re talking to. STMicroelectronics

3) CTRL1 register address & a value that enables acceleration measurements
•	Register: CTRL_REG1_A = 0x20. Layout: ODR3 ODR2 ODR1 ODR0 LPen Zen Yen Xen. STMicroelectronics
•	Value (example, 100 Hz, normal power, X/Y/Z on): 0x57 = 0101 0111b → ODR=100 Hz (0101), LPen=0 (normal), axes enabled. STMicroelectronics

4) 8-bit sub-addresses for accel X/Y/Z data (low/high bytes)
•	X: OUT_X_L_A = 0x28, OUT_X_H_A = 0x29
•	Y: OUT_Y_L_A = 0x2A, OUT_Y_H_A = 0x2B
•	Z: OUT_Z_L_A = 0x2C, OUT_Z_H_A = 0x2D 

