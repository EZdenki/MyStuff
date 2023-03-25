# MyStuff (Private)

1. Install Git for Windows
  https://gitforwindows.org/

Under “Adjusting the name of the initial branch in new repositories, and select “Override the default branch name for new repositories” and leave as “main”
    Start GitBash
    Set your username: git config --global user.name "FIRST_NAME LAST_NAME"
    Set your email address: git config --global user.email MY_NAME@example.com
  Exit GitBash: exit

2. Install STM32CubeProgrammer<br>
https://www.st.com/en/development-tools/stm32cubeprog.html
Click Get Software -> Get latest for Win64 ->ACCEPT

Extract en.stm32cubeprg-win64-v2xxx.zip and run
After install, add bin folder for the STMCubeProgrammer to the path:
  c:\Program Files\STMicroelectronics\STM32Cube\STMCubeProgrammer

3. Install Arm GNU Toolchain<br>
https://developer.arm.com/downloads/-/gnu-rm

Download and install this file. It is reportedly depreciated, but seems to work more smoothly than the latest version.
gcc-arm-none-eabi-10.3-2021.10-win32.exe

Important: At end of installation, check “Add path to environment variable” and click “Finish”


4. Install the STM32 CMSIS headers from GitHub using git inside Cygwin<br>

Open Cygwin terminal and navigate to location where you want to do work:<br>
    cd /cygdrive/c/Users/$USERNAME/Documents

Clone the STM32CubeF1 repo to your PC:<br>
  git clone https://github.com/STMicroelectronics/STM32CubeF1.git

5. Install sample Blinky program from GitHub using git<br>
Clone the BluePill-Blinky-For-Windows repo to your PC:<br>
  git clone https://github.com/sandynomike/ch1-blinky.git

6. Test installation<br>
 Open Cygwin terminal. Navigate to the working directory of the Blinky project:

  cd /cygdrive/c/Users/WDAGUtilityAccount/Documents/ch1-blinky
  make clean
  make
