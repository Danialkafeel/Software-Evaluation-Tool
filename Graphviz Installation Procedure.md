# Graph Visualization Tool

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

**Installation Procedure for Graphviz (Graph Visualization)**

Graph visualization is a way of representing structural information as diagrams of abstract graphs and networks. Automatic graph drawing has many important applications in software engineering, database and web design, networking, and in visual interfaces for many other domains.

Graphviz is open source graph visualization software. It has several main graph layout programs. See the  [gallery](https://graphviz.org/gallery)  for some sample layouts. It also has web and interactive graphical interfaces, and auxiliary tools, libraries, and language bindings.

To install the Graph Visualization tool there are two ways :

- GUI based installation
- CLI based installation

**GUI Based Installation**

[Source code packages](https://graphviz.org/download/source/)  for the latest stable and development versions of Graphviz are available, along with instructions for anonymous access to the sources using  [Git](http://git-scm.com/).

For most cases where you want or need to build from source, you should grab one of the source packages linked below. They contain all of required generated files. You just need to run  `configure`  to tailor the build to your machine and its libraries. The typical installation process is:

```
	./configure
	make
	make install
```

The  `configure`  script has many options for further tailoring the build process. Run to see these help files.

```
	./configure --help
```
The path for the GUI download:
	
	https://www2.graphviz.org/Packages/stable/portable_source/
Using the above path you will get the zipped code for download , please select the latest version of the graphviz tool ([graphviz-2.44.1.tar.gz](https://www2.graphviz.org/Packages/stable/portable_source/graphviz-2.44.1.tar.gz)).
Please use extraction tool to extract the above tool and please go through the installation/readme file for the installation.

Please redirect to the downloaded file path and follow the above said installation process to setup the graph visualization tool.

**For the CLI based installation:**

This package runs under Python 2.7, and 3.5+, use  [pip](https://pip.readthedocs.io/)  to install:

	$ pip install graphviz or pip3 install graphviz

To render the generated DOT source code, you also need to install Graphviz ([download page](https://www.graphviz.org/download/)).

Make sure that the directory containing the  dot  executable is on your systems’ path.

Basic Code:

Create a graph object:

	>>> from graphviz import Digraph

	>>> dot = Digraph(comment='The Round Table')

	>>> dot  #doctest: +ELLIPSIS
<graphviz.dot.Digraph object at 0x...>

Add nodes and edges:

	>>> dot.node('A', 'King Arthur')
	>>> dot.node('B', 'Sir Bedevere the Wise')
	>>> dot.node('L', 'Sir Lancelot the Brave')

	>>> dot.edges(['AB', 'AL'])
	>>> dot.edge('B', 'L', constraint='false')

Check the generated source code:

	print(dot.source)  # doctest: +NORMALIZE_WHITESPACE
	// The Round Table
	digraph {
    A [label="King Arthur"]
    B [label="Sir Bedevere the Wise"]
    L [label="Sir Lancelot the Brave"]
    A -> B
    A -> L
    B -> L [constraint=false]
	}

Save and render the source code, optionally view the result:

	>>> dot.render('test-output/round-table.gv', view=True)  # doctest: +SKIP
	'test-output/round-table.gv.pdf'

![https://raw.github.com/xflr6/graphviz/master/docs/round-table.png](https://warehouse-camo.ingress.cmh1.psfhosted.org/a766bec03dd2c54ad1bf1c96d3277a49bc840a11/68747470733a2f2f7261772e6769746875622e636f6d2f78666c72362f677261706876697a2f6d61737465722f646f63732f726f756e642d7461626c652e706e67)

Reference to the above information https://pypi.org/project/graphviz/.



