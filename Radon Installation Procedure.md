# Radon Tool

**Prerequisite**

 - Some or good grip on the Linux administration commands.
 
 - Should have an idea about installation of Operating Systems.
 
 - Should have good idea about the VMware players(if installation is to be done on VM).
 - Please ensure the system is configured with Python or any latest version of Python (Python3).
 
##
**Basic Installation Steps**

**Installation of Operating System/Virtual Machine:**

 - The above products of Apache would run good on Ubuntu 16.04 LTS and Ubuntu 18.04 LTS version of the operating systems.

 - You can get the image files of the OS by clicking on the link: [Ubuntu OS ](https://ubuntu.com/download/desktop) (Ubuntu 18.04.3 LTS/Ubuntu 16.04.3 LTS).

 - If the system is running on Windows Operating System, then it would be better to make a dual-boot for other operating system to be installed or we can use the VMware Player or Workstation 15.xx version for the installation of the Ubuntu OS.

	 - Link for VMware: [VMware Download Link](https://www.vmware.com/in/products/workstation-player/workstation-player-evaluation.html)

- Please install the VMWare Workstation Player.

- After the installation and running VMWare Workstation Player, you could get a window where there is a tab called Create a New Virtual Machine.

- After the click, please ensure the details are filled and the path to the installation of image file of the Linux OS is to be provided.

- Then we could customize the processor cores, RAM, others as per the system requirements.

- After clicking finish, the virtual machine would start up and the installation of OS would be in process.

##

**Installation of Java Version**

- After the running of Linux OS, use the key Ctrl+Alt+T (To open Terminal).

- After the opening of the Terminal, please follow the below steps:

	- Installation of Java with related commands:

		- sudo su (Run the programs in administrator mode)

		- sudo apt-get update (To check for the updates of OS).

		- sudo apt-get install openjdk-8-jdk

		- java -version

		- export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64

		- export PATH=$ PATH: $ JAVA_HOME/bin (No spaces between the symbol and word).
		
**Expected Output**

![Java Version Output](https://github.com/abhaymehtre/Software-Evaluation-Tool/blob/master/images/1.jpg)

##

**Installation Procedure for Radon**
Radon is a Python tool that computes various metrics from the source code. Radon can compute:

-   **McCabe’s complexity**, i.e. cyclomatic complexity
-   **raw**  metrics (these include SLOC, comment lines, blank lines, &c.)
-   **Halstead**  metrics (all of them)
-   **Maintainability Index**  (the one used in Visual Studio)

Radon will run from  **Python 2.7**  to  **Python 3.8**  (except Python versions from 3.0 to 3.3) with a single code base and without the need of tools like 2to3 or six. It can also run on  **PyPy**  without any problems (currently PyPy 3.5 v7.3.1 is used in tests).

Radon depends on as few packages as possible. Currently only  mando  is strictly required (for the CLI interface).  colorama  is also listed as a dependency but if Radon cannot import it, the output simply will not be colored.

**Note**:  **Python 2.6**  was supported until version 1.5.0. Starting from version 2.0, it is not supported anymore.


**Installation**

With Pip and Pip3 :

	$ pip install radon or pip3 install radon

Or download the source and run the setup file:

	$ python setup.py install

Expected Output:

	$ radon cc sympy/solvers/solvers.py -a -nc
	sympy/solvers/solvers.py
    F 346:0 solve - F
    F 1093:0 _solve - F
    F 1434:0 _solve_system - F
    F 2647:0 unrad - F
    F 110:0 checksol - F
    F 2238:0 _tsolve - F
    F 2482:0 _invert - F
    F 1862:0 solve_linear_system - E
    F 1781:0 minsolve_linear_system - D
    F 1636:0 solve_linear - D
    F 2382:0 nsolve - C

	11 blocks (classes, functions, methods) analyzed.
	Average complexity: F (61.0)

**Explanation:**

-   cc  is the radon command to compute Cyclomatic Complexity
-   -a  tells radon to calculate the average complexity at the end. Note that the average is computed among the  _shown_  blocks. If you want the total average, among all the blocks, regardless of what is being shown, you should use  --total-average.
-   -nc  tells radon to print only results with a complexity rank of C or worse. Other examples:  -na  (from A to F), or  -nd  (from D to F).
-   The letter  _in front of_  the line numbers represents the type of the block (**F**  means function,  **M**  method and  **C**  class).

Reference for Installation : https://pypi.org/project/radon/

