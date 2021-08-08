# MCBE-Scott-CPU
Compiler: 
[![Github release](https://img.shields.io/github/downloads/YuandaLiu-Hashed/Gibberish-Compiler/total.svg)](https://github.com/YuandaLiu-Hashed/MCBE-Scott-CPU/releases)
![Github release](https://img.shields.io/github/repo-size/YuandaLiu-Hashed/Gibberish-Compiler.svg?color=blue)
World: 
[![Github release](https://img.shields.io/github/downloads/YuandaLiu-Hashed/MCBE-Scott-CPU/total.svg)](https://github.com/YuandaLiu-Hashed/MCBE-Scott-CPU-World/releases)
![Github release](https://img.shields.io/github/repo-size/YuandaLiu-Hashed/MCBE-Scott-CPU.svg?color=blue)

[__- NAVIGATIONS -__](/Documents/navigations.md)

This is a Minecraft(bedrock) adoptation of the famous Scott CPU in the book **_But How Do It Know? The Basic Principles of Computers for Everyone_** by J. Clark Scott and Compiler called the **_Gibberish Compiler_** I made of this CPU. 

__[GET STARTED](/Documents/get_started.md)__

Note: This project is in it's very early stage. Instructions and Documentations is expected to be missing or unclear.__

## Download: [WorldFile](https://github.com/YuandaLiu-Hashed/MCBE-Scott-CPU/releases) [GibberishCompiler](https://github.com/YuandaLiu-Hashed/Gibberish-Compiler/releases)

Note: Although you can download it right away, [Get Started](/Documents/get_started.md) is very helpful.

## Project Structures
This project is split into two parts: 
* Gibberish Compiler
   * __File exsist in a subrepo called _[Gibberish-Compiler](https://github.com/YuandaLiu-Hashed/Gibberish-Compiler)_. It will be released in that repo.__
   * __Documentations will exsist in this repo.__
* Minecraft World File of the actual Computer 
   * Exsist in this repo

Compatibility of two part of the project between versions can be found here: [versions.rst](/Documents/versions.rst)

__All documentations' links on this project can be found in [- NAVIGATIONS -](/Documents/navigations.md).__

## Scott Computer Minecraft World

This is a Minecraft adoptation of the famous Scott CPU in the book But how do it knows **_But How Do It Know? The Basic Principles of Computers for Everyone_**. 

![Minecraft Computer](/Documents/images/image_002.jpg)

```LEFT: IO Decoder | RIGHT: RAM | CENTER BLOCK: ALU | FAR BACK TOWER: Stack | MIDDLE: Instruction Decoder```

![Minecraft Computer](/Documents/images/image_003.jpg)

```FRONT LEFT: Stack | RIGHT BOTTOM: Multiplication Module | BACK LEFT: Instruction Decoder | CENTER BLOCK: ALU | RIGHT FRONT: IO Decoder```

![Minecraft Computer](/Documents/images/image_004.jpg)

```FAR BACK: RAM | LEFT: Stack | RIGHT: ALU | MIDDLE: Instruction Decoders```

![Minecraft Computer](/Documents/images/image_005.jpg)

```RIGHT HALF: RAM Editor | LEFT: Steper Control```

The computer is binary compatible with the Scott CPU, with a modified IO port ([more informations](/Documents/compiler/instructions.rst)). 

It could be used as a teaching tool for teachers, or a gadget for someone like me to learn about computer architecture in a intuitive way. 

It have a 256 bit RAM. The program and data is all stored in the RAM. IO devices could be connected to the IO port. 

Instructions is __[here](/Documents/get_started.md#Scott-CPU-Minecraft-World)__ if you want to get started. 

## Gibberish Compiler
Note: only the files of the Minecraft World exsists in this repo. The gobberish compiler exsist in a repo called _[Gibberish-Compiler](https://github.com/YuandaLiu-Hashed/Gibberish-Compiler)_ (only documentation of that project exsist in this repo).

This compiler is made to compile basic programs for the Minecraft Computer. 

![Example Image of a Multiplication Code](/Documents/images/image_001.jpg)

This program made by using [Processing](https://processing.org) which is a program made for learning Java (highly reconmemded if you want to start coding). 
This app can be a effective application to learn basic processing using my custom programming launguage I made called __Gibberish__. 
This program can also be a example of a effective application made by __Processing__, which could used as a teaching and learning tool. 

Note: Java may need to be installed for this program to run. 

Instructions is __[here](/Documents/get_started.md#Gibberish-Compiler)__ if you want to get started.

[__- NAVIGATIONS -__](/Documents/navigations.md)
