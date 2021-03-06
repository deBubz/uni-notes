# Introduction to Embedded Systems

## Overview

- basic concepts of embedded system, embedded processor & its interfaces
  - i/o pins
- using RIMS (a gui simulator) to learn the concepts in this subjects
- understand the requirements of carious components in the embedded system

## Embedded System

embedded systems encompasses
- **electrical devices**
  - embedded with microprocessors (every piece of electronics out there)
- **microprocessors**
  - perform a small number of specific(dedicated) functions
  - constrains by processing power, performance size, time, cost (iot concepts)

### Moore's law

- IC will double in transistor capacity in every 18 month

## Integrated circuits & Moore's Law

> doesn't explain IC

> look up wiki??

## Bit, switch & Button

- You prob know what this is, but in embedded context
  - **1** HIGH
  - **0** LOW
- this doesn't represent **voltage** but the signal if its on or off
- usually abstracts to a binary value, it changing value overtime is called a digital **signal** 
- often represented as button/ switch / led

## RIMS

- an emulation of a micro-controller for learning purposes
- work using `c`
- is a simulator supporting `c` programming simulating the execution of **RIM** (Riverside-Irvine Microcontroller)

> Notice that both the input and output also 8-bit

## Timing diagram & pulse

> here comes the interesting stuff

- Signal change(**event**) terminology
  - **0 - 1** rising
  - **1 - 0** falling
  - **pulse** signal portion started by a rising event & ended by a falling event

### Basic timing pulse diagram

![basic diagram](./assets/basic_diagram.png)

diagram describes:
- represent how an embedded system operates over time according to I/O
- 2 input, 1 output timing diagram
- the output `B0` is one between 4s - 5s when both `A0` and `A1` is **HIGH**
- dotted line presents sometimes to help line up certain events

**sample ex 1.4.1**: Timing diagram showing all permutations of 3 inputs
- 6 possible combinations: a b c ab ac bc abc

> remember from previous section:
>
> I/O also represent 8-bit value

Timing diagrams also sometimes display numerical output values and may includes arrows representing which **events** also trigger a value change

![arrow diagram](./assets/arrow_diagram.png)

> is this PWM - pulse width modulationo

### Events

events are change on signal, typically refer to a bit changing from 0->1 or 1->0.

## Testing

> generic testing paradigm for software engineering

- Test border case (edge cases), ensure 100% coverage
- USE PRINT STATEMENTS 
- for code with multiple branches, testing ensuring each statement is executed once is called 100% code coverage.
- **black box testing** testing functionalities while implementation is **not** known to tester, often ui/ux 
- **white box testing** testing functionalities while implementation is known 

## Input value combination (test vectors)

- can be described in **RIMS** rather than manually clicked
- user can puck sequence of events to perform in order:

```
input: set input A0 - A7 to a specific value
  b00000010     // remember binary representation
  0x02
wait: for a specific amount of time
  wait 15ms
  wait 2s
check output: assert output B
  assert b11110000
  assert 0xf0
```

![simple test vector](test_vector.png)