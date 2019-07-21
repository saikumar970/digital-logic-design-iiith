# Documentation For SRIP Project(DLD-Registers)

Introduction: 

In digital logic and computing, a counter is a device which stores (and sometimes displays) the number of times a particular event or process has occurred, often in relationship to a clock signal. In this experiment, different types of counters will be studied, both for the full binary sequence and for cycle lengths (N) different from powers of 2.

This project is a simulation of the Registers made in Digital Logic Design(DLD). It has only 2 counters currently, the SISO, and the SIPO.
---

### Registers

Flip flops can be used to store a single bit of binary data (1or 0). However, in order to store multiple bits of data, we need multiple flip flops. N flip flops are to be connected in an order to store n bits of data. A Register is a device which is used to store such information. It is a group of flip flops connected in series used to store multiple bits of data.

The information stored within these registers can be transferred with the help of shift registers. Shift Register is a group of flip flops used to store multiple bits of data. The bits stored in such registers can be made to move within the registers and in/out of the registers by applying clock pulses. An n-bit shift register can be formed by connecting n flip-flops where each flip flop stores a single bit of data.
The registers which will shift the bits to left are called “Shift left registers”.
The registers which will shift the bits to right are called “Shift right registers”.
Shift registers are basically of 4 types. These are:

    1.Serial In Serial Out shift register
    2.Serial In parallel Out shift register
    3.Parallel In Serial Out shift register
    4.Parallel In parallel Out shift register
    
### Serial-In Serial-Out Shift Register (SISO) –
1. The shift register, which allows serial input (one bit after the other through a single data line) and produces a serial output is known as Serial-In Serial-Out shift register. Since there is only one output, the data leaves the shift register one bit at a time in a serial pattern, thus the name Serial-In Serial-Out Shift Register.

2. The logic circuit given below shows a serial-in serial-out shift register. The circuit consists of four D flip-flops which are connected in a serial manner. All these flip-flops are synchronous with each other since the same clock signal is applied to each flip flop. 

