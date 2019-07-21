# Documentation For SRIP Project(DLD-Registers)
 
### Introduction
We have examined a general model for sequential circuits. In this model the effect of all previous inputs on the outputs is represented by a state of the circuit. Thus, the output of the circuit at any time depends upon its current state and the input. These also determine the next state of the circuit. The relationship that exists among the inputs, outputs, present states and next states can be specified by either the state table or the state diagram.

### State Table

The state table representation of a sequential circuit consists of three sections labeled present state, next state and output. The present state designates the state of flip-flops before the occurrence of a clock pulse. The next state shows the states of flip-flops after the clock pulse, and the output section lists the value of the output variables during the present state.

### State Diagram

In addition to graphical symbols, tables or equations, flip-flops can also be represented graphically by a state diagram. In this diagram, a state is represented by a circle, and the transition between states is indicated by directed lines (or arcs) connecting the circles.

This project is a simulation of the State Diagram made in Digital Logic Design(DLD).
---

### State Machines

Up to now, every circuit that was presented was a combinatorial circuit. That means that its output is dependent only by its current inputs. Previous inputs for that type of circuits have no effect on the output.
However, there are many applications where there is a need for our circuits to have “memory”; to remember previous inputs and calculate their outputs according to them. A circuit whose output depends not only on the present input but also on the history of the input is called a sequential circuit.
In this section we will learn how to design and build such sequential circuits. In order to see how this procedure works, we will use an example, on which we will study our topic.
So let’s suppose we have a digital quiz game that works on a clock and reads an input from a manual button. However, we want the switch to transmit only one HIGH pulse to the circuit. If we hook the button directly on the game circuit it will transmit HIGH for as few clock cycles as our finger can achieve. On a common clock frequency our finger can never be fast enough.

### Step1:
The first step of the design procedure is to define with simple but clear words what we want our circuit to do:
“Our mission is to design a secondary circuit that will transmit a HIGH pulse with duration of only one cycle when the manual button is pressed, and won’t transmit another pulse until the button is depressed and pressed again.”

### Step2:

