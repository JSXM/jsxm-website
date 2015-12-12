## Account Example

The Account example describes a bank account stream x machine that consists of 4 different states. Initial, opened, closed and normal. The user can
open an account, close an account, deposit and withdraw money.

The following snippet describes the states and the transitions of the Account JSXM specification.

```
    <!--States definition-->
    <states>
        <state name="initial"/>
        <state name="opened"/>
        <state name="closed"/>
        <state name="normal"/>
    </states>

    <!--Initial State definition-->
    <initialState state="initial"/>

    <!--Transitions definition-->
    <transitions>
        <transition from="initial" function="open" to="opened"/>
        <transition from="opened" function="close" to="closed"/>
        <transition from="opened" function="deposit" to="normal"/>
        <transition from="normal" function="deposit" to="normal"/>
        <transition from="normal" function="withdrawN" to="normal"/>
        <transition from="normal" function="withdraw0" to="opened"/>
        <transition from="opened" function="readbalance" to="opened"/>
        <transition from="normal" function="readbalance" to="normal"/>
    </transitions>
```

*The example contains implementation, specification and the java adapter.

Download the <a class="btn btn-success" href="../examples-downloads/Account.zip"><span class="icon-download-alt icon-large" style="margin: 0px;"></span> Account</a> Maven project.


[1]: ../examples-downloads/Account.zip      "Account"  

