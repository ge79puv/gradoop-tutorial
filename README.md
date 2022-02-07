# Gradoop Tutorial about subgraph operator


## Setup

The following explains which software is required for the Gradoop tutorial.

### Java

For the Gradoop-Tutorial java 8 is required. Install Java 8 (Unix). For Windows installation see [here](https://www.java.com/en/download/help/windows_manual_download.html).
 
```
sudo apt install openjdk-8-jdk
```

Check Java Version:

```
java -version
```

The output should be something like:

```
openjdk version "1.8.0_265"
```

### Maven

Installation of maven 3 (Unix). For Windows installation see [here](https://docs.wso2.com/display/IS323/Installing+Apache+Maven+on+Windows).

```
sudo apt install maven
```

Check maven version:

```
mvn -version 
```

Output should look like this:

```
Apache Maven 3.6.3
Maven home: /usr/share/maven
Java version: 1.8.0_265, vendor: Private Build, runtime: /usr/lib/jvm/java-8-openjdk-amd64/jre
```

### Graphviz

To visualize the results of our task, you need to use the .dot format that is supported by [Graphviz](https://graphviz.gitlab.io/download/).
There is the Online GraphViz tool [here](https://dreampuf.github.io/GraphvizOnline/#digraph%20%7B%0A%0Asubgraph%20cluster_g5f510d30ea80a38fa8609449%7B%0Alabel%3D%22Gradoop%20Tutorial%22%3B%0Av5f510d30ea80a38fa86094465f510d30ea80a38fa8609449%20%5Bshape%3DMrecord%2C%20label%3D%22Hello%22%5D%3B%0Av5f510d30ea80a38fa86094475f510d30ea80a38fa8609449%20%5Bshape%3DMrecord%2C%20label%3D%22World%22%5D%3B%0Av5f510d30ea80a38fa86094465f510d30ea80a38fa8609449-%3Ev5f510d30ea80a38fa86094475f510d30ea80a38fa8609449%20%5Blabel%3D%225f510d30ea80a38fa8609448%22%5D%3B%0A%7D%0A%0A%7D) where you can open the generated dot files with notepad and paste the content of it on the Online GraphViz tool.

## Program Execution

### Clone the repository
First clone the git [gradoop-tutorial](https://github.com/dbs-leipzig/gradoop-tutorial) repository.

```
git clone https://github.com/dbs-leipzig/gradoop-tutorial.git
```

### See the original graph structure
In this tutorial you need to edit the Java program in `/gradoop-tutorial/src/main/java/org/gradoop/tutorial/operators/subgraph/` called SubgraphTutorial_1.java. The use of the subgraph operator is on line 63. 

```
graph = graph.subgraph(new ByLabel<>("person"), new ByLabel<>("knows"));
```

Firstly, let's see how the original graph structure looks like, so comment out this line. 

Go into the '/gradoop-tutorial' folder. Delete all previously compiled Java files and resources, and then compile, test & package a new Java project.

```
mvn clean install
```

Then execute this new Java program.

```
mvn exec:java -Dexec.mainClass="org.gradoop.tutorial.operators.subgraph.SubgraphTutorial_1" -Dexec.cleanupDaemonThreads=false
```

In '\gradoop-tutorial\gradoop_tutorial_output' you can see the first output called 01_subgraph_1.dot. Open it and paste the content of it on the Online GraphViz tool. Here you can see the original graph. In addition, before executing a new Java program you need to rename the first output file.

### Use the subgraph operator
Now, let the subgraph operator is on line 63 work and repeat the above process of 'mvn clean install' and 'mvn exec'. Then you will see the new output after using the subgraph operator. In this program, you create a subgraph that contains "person" vertices and "knows" edges only.