The next step is to design a State Diagram. This is a diagram that is made from circles and arrows and describes visually the operation of our circuit. In mathematic terms, this diagram that describes the operation of our sequential circuit is a Finite State Machine.
Make a note that this is a Moore Finite State Machine. Its output is a function of only its current state, not its input. That is in contrast with the Mealy Finite State Machine, where input affects the output. In this tutorial, only the Moore Finite State Machine will be examined. 
The State Diagram of our circuit is the following: (Figure below)
   ![Image](https://github.com/saikumar970/digital-logic-design-iiith/blob/master/SRIP_Project_1/Codes/images/basic1.webp)
### Serial-In Serial-Out Shift Register (SISO) –
1. The shift register, which allows serial input (one bit after the other through a single data line) and produces a serial output is known as Serial-In Serial-Out shift register. Since there is only one output, the data leaves the shift register one bit at a time in a serial pattern, thus the name Serial-In Serial-Out Shift Register.

2. The logic circuit given below shows a serial-in serial-out shift register. The circuit consists of four D flip-flops which are connected in a serial manner. All these flip-flops are synchronous with each other since the same clock signal is applied to each flip flop. 

3. The below circuit is an example of shift right register, taking the serial data input from the left side of the flip flop. The main use of a SISO is to act as a delay element.
![Image](https://github.com/saikumar970/digital-logic-design-iiith/blob/master/SRIP/Codes/images/SISO_DOC.png)

### Serial-In Parallel-Out shift Register (SIPO) –:

The shift register, which allows serial input (one bit after the other through a single data line) and produces a parallel output is known as Serial-In Parallel-Out shift register.

The logic circuit given below shows a serial-in-parallel-out shift register. The circuit consists of four D flip-flops which are connected. The clear (CLR) signal is connected in addition to the clock signal to all the 4 flip flops in order to RESET them. The output of the first flip flop is connected to the input of the next flip flop and so on. All these flip-flops are synchronous with each other since the same clock signal is applied to each flip flop.
The below circuit is an example of shift right register, taking the serial data input from the left side of the flip flop and producing a parallel output. They are used in communication lines where demultiplexing of a data line into several parallel lines is required because the main use of the SIPO register is to convert serial data into parallel data.
![Image](https://github.com/saikumar970/digital-logic-design-iiith/blob/master/SRIP/Codes/images/SIPO_DOC.png)

### Parallel-In Serial-Out Shift Register (PISO):

The shift register, which allows parallel input (data is given separately to each flip flop and in a simultaneous manner) and produces a serial output is known as Parallel-In Serial-Out shift register.

The logic circuit given below shows a parallel-in-serial-out shift register. The circuit consists of four D flip-flops which are connected. The clock input is directly connected to all the flip flops but the input data is connected individually to each flip flop through a multiplexer at the input of every flip flop. The output of the previous flip flop and parallel data input are connected to the input of the MUX and the output of MUX is connected to the next flip flop. All these flip-flops are synchronous with each other since the same clock signal is applied to each flip flop.
A Parallel in Serial out (PISO) shift register us used to convert parallel data to serial data. 

![Image](https://github.com/saikumar970/digital-logic-design-iiith/blob/master/SRIP/Codes/images/PISO_DOC.jpg)
### Parallel-In Parallel-Out Shift Register (PIPO):

The shift register, which allows parallel input (data is given separately to each flip flop and in a simultaneous manner) and also produces a parallel output is known as Parallel-In parallel-Out shift register.

The logic circuit given below shows a parallel-in-parallel-out shift register. The circuit consists of four D flip-flops which are connected. The clear (CLR) signal and clock signals are connected to all the 4 flip flops. In this type of register, there are no interconnections between the individual flip-flops since no serial shifting of the data is required. Data is given as input separately for each flip flop and in the same way, output also collected individually from each flip flop.
![Image](https://github.com/saikumar970/digital-logic-design-iiith/blob/master/SRIP/Codes/images/PIPO_DOC.png)


## Objective:

1. The objective of this experiment is to understand working of the Register.
2. Try to make basic SIPO SISO PISO and PIPO.

## Procedure:

1. With The help of Theory Page , try to build the Register Circuit.
2. First of all build the basic Register .
3. Then make the Ring SISO
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

#### Circuitworking.js

##### Overview:
This file manages all the local variables and remembers the settings to be applied on refreshes of the page.

##### Technicalities:
1. Made the width of the simulator dynamic by using the screen size of the pc which is running the simulation to utilize maximum width possible without scrolling
2. This file uses 'sessionStorage' variables(which uses key value pairs to store data), which remain as long as the tab is open, and do not clear on page refreshes. These variables are used to store the settings of the user.
3. Since the simcir library uses the json data provided at the start, and then replaces it by the simulation, we need to refresh the page and set new json data in the 'simcir' div.
4. Different settings are stored in different key-value pairs in sessionStorage.
	* 'OSCfreq' - The frequency of OSC
	* 'SISO' - Is true if the button "Load SISO Register" is clicked
	* 'SIPO' - Is true if the button "Load SIPO Register" is clicked
5. The program first checks if there should be any circuit preloaded. If yes, then it checks all the settings and sets them up accordingly. If no, then it loads a blank simulation with the settings applied.
6. The file also handles all the click events on the webpage to make the buttons interactable

## Test Cases

### Test Case 1

#### Dynamic simulator size

* Simulator loads according to different screen size

* Simulator does not resize itself when the window is resized when the simulator is already loaded, a refresh is required.

Test case partially passed.

### Test Case 2

#### Checkboxes

Input: click
Output: toggle

Test case passed.

### Test Case 3

#### Load

Input: click
Output: page refresh with couter loaded with no interaction(with settings intact).

Test case passed.

### Test Case 4

#### Load SISO Register

Input: click
Output: page refresh with ring couter loaded with no interaction(with settings intact).

Test case passed.
### Test Case 5

#### Load SIPO Register

Input: click
Output: page refresh with ring couter loaded with no interaction(with settings intact).

Test case passed.
### Test Case 6

#### Clear Workspace

Input: click
Output: page refresh with blank breadboard and interaction enabled(with settings intact). 

Test case passed.

### Test Case 7

#### Simulation

Input: drag/drop/connections
Output: everything working correctly. 

Test case passed.

