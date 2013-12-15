Getting started with STM32F401C/F429I Discovery boards using EmBlocks
=====================================================================

The purpose of these 5 files is to provide a low cost alternative for Arduino development.

Required Hardware
-----------------
1.	Windows 7/8 platform to host the development, no additional cost
2.	USB cable with mini USB connector, few dollars or no additional cost
3.	STM32F401C Discovery board, $14.50
4.	STM32F429I Discovery board, $24,00

Required Software
-----------------
1.	ST-Link Utility (STSW-LINK004), no cost
2.	STM32F401C firmware (STSW-STM32136), no cost
3.	STM32F429I firmware (STSW-STM32138), no cost
4.	EmBlocks development environment, no cost
5.	Project files to connect EmBlocks to STM32F401C/F429I firmware libraries, no cost
	a.	startup_stm32f4xx.S assembly file, same for both boards
	b.	gcc_arm_f401.ld loader file for F401C
	c.	F401_template.ebp project file for F401C
	d.	gcc_arm_f429.ld loader file for F429I
	e.	F429_template.ebp project file for F429I

Acquisitions
------------
1.	Hardware from www.mouser.com (or similar)
2.	ST-Link and STM32 firmware from www.st.com
3.	EmBlocks IDE from www.emblocks.org
4.	Project files from this repository

Installation
------------
1.	Use the USB cable to connect Windows platform to USB ST-Link connector on Discovery board to provide
	a.	Power for the board
	b.	Program loading from EmBlocks
	c.	GNU Debugger (GDB) control from EmBlocks
	d.	STM32 ST-LINK Utility additional services (all optional)
2.	Install the ST-Link Utility in the default location (Program Files)
3.	Install the EmBlocks in the default location (Program Files)
4.	Install the firmware libraries in a user folder, such as E:\Users\Ollie\Documents\My Projects\STM32F4
5.	Map drive S: to the selected user folder (in Explorer click Home Tab, Select Easy Access, Select Map as drive, select S: drive, browse to the user folder, click finish)
6.	If S: drive is already used for something else, select a different drive letter, open (with text editor) the two EBP files (in XML format) and change S: to the other drive.
7.	Create a folder for F401C project
	a.	Install gcc_arm_f401.ld and F401_template.ebp in this folder
	b.	Create subfolder Src and install startup_stm32f4xx.S there
8.	Create a folder for F429I project
	a.	Install gcc_arm_f429.ld and F429_template.ebp in this folder
	b.	Create subfolder Src and install startup_stm32f4xx.S there

Verification
------------
1.	Connect the USB cable to the target board
2.	Click on the corresponding EBP file (to start EmBlocks)
3.	Click the Rebuild button (or under Build menu select Rebuild all)
	a.	If there are any red errors, check your installations
	b.	In case of F401, there are some blue warnings – those are harmless
4.	Click Session Start/Stop to load the binaries and start GDB (or under Debug Menu select Session Start/Stop, which is same as F8)
	a.	Some additional windows will be opened for debugging support
	b.	Debugging can be stopped at any time (F8)
	c.	In the Workspace projects tree, you can click on Source/S/firmware/Projects/Template/main.c and set a break point (F9) to in the main() code.
	d.	After that you can restart the session (F8) and observe how the execution halts there

Repeatable templates
--------------------
1.	To make the repeatable template usage easier, in EmBlocks file menu select save project as template.  The error message is normal (Some files could not be used).
2.	After that you can start the EmBlocks without using an existing EBP file and in New From template dialog select User Templates and the name of your own template

Your own projects
-----------------
1.	Look for STM and EmBlocks documentation how to tailor this environment for your own projects.
