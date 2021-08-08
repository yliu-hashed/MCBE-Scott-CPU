# Summary of Gibberish Compiler for MCBE Scott CPU

[__- NAVIGATIONS -__](/Documents/navigations.md)

![Gibberish Compiler](/Documents/images/image_001.png)

This compiler is made to compile basic programs for the Minecraft Computer. The binary used in this computer is **identical to the Scott CPU except the IO section**. I name the launguage used in this compiler **Gibberish** since it is a hybrid between Pseudo Code and actual Swift. But some concepts is entirely new. This document outlines the key features of this compiler and the Gibberish. 

It is written in Processing, with all its UI written form the groud up. 

To use install this program, see [get started](/Documents/get_started.md).

## The Gibberish Compiler

This program read and write in ```.gibberish``` file. It is not customly encoded, changing the extension between ```.txt``` and ```.gibberish``` is accepted. 

```New``` ```Open``` ```Save``` button are file control buttons. 

### Code Editor
This is where you will type your code in. 

Copy & Paste and text selection is supported. 

```OPTION``` or ```ALT``` key will manually bring up the **Code Suggestion** dropdown. Use ```UP``` and ```DOWN``` arrow to navigate to desired suggestion. ```ENTER/RETURN``` and ```TAB``` key will complete the suggestion. 

### Machine Code Viewer
This is where the **Machine Code** is displayed. The Machine code will always **align** to the currently selected Gibberish Code.

The **two digit number** is in **HEX**, **three digit number** is in **Decimal**. They are the current address of the program. 

## Gibberish Launguage
The following is a **example** of the Gibberish Launguage. It is a multiplication program. 
```java
load(N5, to:R0)
load(N6, to:R1)
//result
zeroOut(R2)

@tag(StartOfLoop)
clearFlag

//see if last bit is One
shiftRight(on:R0)
//if last bit is one, do addition
jumpOnFlag(C:Btrue, A:Bfalse, E:Bfalse, Z:Bfalse, to:@Add)
//if it is zero, it is done;
jumpOnFlag(C:Bfalse, A:Bfalse, E:Bfalse, Z:Btrue, to:@DisplayResult)
jumpTo(@EndAdd)

@tag(Add)
clearFlag
add(R1, to:R2)
@tag(EndAdd)
clearFlag

//prepair for the next add
shiftLeft(on:R1)

jumpTo(@StartOfLoop)

@tag(DisplayResult)
ioWriteData(in:R2)
```

Instruction set and their correspondingly binary is listed in the [instructions.rst](/Documents/compiler/instructions.rst) file.

### Value Types
Value types is treated **explicitly** in this launguage. **The type of the value is indicated in the first character of the value represented as a capital letter or special character.** A placeholder is marked as the value type character + ```#```. 

For example, a (8bit) intiger number with the value of ```5``` is represented ```N5```, a intiger placeholder is represented as ```N#```. 

Value types is listed below. 
Value Type | Placehodler | Example Value | Description
---|---|---|---
8 Bit Intiger | ```N#``` | ```N5``` | This is unsigned intiger, ```0-255``` is allowed.
Boolean | ```B#``` | ```BTrue``` | Only ```BTrue``` and ```BFalse``` is allowed. 
Register | ```R#``` | ```R3``` | Register ```R0,R1,R2,R3``` is the only acceptable value
Code Tag | ```@#``` | ```@StartOfLoop``` | This is explained below

### Code Tags

Because a single line of Gibberish will be coompiled to one or more line of Machine Code. Instruction involving Jump like ```jumpTo(address:N#)``` is **difficult to program** since the **location to jump to is hard to determine**, and if code is inserted, the pointer will no longer point to the desired location. So, the need for the compiler to takeove the jump address is highly in need. 

This is where the idea of **Code Tagging** is born. Gibberish Code like ```@tag(doSomething)``` is not going to translate to any machine code, but instructions like  ```jumpTo(@doSomething)``` will fill in wherever the address of the instruction after ```@tag(doSomething)``` is. 

Example of pseudo code below: 
```
start
while R0 is bigger than R1
  do something
  add R0 by 1 
end
```
can be translated to: 
```java
load(N1, to:R3)

@tag(startOfLoop)
compare(R0, R1)
jumpOnFlag(C:Bfalse, A:Btrue, E:Bfalse, Z:Bfalse, to:@ending)

add(R3, to:R0)

jumpTo(@startOfLoop)

```
If you want to dig into the **launguage definitions**, see launguage definition folder of the Processing Project: [link](/Gibberish_Compiler/data/Language%20Reference). Compiler translations to the **Official Scott CPU launguage** and other information can be found [here](/Documents/compiler/instructions.rst)

[__- NAVIGATIONS -__](/Documents/navigations.md)
