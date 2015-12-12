## MarsExplorerJSXM Example

MarsExplorerJSXM  contains 4 JSXM specifications that are tranformed to Repast Agents and can be used in the [Repast Framework][2]. 
The specifications are Crumb, Explorer, Obstacle and Sample.

### Crumb
The following snippet describes the states and the transitions of the Crumb JSXM specification.

```
    <!--States definition-->
    <states>
        <state name="initial" />
    </states>
    <!--Initial State definition-->
    <initialState state="initial" />
    <!--Transitions definition-->
    <transitions>
        <transition from="initial" function="Step" to="initial" />
    </transitions>
```

### Explorer
The following snippet describes the states and the transitions of the Explorer JSXM specification.

```
    <!--Dependencies definition-->
    <dependencies>
        <uses sxm="Obstacle"/>
        <uses sxm="Sample"/>
        <uses sxm="Crumb"/>
    </dependencies>
    <!--States definition-->
    <states>
        <state name="initial" />
        <state name="carrying" />
    </states>
    <!--Initial State definition-->
    <initialState state="initial" />
    <!--Transitions definition-->
    <transitions>
        <transition from="initial" function="MoveRandomly" to="initial" />
        <transition from="initial" function="FollowCrumb" to="initial" />
        <transition from="initial" function="AvoidObstacle" to="initial" />
        <transition from="initial" function="Carry" to="carrying" />
        <transition from="carrying" function="MoveToBase" to="carrying" />
        <transition from="carrying" function="AvoidObstacle" to="carrying" />
        <transition from="carrying" function="DropAtBase" to="initial" />
    </transitions>
```

### Obstacle
The following snippet describes the states and the transitions of the Obstacle JSXM specification.

```
    <!--States definition-->
    <states>
        <state name="initial" />
    </states>
    <!--Initial State definition-->
    <initialState state="initial" />
    <!--Transitions definition-->
    <transitions>
        <transition from="initial" function="Nothing" to="initial" />
    </transitions>
```

### Sample
The following snippet describes the states and the transitions of the Sample JSXM specification.

```
    <!--Dependencies definition-->
    <dependencies>
        <uses sxm="Explorer" />
    </dependencies>
    <!--States definition-->
    <states>
        <state name="initial" />
        <state name="carried" />
        <state name="atbase" />
    </states>
    <!--Initial State definition-->
    <initialState state="initial" />
    <!--Transitions definition-->
    <transitions>
        <transition from="initial" function="Carried" to="carried" />
        <transition from="carried" function="Move" to="carried" />
        <transition from="carried" function="Dropped" to="atbase" />
    </transitions>
```

*The specifications included in this example are not compilable and cannot be animated.

Download the <a class="btn btn-success" href="../examples-downloads/MarsExplorerJSXM.zip"> <span class="icon-download-alt icon-large" style="margin: 0px;"></span>  MarsExplorerJSXM</a> Maven project.

[1]: ../examples-downloads/MarsExplorerJSXM.zip      "MarsExplorerJSXM" 
[2]: http://repast.sourceforge.net/      "Repast Framework" 
