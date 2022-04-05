<div align="center">
    <img width="1080" height="489" src="https://i.ibb.co/rZmk7dp/Screen-Shot-2022-04-05-at-10-45-14-AM.png"/>
    <br/>
    <br/>
    <a href="https://hub.docker.com/_/docker"><img src="https://img.shields.io/badge/docker-20.10.12-blue.svg"></a>
    <br/>
    <h1>Debugger</h1>
    <p>Docker container with the necessary tools for debugging devices.
</p>
    <br/>
</div>

## Contents
1. [Download](#download)
2. [Usage](#usage)
3. [Tools](#tools)
4. [Donations](#donations)

<div align="center">
    <h1>Download</h1>
    <p>Download and Install Debugger</p>
</div>

Debugger can be downloaded using the docker command
```
docker run  -h debugger --rm  -it sasaga/debugger:1.0 shell
```

<div align="center">
    <h1>Usage</h1>
    <p>List of Some debugger utilities</p>
</div>

## Usage

You can run Debugger and get a zsh shell as follows:
```
docker run -h debugger --rm  -it sasaga/debugger:1.0 shell
```
<img width="1080" height="489" src="https://i.ibb.co/rZmk7dp/Screen-Shot-2022-04-05-at-10-45-14-AM.png"/>

If you want to run ChipWhisperer notebooks with jupyter you must execute the following command:
````
docker run -p 8888:8888 --rm  -it sasaga/debugger:1.0 jupyter_chipwhisperer
````
<img width="740" height="359" src="https://i.ibb.co/TBJ4pgf/Screen-Shot-2022-04-05-at-11-28-06-AM.png"/>
You can easily access the link provided by jupyter.
<img width="740" height="359" src="https://i.ibb.co/27YQCCG/Screen-Shot-2022-04-05-at-11-30-33-AM.png"/>

You can also share for example a USB Serial device to access from Debugger. 
```
sudo docker run -h debugger --privileged --device="/dev/ttyUSB0" --rm  -it sasaga/debugger:1.0 shell
```
Verify that the communication from Debugger is correctly established.
```
python3 -c 'import serial;s = serial.Serial("/dev/ttyUSB0", 115200);s.write(b"?\n");print(s.read(900).decode())'
```
<img width="740" height="259" src="https://i.ibb.co/4NXHNPB/Screen-Shot-2022-04-05-at-12-07-37-PM.png"/>


<div align="center">
    <h1>Tools</h1>
    <p>List of all the tools installed in Debugger</p>
</div>

## Included Tools
| Tools         | Description                                                                                                 |
|---------------|-------------------------------------------------------------------------------------------------------------|
| gdb           | GNU Project debugger.                                                                                       |
| gdb-multiarch | GNU Debugger (with support for multiple architectures)                                                      |
| binwalk       | Firmware (and arbitrary file) analysis tool.                                                                |
| lldb          | Default debugger in Xcode on macOS and supports debugging objective-C and C++                                                                                           |
| exiftool      | Meta information reader/writer.                                                                             |
| checksec      | single-file shell script, albeit a rather large one. An advantage is that you can read through the script quickly and understand all the system commands running to find information about binaries or executables                                                                   |
| openssh-server| Secure Shell.                                                                     |
| screen        | Full screen window. manager                                                                                                            |
| minicom       | Friendly menu driven serial communication program.                                                                                                            |
| ropper        | Find gadgets to build ROPs chains for different architectures (x86/x86_64, ARM/ARM64, MIPS, PowerPC).                                                                                                            |
| ROPgadgetTool | This tool lets you search your gadgets on your binaries to facilitate your ROP exploitation.                                                                                                            |
| pwndbg        | Is a GDB plug-in that makes debugging with GDB suck. less                                                                                                            |
| peda          | Python Exploit Development Assistance for GDB.                                                                                                            |
| radare2       | Complete framework for reverse.engineering                                                                                                            |
| OpenOCD       | Open On-Chip Debugger.                                                                                                            |
| urJTAG        | UrJTAG aims to create an enhanced, modern tool for communicating over JTAG                                                                                                            |
| stlink-tools  | stlink is an open source toolset to program and debug STM32 devices and boards manufactured by STMicroelectronics.                                                                                                            |
| ChipWhisperer | ChipWhisperer is an open source toolchain dedicated to hardware security research.                                                                                                            |
| ChipWhisperer-Books| The course uses the open‐source ChipWhisperer project                                                                                                        |
| jupyter       | The Jupyter Notebook is a web-based interactive computing platform.                                                                                                            |
| tmux          | tmux is a terminal multiplexer for unix-like systems,                                                                                                             |
| zsh           | Z shell is a powerful command interpreter for Unix-like operating systems.                                                                                                            |

<div align="center">
    <h1>Donations</h1>
    <p>You can contribute by donating to this project. <a href="https://www.paypal.me/exploitwriter">here</a></p>
    <a></a>
</div>