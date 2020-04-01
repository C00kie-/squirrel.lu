## On Chip debugging with OpenOCD and GDB

Running OpenOCD on a machine to run On-chip debugging with GDB is kinda magic. This first tutorial covers the installation and configuration for OpenOCD on a debian based machine, for ARM chip debugging.

The content of this post has been done actually quite shortly after the Bsides Manchester 2018, pre-party presentation, while I was guessing how to make things clear aside of the slides and for people who didn’t see the presentation.

It’s my first write-up, feel free to comment and let me know how to improve it!

### Hardware hacking?

Dumping the firmware from the device allows you to test, debug and run anything on emulation right after, instead of working directly on the device, what could be very convenient if you have many operations to perform and a limited number of devices you can break.

As you might have seen in the slides [here](https://www.slideshare.net/PaulineKo1/onchip-debugging-with-openocd-hardwarehacking), I use this configuration :

Your computer will be a debug host machine. Mine runs Ubuntu. You’ll need an interface that will make the connection between your chip and the computer. Here I use a ST-LINK USB dongle. And finally, you’ll need the chip itself.

*You can run the same installation on other OS:

Source code : https://sourceforge.net/p/openocd/code/ci/master/tree/

### GDB

Before starting debugging, I recommend you to become familiar with the general concepts behind [GDB](https://www.gnu.org/software/gdb/). It the idea of seeing what’s happening while you run the different commands and how the executable that you run behaves.

Basically, GDB will allow you to see what your executable does instruction by instruction, at different levels. You’ll, for example, have access to the assembly code that is run on the machine. The idea with such a low-level approach is to see exactly what is happening on the machine from the memory point of view. I used many times GDB while I was at IT school for debugging my huge SEGV signals. :-/ You’ll find a lot of GDB tutorials as well as a cheat sheet on the subject online!

Associated with GDB, I recommend using GEF (GDB Enhanced Features). GEF is a plugin to GDB that provides augmented features: like colors and the display of separated pieces of information for registers, stack, flags and also miscellaneous commands that you’ll learn (as I will too) to appreciate. GEF is a Python API used for Dynamic Analysis, make sure that you have the last and/or a good version of Python installed on your machine before running the installation scripts.

GEF [github](https://github.com/hugsy/gef) 

Note : If you have an ARM chip to debug, you will need to configure GDB for this architecture.

GDB runs also a server for debugging which is very useful, in the case of you can not work directly on the device you are debugging or, for catching all the output you want to write into a debug file. You can also Telnet your device using configurations (port and address) given to you by the OpenOcd config files. In this tutorial, I’ll use telnet.

### Installation

First, in order to install OpenOCD properly and don’t mess with the configuration, I’ll recommend trying the easy way installation.

You can run an apt-get install Openocd directly from your Debian GNU Linux distribution.

### Running

Once you run the program, you’ll only have to choose in the folders of the .cfg files for your interface name and your chip name.

You run the command :

      $sudo openocd -f [interface] -f[target]

This will initialize OpenOCD with the configuration files you give as parameters with the -f option. OpenOCD will find itself which configuration to apply and will run the debug server as referenced with default ports :

3333 for GDB

4444 for Telnet

In another window of your terminal, you initialize a telnet/gdb connection with your chip using your local loop :

Inside GDB it will be the command :

    $target remote localhost:3333

If you didn’t get lucky and configuration didn’t work, it’s ok. Just follow the next sections.
meeh ain’t working

First check if you have Python and GDB updated and working correctly on your machine, then reinstall GEF.

Installing Open OCD is quite straightforward if you respect the instructions on the SourceForge page of the project. What you’ll do is to build the application on your own machine. Instructions for building comes with dependencies installation that you must have done on your machine before running the installation of OpenOCD. Each time you change something related to these dependencies, you have to rebuild the program, it includes reloading the installation framework updated with configurations you changed (path file or whatever), that what bootstrap is doing. So relaunch it before rebuilding your program doing $make re
OpenOCD is installed

Now go to the main folder where is your openocd executable.

As we previously mentioned there are folders what would be useful to take a look :

chip

interface

target

board

For example, you’ll need to go to /interface to match your interface name.

I recommend you run the command $openocd -h, it displays the basic commands you can run with their parameters :

~~~~shell
    $ openocd -h

Open On-Chip Debugger 0.10.0+dev-00510-g766d611 (2018-08-10-17:46)

Licensed under GNU GPL v2

For bug reports, read
http://openocd.org/doc/doxygen/bugs.html

Open On-Chip Debugger

Licensed under GNU GPL v2

–help | -h display this help

–version | -v display OpenOCD version

–file | -f use configuration file <name>

–search | -s dir to search for config files and scripts

–debug | -d set debug level to 3

| -d<n> set debug level to <level>

–log_output | -l redirect log output to file <name>

–command | -c run <command>

In case you need to debug your openocd command, the first line give you precious information about the version you installed on your machine.

Once you selected the names of your interface and board (a quick look at the .cfg files will inform you also), you can ask Openocd to directly include these file with the -s option. In the other case, you’ll have to write the full path of the .cfg files you want to include.

Now write the openocd command to run the debugging server with the configuration files you associated :

    $ sudo openocd -f [interface] -f[target]

It will ask for your root password.

On my machine, it displays this:

Open On-Chip Debugger 0.10.0+dev-00510-g766d611 (2018-08-10-17:46)

Licensed under GNU GPL v2

For bug reports, read
[http://openocd.org/doc/doxygen/bugs.html](http://openocd.org/doc/doxygen/bugs.html)

WARNING: interface/stlink-v2.cfg is deprecated, please switch to interface/stlink.cfg

Info : auto-selecting first available session transport « hla_swd ». To override use ‘transport select <transport>’.

Info : The selected transport took over low-level target control. The results might differ compared to plain JTAG/SWD

adapter speed: 1000 kHz

adapter_nsrst_delay: 100

none separate

Info : Listening on port 6666 for tcl connections

Info : Listening on port 4444 for telnet connections

Info : Unable to match requested speed 1000 kHz, using 950 kHz

Info : Unable to match requested speed 1000 kHz, using 950 kHz

Info : clock speed 950 kHz

Info : STLINK v2 JTAG v17 API v2 SWIM v4 VID 0x0483 PID 0x3748

Info : using stlink api v2

Info : Target voltage: 3.241744

Info : stm32f1x.cpu: hardware has 6 breakpoints, 4 watchpoints

Info : Listening on port 3333 for gdb connections

~~~~

Brilliant ! So what does it tell us? That everything is working, even if I have a warning, telling me my version of ST-LINK v2 file is depreciated. (I figured out that it linked directly to the st-link.cfg file instead).

### Start Debugging!

\o/

### Trouble shooting

ARM architecture-specific GDB configuration

Search into your package manager if you have not gdb-arm-none-eabi installed,

    $ sudo apt-cache search gdb-arm-none-eabi

gdb-arm-none-eabi – GNU debugger for ARM Cortex-A/R/M processors

    $ sudo apt-get install gdb-arm-none-eabi

for mac OSX
[https://github.com/eblot/homebrew-armeabi](https://github.com/eblot/homebrew-armeabi)

Then instead of running gdb this way

$gdb

do

$gdb-arm-none-eabi

$target remote:3333

$info register
