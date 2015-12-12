## Automaton Example

The Automaton example describes simple automaton that can be started, stopped and reseted.
The example contains also the fault behaviour.  

The following snippet describes the states and the transitions of the Automaton JSXM specification.

```
  <!--States definition-->
  <states>
    <state name="initial" />
    <state name="middle" />
    <state name="terminal" />
  </states>
  <!--Initial State definition-->
  <initialState state="initial" />
  <!--Transitions definition-->
  <transitions>
    <transition from="initial" function="startAutomaton" to="middle" />
    <transition from="middle" function="stopAutomaton" to="terminal" />
    <transition from="terminal" function="resetAutomaton" to="initial" />
    <transition from="middle" function="resetAutomaton" to="initial" />
    <transition from="terminal" function="startError" to="terminal" />
    <transition from="middle" function="startError" to="middle" />
    <transition from="initial" function="stopError" to="initial" />
    <transition from="terminal" function="stopError" to="terminal" />
    <transition from="initial" function="resetError" to="initial" />
  </transitions>
```

*The example contains implementation, specification and the java adapter. 

Download the <a class="btn btn-success" href="../examples-downloads/Automaton.zip"> <span class="icon-download-alt icon-large" style="margin: 0px;"></span>  Automaton</a> Maven project.

[1]: ../examples-downloads/Automaton.zip      "Automaton" 