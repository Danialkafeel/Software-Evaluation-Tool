# Installation of Pycfg tool.

**Prerequisite**

 - Some or good grip on the Linux administration commands.
 
 - Should have an idea about installation of Operating Systems.
 
 - Should have good idea about the VMware players(if installation is to be done on VM).
 - Please ensure the system is configured with Python or any latest version of Python.
 
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

![Java Version Output](https://github.com/abhaymehtre/Crawling-Engines/blob/master/images/ELK_Nutch/1.JPG)

##

**Installation Procedure for Pycfg**

- Usually, we draw manual _Control Flow Graph_ using pen and paper by analyzing the control flow of the program. CFG helps us finding independent paths ([Cyclomatic Complexity](https://www.geeksforgeeks.org/cyclomatic-complexity/)), which leads to the number of test cases required to test the program. We can automate the CFG task using a Python library called [pycfg](https://pypi.org/project/pycfg/). This library takes a Python script as input and gives graph as output.
We can use [pycfg](https://pypi.org/project/pycfg/) in 2 following ways:
1.  [By Directly using the file](https://www.geeksforgeeks.org/draw-control-flow-graph-using-pycfg-python/#first)
2.  [By importing library in the program](https://www.geeksforgeeks.org/draw-control-flow-graph-using-pycfg-python/#second)

**By Directly using the file**
3.  [Download pycfg tar file](https://files.pythonhosted.org/packages/1b/56/e837ca7330163dd5834c0223adf8057513105081b0f7966bed305edac114/pycfg-0.1.tar.gz)
4.  UnZip it
5.  Use  `pycfg.py`  file.

**Note:** pycfg.py file location after unzipping is  `pycfg-0.1/pycfg/pycfg.py`.

Let’s take  **whiletest.py**  file to get CFG. This is the sample code to get the desired output. Please follow the below steps to successfully proceed the installation of pycfg.

	a= 10
	while(a <= 0): 
	if a == 5: 
	print(a) 
	a += 1
	print("exited") 

Run below command on terminal (path_to is the directory/folder where the file is stored).
	
	python path_to/pycfg.py path_to/whiletest.py -d
Syntax Output:

![](https://media.geeksforgeeks.org/wp-content/uploads/20190903005403/gfg123-300x273.png)

This approach gives output in the form of Graph having Nodes, labeled Sentences, edges between nodes.

The other installation procedure for installation of pycfg is as directed below:

 **By importing library in the program**

With help of importing linrary and  [tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/), we can do way better than just using  **pycfg.py**  file alone.

-   Representing CFG instead of terminal.
-   Find cyclomatic complexity also

Run the below command (Ensure the version of the python you are using).

	sudo pip install pycfg or sudo pip3 install pycfg

Once Done, using same  **whiletest.py**  for testing. We can run the following python program on  **whiletest.py**.

Syntax (path_to here is the saved file location)

	 python /path_to/this_file.py /path_to/whiletest.py

Below is the code for the pycfg code:

	from pycfg.pycfg import PyCFG, CFGNode, slurp 
	import argparse 
	import tkinter as tk 
	from PIL import ImageTk, Image 

	if __name__ == '__main__': 
	parser = argparse.ArgumentParser() 

	parser.add_argument('pythonfile', help ='The python file to be analyzed') 
	args = parser.parse_args() 
	arcs = [] 

	cfg = PyCFG() 
	cfg.gen_cfg(slurp(args.pythonfile).strip()) 
	g = CFGNode.to_graph(arcs) 
	g.draw(args.pythonfile + '.png', prog ='dot') 

	# Draw using tkinter. 
	root = tk.Tk() 
	root.title("Control Flow Graph") 
	img1 = Image.open(str(args.pythonfile) + ".png") # PIL solution 
	img1 = img1.resize((800, 600), Image.ANTIALIAS) 
	img = ImageTk.PhotoImage(img1) 
	
	background ="gray"

	panel = tk.Label(root, height = 600, image = img) 
	panel.pack(side = "top", fill ="both", expand = "yes") 
	nodes = g.number_of_nodes()	 # no. of nodes. 
	edges = g.number_of_edges()	 # no. of Edges. 
	complexity = edges - nodes + 2		 # Cyclomatic complexity 

	frame = tk.Frame(root, bg = background) 
	frame.pack(side ="bottom", fill ="both", expand = "yes") 
		
	tk.Label(frame, text ="Nodes\t\t"+str(nodes), bg = background).pack() 
	tk.Label(frame, text ="Edges\t\t"+str(edges), bg = background).pack() 
	tk.Label(frame, text ="Cyclo Complexity\t"+
			str(complexity), bg = background).pack() 

	root.mainloop() 

Output after combining the while test code and the pycfg.py code:
![](https://media.geeksforgeeks.org/wp-content/uploads/20190907103732/gfg59.png)
