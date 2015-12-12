## jsxm-quickstart-archetype

The archetype provides the pox.xml settings for the successful execution of JSXM maven plugin.

Furthermore the archetype generates the folder structure and an abstract example in order to provide a good insight of how an Stream X machine can be described using the JSXM language. 

The Quickstart.xml and Quickstart_sets.xml are loacated inside the src/spec/org/jsxm/examples/Quickstart/specification. 

The spec folder is automatically added in the classpath as a classpathentry and is treated as a source folder in order to provide quick navigation in the example.

## jsxm-example-archetype

The archetype provides the pox.xml settings and the configuration for creating a complete JSXM example that could be compiled, animated and tested using the available goals.


## jsxm-generate-m2e-archetype

The archetype provides the pox.xml settings the  folder structure and a sample JSXM specification with sets, implementation, and the Java adapter. 

The sample JSXM could be compiled, animated and tested using the available goals. The difference of this archetype and jsxm-example is the fact that the pom.xml of this archetype inlcudes the configuration required by Eclipse(m2e) in order to allow the plugin to be executed as a part of Eclipse workspace full or incremental build. 

The project created by this  archetype can be triggered by using clean with install, test or deploy.

