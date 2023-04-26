BDD Reordering

## What is this project?
This is a final project for ECE5740/6740-CAD of Digital Circuits at the University of Utah.
The purpose of this project is to find a variable ordering that results in a minimized node side in a BDD. 
This code is a C program that processes a given digital circuit represented as a Boolean network and constructs its Binary Decision Diagrams (BDDs). BDDs are a compact graphical representation of boolean functions, widely used in digital circuit design, formal verification, and synthesis.
Specifically, this code does the following:
1. Reads a BLIF (Berkeley Logic Interchange Format) file, which represents a digital circuit as a Boolean network.
2. Parses the BLIF file to create a BnetNetwork structure that holds the circuit's information, including inputs, outputs, and internal nodes (gates).
3. Initializes a CUDD (CU Decision Diagram) package's DdManager, which is a data structure used for managing BDDs.
4. Constructs BDDs for the given Boolean network using the CUDD package.
5. Applies various reordering techniques to minimize the BDDs' size (number of nodes). These techniques include sequential reordering, optimal reordering, and dynamic reordering.
6. Outputs statistics about the original and reordered BDDs, such as the number of nodes, edges, and levels, as well as the percentage of improvement.
7. Dumps the BDDs in DOT format, which is a standard graph description langua, suitable for visualization or further processing.
8. Frees the memory allocated for the BnetNetwork structure and the DdManager.

## Repository Structure
cudd-2.5.0 contains the cudd-package
+ cudd-location file to store the path to cudd-2.5.0
+ blif2bdd contains the source files and the executable file.
+ bench contains benchmarks
+ test contains test files

## Compile steps
Navigate into cudd-2.5.0

```bash
make distclean
make
```
navigate to base directory

```bash
make distclean
make
```

## Run
navigate to blif2bdd directory
```bash
./blif2bdd ../test/test-file.blif
or
./blif2bdd ../bench/bench-file.blif
Replace test-file.blif or bench-file.blif with the file you want to run.

For example, 
./blif2bdd ../bench/adder8.blif
```
