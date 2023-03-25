## STM32 Toolchain for Windows Notes

### Install make for Windows
   1. Install setup program from this page:
      + https://gnuwin32.sourceforge.net/packages/make.htm
   2. Add path to bin folder to default path:
      + C:\Program Files (x86)\GnuWin32\bin

### Install Git for Windows
   1. Install setup program from this page:
      + https://gitforwindows.org/
   2. Under “Adjusting the name of the initial branch in new repositories, and select “Override the default branch name for new repositories” and leave as “main”
   3. Start GitBash
   4. Set your username:
      + ```git config --global user.name "FIRST_NAME LAST_NAME"```
   5. Set your email address:
      + ```git config --global user.email MY_NAME@example.com```
   6. Exit GitBash:
      + ```exit```

### Install STM32CubeProgrammer
1. Download, extract, and install STM32CubeProgrammer setup program from the following link. Note that you may need to register your name and email address and confirm the email address to download.
   + https://www.st.com/en/development-tools/stm32cubeprog.html

2. After install, add bin folder path for the STMCubeProgrammer to the default path:
   + c:\Program Files\STMicroelectronics\STM32Cube\STMCubeProgrammer

3. Download and install Arm GNU Toolchain. Note that this is not the latest toolchain, but may work best.
   + https://developer.arm.com/downloads/-/gnu-rm

   + Download and install this file. Note that it is reportedly depreciated, but seems to work more smoothly than the latest version. Also, before clicking "Finish" at the end of the installation, be sure to check “Add path to environment variable”. 
     + gcc-arm-none-eabi-10.3-2021.10-win32.exe
   
### Install the STM32 CMSIS headers from GitHub using git inside Cygwin<br>

1. Open Cygwin terminal and navigate to location where you want to do work:<br>
   + ```cd /cygdrive/c/Users/$USERNAME/Documents```

2. Clone the STM32CubeF1 repo to your PC:<br>
   + ```git clone https://github.com/STMicroelectronics/STM32CubeF1.git```

### Install sample Blinky program from GitHub using git<br>
1. Clone the BluePill-Blinky-For-Windows repo to your PC:<br>
   + ```git clone https://github.com/sandynomike/ch1-blinky.git```

### Test installation<br>
1. Navigate to the working directory of the Blinky project:
   + ```cd ch1-blinky```
   + ```make clean```
   + ```make```
