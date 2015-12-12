## Calculation Addition Subtraction Example

CalcPlusMinus is a specification of a simple calculator accepting one digit at a time and performing addition and subtraction. 
This is an example of a uniform specification since test inputs do not depend on memory. 
Therefore all test sequences are realizable. This is an input-complete specification.

The following snippet describes the states and the transitions of the CalcPlusMinus JSXM specification.

```
    <!--States definition-->
    <states>
        <state name="initial"/>
        <state name="accept"/>
        <state name="result"/>
    </states>

    <!--Initial State definition-->
    <initialState state="initial"/>

    <!--Transitions definition-->
    <transitions>
        <transition from="initial" function="digit1" to="accept"/>
        <transition from="accept" function="digitN" to="accept"/>
        <transition from="accept" function="add" to="initial"/>
        <transition from="accept" function="sub" to="initial"/>
        <transition from="accept" function="res" to="result"/>
        <transition from="result" function="digit1" to="accept"/>
        <transition from="result" function="add" to="initial"/>
        <transition from="result" function="sub" to="initial"/>
        <transition from="initial" function="addErr" to="initial"/>
        <transition from="initial" function="subErr" to="initial"/>
        <transition from="initial" function="resErr" to="initial"/>
        <transition from="initial" function="dig1Err" to="initial"/>
        <transition from="accept" function="digNErr" to="accept"/>
        <transition from="result" function="resErr" to="result"/>
        <transition from="result" function="dig1Err" to="result"/>
    </transitions>
```

*The example contains implementation, specification and the java adapter. 

Download the <a class="btn btn-success" href="../examples-downloads/CalculatorAdditionSubtraction.zip"> <span class="icon-download-alt icon-large" style="margin: 0px;"></span>  CalculatorAdditionSubtraction</a> Maven project.

[1]: ../examples-downloads/CalculatorAdditionSubtraction.zip      "CalculatorAdditionSubtraction" 