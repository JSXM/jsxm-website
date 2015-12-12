#### Graphical SXM Animation

![JSXM Animator](images/animator.png)

Graphical animator for testing the Stream X Machine.

#### JUnit Test Generation

![JSXM Animator](images/junitTest.png)

JUnit tranformers for generating JUnit tests from the abstract XML
tests. PHP and Javascript tranformers will be added soon.

#### Sample Generation

![Page layouts](images/sampleGeneration.png)

Automatic generation of JSXM models for easier integration with
existing projects. 


#### Model Validation

![Modern skin](images/validation.png)

JSXM models are validated against XSD schemas to ensure that the 
specifications match the SXM rules.


#### Advanced Configuration

![Animate list and individual k](images/kAnimate.png)

Each JSXM specification can be processed using a different k without affecting the general k 
or any other specification.


#### Advanced Configuration cont.

![Customizable Threadpools and advanced logging](images/loggingPool.png)


---


## Usage

To use this Maven plugin, include it in your pom.xml plugins section:

```xml
<plugins>
  ...
            <plugin>
                <groupId>org.jsxm.maven.plugin</groupId>
                <artifactId>jsxm-maven-plugin</artifactId>
                <version>1.4.11-RC1</version>
            </plugin>
  ...
</plugins>
```



## POM Repositories

Add jsxm repository to the repositories in the POM file:

[reflow-tools]: ../reflow-velocity-tools

```xml
    <pluginRepositories>
        ...
        <pluginRepository>
            <releases>
                <enabled>true</enabled>
                <updatePolicy>always</updatePolicy>
                <checksumPolicy>fail</checksumPolicy>
            </releases>
            <id>jsxm</id>
            <name>JSXM Model Based Testing</name>
            <url>http://www.jsxm.org/maven2/</url>
        </pluginRepository>
        ...
    </pluginRepositories>

```

[1]: plugin-info.html      "JSXM Goals" 

## Multi threaded

JSXM Maven plugin is designed to support different multi-threaded implementations.
Taking advantage of the factory and thread pool patterns there is an easy 
way of switching thread pool implementations by changing the following properties in the pom.xml

-   **banimationThreadPool** - thread pool responsible for the banimation phase
-   **compilationThreadPool** - thread pool responsible for the compilation phase
-   **sampleCreationThreadPool** - thread pool responsible for the sample creation phase
-   **externalPackageCreationThreadPool** - thread pool responsible for the copying external package structure
-   **generationThreadPool** - thread pool responsible for the generation phase
-   **transformationThreadPool** - thread pool responsible for the transformation phase
-   **validationThreadPool** - thread pool responsible for the validation phase

**The available options for each thread pool are

-     **cachedThreadPool**
-     **fixedThreadPool**
-     **singleFixedThreadPool**
-     **singleThreadExecutor**

## Logging Configuration

JSXM Maven Plugin uses logback and currently supports 3 different exports.
HTML, PDF and txt logs. Each file can have its own logger level, independent 
from the other files. The available logging levels are: 
 
-     **WARN** - Prints warn messages.
-     **ERROR** - Prints error and warn messages.
-     **INFO** - Prints info, error and warn messages.
-     **DEBUG** - Prints debug, info, error and warn messages.
-     **TRACE** - Prints trace, debug, warn, error and info messages.
-     **OFF** - No logging. 

The above levels can be used as a text inside the configuration properties
below. 

```xml
    <configuration>
        ...
        <consoleLoggerLevel>LOGGING_LEVEL</consoleLoggerLevel>
        <htmlFileLoggerLevel>LOGGING_LEVEL</htmlFileLoggerLevel>
        <txtFileLoggerLevel>LOGGING_LEVEL</txtFileLoggerLevel>
        ...
    </configuration>

```


*Tip: In case you have enough experience in writing JSXM specifications you can just turn off the console and txt logger 
and let the HTML logger report only errors. 

---


## ANSI Support

JSXM Maven plugin supports message output using ANSI escape code.
By setting the parameter ansiSupport to true, messages in the console
will be colorful. The plugin uses a special profile which is triggered 
when a windows platform is detected in order to download the org.fusesource.jansi
library to allow support in a windows terminal in comparison with Unix 
based platforms that natively support ANSI and do not require any additional library.
ANSI is also supported by Netbeans and Eclipse IDE, although the latter requires 
an extra plugin.  

---

## Graphical Interface Animation

JSXM Maven plugin has a built in graphical envirnoment
for animating JSXM models. The SXM under animation can be
reseted at any point and the animation can be saved 
and used with batch animation processing. The environment
is aware of every SXMs current state so 
switching between SXM instances animation can be safely   
done without lossing the current animation. 

---

