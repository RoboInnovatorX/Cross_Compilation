## Cross-compiling and Debugging with Qt creater

### Step 1: 
* **Download and extract** the [*Jetson Linux Driver Package Toolchain*](https://docs.nvidia.com/jetson/l4t/Tegra%20Linux%20Driver%20Package%20Development%20Guide/xavier_toolchain.html) file .
   
    
### Step 2:
* **Setup the Qt creator**  for debugging.

* For setting up Device Go to **Tools** => **Options** => **Devices** and **Add** a new device there
  ![](images/1.png)
* Select **Generic Linux Device** and click **Start Wizard**

  ![](images/b.png)
* Set up **Identity name**, **Devie's host name**, **username** and click the **Next** button
  ![](images/c.png)
* Add **Private ssh key** and press **Next** button
  ![](images/d.png) 
* Press the **Finish** Button
  ![](images/e.png) 
* You can test the connection just click **Test**

  ![](images/f.png) 

* For setting up Kit Go to **Tools** => **Options** => **Kits** => **Compilers** and **Add** manually two compilers. One is for C++ that is **aarch64-liux-gnu-g++** and another one for C that is **aarch64-liux-gnu-gcc**
  ![](images/i.png)
* Go to **Debuggers** and add a manual debugger that is **linaro-7.3.1-gdb**
  ![](images/j.png)
* Now Go to **Kits** and **Add** a new Kit
  * Add a device name 
  * Select the Device type **Generic Linux Device**
  * Select the **Device** priviously added.
  * Select the C,C++ **Compiler** and the **Debugger** previously added
  * Press **Apply** and **OK** button
  ![](images/h.png)

* Now in the left side go to **Projects** and Select the **Kit** previously added and go to **Build** and add the path of the cmake_toolchain file
  * **CMAKE_TOOLCHAIN_FILE = /home/shofikul/git/gmapping/Toolchain-linaro-arm-linux.cmake**
  ![](images/k.png)
* Go to **Run** 
  * Setup **Alternate executable on device** path to **/home/ubuntu/bin/mapper**
  * Setup **Command line arguments** to **-filename /home/ubuntu/data/fr079-complete.gfs.log** 
  ![](images/k.png)
