# passworLd
"passworLd" is a project that locks and unlocks the systems such as cell phones, smart home systems or card entry systems by entering password which is controlled by the distance between the user and the system. It was written in SystemVerilog

##FSM Module
 Function: FSM module which gets the signal from Ultrasonic Module will check if the entered
password, which is 10100, is right or wrong.
 Description: For the password, two inputs, “i1” and “i0”, are used. When output “Y” is 1, the
process of entering password is completed successfully. Buttons Module is instantiated in this
module for synchronizing

 ##Buttons Module
 Function: This module synchronizes push buttons and converts to pulses.
 Description: Output “out” goes high for one cycle of input “clk” whenever input “in” makes a
low-to-high transition.

 ##ClockGenerate Module
 Function: This is the clock for 7 segment display.
 Description: It is used for generating a clock for 7 segment display.

##Counter Module
 Function: This module controls the reaction of 7 segment module according to ultrasonic
module and FSM module.
 Description: Controls when the 7 segment shows “----”, “PASS” or “OPEN” according to data from
“Detected” and “isUnlocked”.

##enable_sr Module
 Function: Enables the digits on 7 segment.
 Description: This module takes input refreshClk and has outputs enable_D1, enable_D2,
enable_D3 and enable_D4.

 ##SegmentDisplay Module
 Function: This module is to encode the letters.
 Description: This module gets hexadecimal input and codes them as 7 segment output. We used
active low logic to turn on the segment we want. We encode the letter as the case “hex”. For example,
P is correspond to 0 that 7'b0011000.

 ##Ultrasonic Module
 Function: This block will send a signal to FSM module if there is an object near it.
 Description: Output “trig” sends a signal to out to hit the object. Input “echo” is a signal which
hits the object and turns back to the sensor. By measuring the time between these two signals, the
distance is found as the output “Detected”. Vcc is connected to 5V, GND is connected to 0V on Beti.

 ##ClockDivider Module
 Function: This is the clock divider module for ultrasonic sensor. It helps coordinating the clock of
Basys3 with the working frequence of ultrasonic sensor.
 Description: The ultrasonic sensor works 40 Mhz. This module takes input “basysClk” to slow it
and outputs “clkout”. This clock will be used in Ultrasonic Module.

 ##Top Module
 Function: This module connects other modules and makes the connections between them.
 Description: All modules that clock, enable_sr, FSM, Ultrasonic, Counter, SegmentDisplay are
instantiated in this module. Case statement is used to assign hexadecimal to each digit. Condition is
which digit is on.

Made for CS223 Project in Bilkent University

![Alt text](/C:\Users\Aylin\Desktop\MyNotes\cs223spring\Yeni klasör\BLOCKdiagram.png)