3. The below circuit is an example of shift right register, taking the serial data input from the left side of the flip flop. The main use of a SISO is to act as a delay element.
![Image](http://cse15-iiith.vlabs.ac.in/images/CD4029codes.png)
4. Apply Manual Clock pulses and tabulate the state sequence for the entire cycle. 

5. Now change the clock input connections to CK1 = Q0’, CK2 = Q1’, CK3 = Q2’, to obtain a Down-counting Binary Ripple counter. 


### Asynchronous (ripple) counter:

An asynchronous (ripple) counter is a single JK-type flip-flop, with its J (data) input fed from its own inverted output. This circuit can store one bit, and hence can count from zero to one before it overflows (starts over from 0). This counter will increment once for every clock cycle and takes two clock cycles to overflow, so every cycle it will alternate between a transition from 0 to 1 and a transition from 1 to 0. Notice that this creates a new clock with a 50% duty cycle at exactly half the frequency of the input clock. If this output is then used as the clock signal for a similarly arranged D flip-flop (remembering to invert the output to the input), you will get another 1 bit counter that counts half as fast. Putting them together yields a two-bit counter:

|Cycle|	Q1|	Q2|	(Q1:Q0)dec|
|:----|:--|:---|:---------
|0	|0|	0|	0|
|1	|0|	1|	1|
|2	|1|	0|	2|
|3	|1|	1|	3|
|4	|0|	0|	0|

### Synchronous counter:

A simple way of implementing the logic for each bit of an ascending counter (which is what is depicted in the image to the right) is for each bit to toggle when all of the less significant bits are at a logic high state. For example, bit 1 toggles when bit 0 is logic high; bit 2 toggles when both bit 1 and bit 0 are logic high; bit 3 toggles when bit 2, bit 1 and bit 0 are all high; and so on. Synchronous counters can also be implemented with hardware finite state machines, which are more complex but allow for smoother, more stable transitions. Hardware-based counters are of this type.


### Decade counter:

A decade counter is one that counts in decimal digits, rather than binary. A decade counter may have each digit binary encoded (that is, it may count in binary-coded decimal, as the 7490 integrated circuit did) or other binary encodings (such as the bi-quinary encoding of the 7490 integrated circuit). Alternatively, it may have a "fully decoded" or one-hot output code in which each output goes high in turn (the 4017 is such a circuit). The latter type of circuit finds applications in multiplexers and demultiplexers, or wherever a scanning type of behavior is useful. Similar counters with different numbers of outputs are also common. The decade counter is also known as a mod-counter when it counts to ten (0, 1, 2, 3, 4, 5, 6, 7, 8, 9). A Mod Counter that counts to 64 stops at 63 because 0 counts as a valid digit. 
A decade counter has the count sequence 0 → 1 → 2 →.....→ 8 → 9 → 0.., which can be achieved by making R’ = (Q3 •Q1)’ for all the flip-flops in a 4-bit binary counter. This forces the counter to go to the state 0000 as soon as the counter makes the transition from the state 1001 representing count 9 to the next state 1010 according to the normal up counting sequence.

### Decade synchronous counter:

The logic for the J-K inputs required for a Decade Synchronous Counter is as follows: 
J0 = K0 = 1; J1 = Q0•Q3’, K1 = Q0; J2 = K2 = Q0•Q1; J3 = Q0•Q1•Q2, K3 = Q0.

### Multipurpose 4-bit Synchronous Counter:

CD4029 is a multipurpose 4-bit counter capable of operating in all the four combinations of Binary/BCD and Up/Down modes, depending on the values of the control inputs B/D’ and U/D’. 
In addition, the 4-bit output Q3Q2Q1Q0 of the counter can be preset to any value by applying the desired bits to the direct inputs D3D2D1D0 and making the Set ENable control SEN = 1. 

![Image](http://cse15-iiith.vlabs.ac.in/images/CD4029codes.png)

## Objective:

1. The objective of this experiment is to understand working of the counters.
2. Try to make basic ripple counter and ring counter.

## Procedure:

1. With The help of Theory Page , try to build the Counter Circuit.
2. First of all build the basic counter .
3. Then make the Ring Counter
4. If You are unable to make it , load the circuit directly and use it
5. Use OSC frequence input to analyze the output

# Technical Details:

## Languages Used:
1. HTML
2. CSS
3. Javascript

## Libraries Used:
1. [Bootstrap](https://getbootstrap.com/) 
2. [jQuery](https://jquery.com/)

## Module Used
1. [Simcir](https://kazuhikoarase.github.io/simcirjs/)
[github link](https://github.com/kazuhikoarase/simcirjs)

## Implementation:

### The simcir module

The simcir module basically searches for a div with class named "simcir". It reads the json data inside that div, and transforms it into a live simulation. 

The json data contains the following things:
1. width(integer)- width of the simulator on the screen in px
2. height(integer)- height of the simulator in px
3. showToolbox(boolean)- decides if the toolbox(the left panel) is to be displayed or not.
4. toolbox(array)- items/tools to be shown in toolbox
5. devices(array)- devices to be displayed on the breadboard
6. connectors(array)- connections between the simulated tools/items.

### Overview

More circuits/tools have been added to the simulation, and premade circuit data is created to load the counters with the click of a button.

### Files

#### end.js

##### Overview:
Added more functionality to the existing module.

##### Technicalities
1. used the function registerDevice() which is defined in the module simcir to add more items/tools that are required by the simulation
2. it's named end.js because it has to be run in the end, after all the js files, because it uses variables from the simcir module's js files

#### main.js

##### Overview:
This file manages all the local variables and remembers the settings to be applied on refreshes of the page.

##### Technicalities:
1. Made the width of the simulator dynamic by using the screen size of the pc which is running the simulation to utilize maximum width possible without scrolling
2. This file uses 'sessionStorage' variables(which uses key value pairs to store data), which remain as long as the tab is open, and do not clear on page refreshes. These variables are used to store the settings of the user.
3. Since the simcir library uses the json data provided at the start, and then replaces it by the simulation, we need to refresh the page and set new json data in the 'simcir' div.
4. Different settings are stored in different key-value pairs in sessionStorage.
	* 'OSCfreq' - The frequency of OSC
	* '8bitCounter_module' - Checkbox of 8-bit-counter module 
	* '8bitRingCounter_module' - Checkbox of 8-bit-ring-counter module 
	* '8bitCounter' - Is true if the button "Load Counter" is clicked
	* '8bitRingCounter' - Is true if the button "Load Ring Counter" is clicked
5. The program first checks if there should be any circuit preloaded. If yes, then it checks all the settings and sets them up accordingly. If no, then it loads a blank simulation with the settings applied.
6. The file also handles all the click events on the webpage to make the buttons interactable

## Test Cases

### Test Case 1

#### Dynamic simulator size

* Simulator loads according to different screen size

* Simulator does not resize itself when the window is resized when the simulator is already loaded, a refresh is required.

Test case partially passed.

### Test Case 2

#### Input of the frequency

Input: words
Output: not accepted

Test case passed.

### Test Case 3

#### Input of the frequency

Input: numbers between 1 and 10
Output: accepted

Test case passed.

### Test Case 4

#### Input of the frequency

Input: numbers not in the range of 1-10
Output: error shown

Test case passed

### Test Case 5

#### Checkboxes

Input: click
Output: toggle

Test case passed.

### Test Case 6

#### Save Settings button

Input: click
Output: Page refresh with new settings applied

Test case passed.

### Test Case 7

#### Clear Settings

Input: click
Output: page refresh with default settings 

Test case passed.

### Test Case 8

#### Load

Input: click
Output: page refresh with couter loaded with no interaction(with settings intact).

Test case passed.

### Test Case 9

#### Load Ring counter

Input: click
Output: page refresh with ring couter loaded with no interaction(with settings intact).

Test case passed.

### Test Case 10

#### Clear Workspace

Input: click
Output: page refresh with blank breadboard and interaction enabled(with settings intact). 

Test case passed.

### Test Case 11

#### Simulation

Input: drag/drop/connections
Output: everything working correctly. 

Test case passed.

