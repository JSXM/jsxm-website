
## Overview

JSXM is a model-based testing tool. The tool is implemented in Java and allows 
the automated generation of test cases based on a model of the software to be tested. 
The model is expressed as a Stream X-machine (SXM). With the help of JSXM the 
specifed model can be used for: Model Animation, Test Generation and Test Transformation.

##JSXM Models
JSXM models are a special type of extended finite state machines, called Stream X-Machines (SXMs). 
SXMs allow the description of both the control and the data of a system. 
The most important advantage of SXMs is their testing method. It can be guaranteed that under certain 
desing-for-test conditions, the generated test cases reveal all functional inconsistencies in the implementation.

JSXM's modelling language is based on XML and inline Java code. It supports XSD types. 
It supports the automatic generation of JUnit test cases for testing Java applications.

## Model Animation
Animation of the model means execution of the model or simulation of the modeled software. 
Interactive or batch animation allow the model designer to validate the specification, 
i.e. ensure that the correct functionality is modeled.

## Test Transformation

Since the generated test cases are independent of the underlying technology of the implementation under test, 
the tests cannot be directly used for testing. A Test Transformer is responsible 
for transforming the general test cases to concrete test cases.

## Test Generation

The generated test cases are in XML format and they are independent of the 
technology or programming language of the implementation. This means that the 
implementation under test can be an application any programming language or implementation platform.