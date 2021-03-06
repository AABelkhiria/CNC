# CNC

![alt text][logo]

[logo]: https://github.com/AABelkhiria/CNC/blob/master/Logo/Capture.bmp


CNC-Machine on STM32 Nucleo F3.

In this project, the program in the microprocessor is written in C++. The GUI in the computer is written in Python.

## PRINCIPLE OF OPERATION

The operator connects the CNC machine with the computer, so the user could open the executable previously installed on the PC. The communication interface between the machine and the user is the computer via an executable application.

The program offers a workspace equivalent to 1 pixel (according to the step motors) per millimeter of the actual workspace.

The program offers you to draw simple geometric shapes (Lines / Circles / Set of points ...) that will be translated later by the movement of the element carried by the head of the CNC machine.

After the schema is complete, the program proceeds to translate the drawing into a path. This path will be transmitted by a USB cable.

The program included in the microcontroller decrypts the path of the executable. The head then starts moving.

## Microprocessor Program

The program in the STM32 is written in C++ language. In order to get the binary program, we need to compile the code in [mbed compiler](https://os.mbed.com/compiler).
After hitting the **compile** button, a .bin file is generated and downloaded. you need to place this file in the flash memory of the microprocessor.

The main.cpp code is under MPross folder. This can be imported to the Mbed compiler or can written manually.

## Graphical Unit Interface

A GUI program was written in python using the TKinter library. The program contains a workspace for drawing geometric shapes and a button allowing you to comunicate to your controller via USB.

You need for this application python 3.6.

* Another program written with python allows you to convert a DXF file done by 3D modeling software like Solidworks to a text file containing path of the end-effector.
* A third program is made to build a connection between the PC and the controller via Serial communication.

The program assuring the connection between the PC and the microprocessor.
In fact, the program treats the contents of the file line by line.

## Mecanical Conception

This conception was made by Solidworks, containing all parts needed in the realization of the CNC-Machine.
An Assembly file also indicates how parts are pieced together.

## Electronic Conception

Using Proteus 8, an electronic design was made in the form of a mother board.
The board contains a shield space for the STM32 F3 Nucleo.
Also, the power section is made by 3 L298, 1 for each step motor.

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/eADHYIyrXmQ/0.jpg)](https://www.youtube.com/embed/eADHYIyrXmQ)
