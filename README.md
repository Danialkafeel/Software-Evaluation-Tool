Code Complexity Evaluation Tool

**What is a Cyclomatic complexity?**

Cyclomatic complexity is a software metric used to indicate the complexity of a program. It is a quantitative measure of the number of linearly independent paths through a program's source code.

It is computed using the Control Flow Graph of the program. The nodes in the graph indicate the smallest group of commands of a program, and a directed edge in it connects the two nodes i.e. if second command might immediately follow the first command. 

For example, if source code contains no control flow statement then its cyclomatic complexity will be 1 and source code contains a single path in it. Similarly, if the source code contains one if condition then cyclomatic complexity will be 2 because there will be two paths one for true and the other for false. 

Mathematically, for a structured program, the directed graph inside control flow is the edge joining two basic blocks of the program as control may pass from first to second.  
So, cyclomatic complexity M would be defined as,

	 M = E – N + 2P
	 where,  
	 E = the number of edges in the control flow graph  
	 N = the number of nodes in the control flow graph  
	 P = the number of connected components  

Steps that should be followed in calculating cyclomatic complexity and test cases design are:  

-   Construction of graph with nodes and edges from code.
-   Identification of independent paths.
-   Cyclomatic Complexity Calculation
-   Design of Test Cases

Let a section of code as such:  

	A = 10
	  IF B > C THEN
	     A = B
	  ELSE
	     A = C
	  ENDIF
	Print A	
	Print B
	Print C

**Control Flow Graph** of above code

![Control Flow Graph Example](https://github.com/abhaymehtre/Software-Evaluation-Tool/blob/master/images/2.png)

The cyclomatic complexity calculated for above code will be from control flow graph. The graph shows seven shapes(nodes), seven lines(edges), hence cyclomatic complexity is 7-7+2 = 2.

**Use of Cyclomatic Complexity:**  

-   Determining the independent path executions thus proven to be very helpful for Developers and Testers.
-   It can make sure that every path have been tested at least once.
-   Thus help to focus more on uncovered paths.
-   Code coverage can be improved.
-   Risk associated with program can be evaluated.
-   These metrics being used earlier in the program helps in reducing the risks.

**Advantages of Cyclomatic Complexity:**.

-   It can be used as a quality metric, gives relative complexity of various designs.
-   It is able to compute faster than the Halstead’s metrics.
-   It is used to measure the minimum effort and best areas of concentration for testing.
-   It is able to guide the testing process.
-   It is easy to apply.

**Disadvantages of Cyclomatic Complexity:**

-   It is the measure of the programs’s control complexity and not the data the data complexity.
-   In this, nested conditional structures are harder to understand than non-nested structures.
-   In case of simple comparisons and decision strucures, it may give a misleading figure.

**Installation Steps for the Cyclomatic Complexity Tools**
-   Please follow the below steps to get a proper installation of tools done.
-   Install Pycfg in the first place.
-   Secondly, use the installation procedure for graphviz and 
-   Lastly, install radon.

The above flow has to be strictly be followed. Incase of any other flow you would end into trouble while installing the tools.


 **Tools used for the calculating the cyclomatic Complexity are:**
 - Pycfg -  Usually, we draw manual _Control Flow Graph_ using pen and paper by analyzing the control flow of the program. CFG helps us finding independent paths ([Cyclomatic Complexity](https://www.geeksforgeeks.org/cyclomatic-complexity/)), which leads to the number of test cases required to test the program. We can automate the CFG task using a Python library called [pycfg](https://pypi.org/project/pycfg/). This library takes a Python script as input and gives graph as output.

[Installation Instructions](https://github.com/abhaymehtre/Software-Evaluation-Tool/blob/master/Pycfg%20Installation%20Procedure.md)

- Graphviz - Graph visualization is a way of representing structural information as diagrams of abstract graphs and networks. Automatic graph drawing has many important applications in software engineering, database and web design, networking, and in visual interfaces for many other domains. 
	- Graphviz is open source graph visualization software. It has several main graph layout programs. See the  [gallery](https://graphviz.org/gallery)  for some sample layouts. It also has web and interactive graphical interfaces, and auxiliary tools, libraries, and language bindings.

[Installation Instructions](https://github.com/abhaymehtre/Software-Evaluation-Tool/blob/master/Graphviz%20Installation%20Procedure.md)


- Radon - Radon is a Python tool that computes various metrics from the source code. Radon can compute:
	-   **McCabe’s complexity**, i.e. cyclomatic complexity
	-   **raw**  metrics (these include SLOC, comment lines, blank lines, &c.)
	-   **Halstead**  metrics (all of them)
	-   **Maintainability Index**  (the one used in Visual Studio)

[Installation Instructions](https://github.com/abhaymehtre/Software-Evaluation-Tool/blob/master/Radon%20Installation%20Procedure.md)

