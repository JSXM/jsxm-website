## VendingMachine Example

VendingMachine is a specification describing a simple vending machine that provides drinks 
by using coins.

The following snippet describes the states and the transitions of the VendingMachine JSXM specification.

```
  <!--States definition-->
  <states>
    <state name="charging" />
    <state name="full" />
  </states>
  <!--Initial State definition-->
  <initialState state="charging" />
  <!--Transitions definition-->
  <transitions>
    <transition from="charging" function="acceptMoney" to="charging" />
    <transition from="charging" function="acceptFullAmount" to="full" />
    <transition from="full" function="getDrink" to="charging" />
    <transition from="charging" function="drink_error" to="charging" />
    <transition from="full" function="coin_error" to="full" />

  </transitions>
```

*The example does not contain implementation and the java adapter. 

Download the <a class="btn btn-success" href="../examples-downloads/VendingMachine.zip"> <span class="icon-download-alt icon-large" style="margin: 0px;"></span>  VendingMachine</a> Maven project.

[1]: ../examples-downloads/VendingMachine.zip      "VendingMachine" 