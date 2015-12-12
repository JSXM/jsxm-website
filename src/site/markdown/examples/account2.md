## Account2 Example

The Account2 example is an extension of the [Account](account.html "Account") example  
which describes the faults 

The following snippet describes the transitions of the Account2 JSXM specification.

```
    <!--Transitions definition-->
    <transitions>
        <transition from="initial" function="Open" to="active"/>
        <transition from="active" function="Close" to="closed"/>
        <transition from="active" function="Deposit" to="normal"/>
        <transition from="normal" function="Deposit" to="normal"/>
        <transition from="normal" function="Withdraw" to="normal"/>
        <transition from="normal" function="WithdrawAll" to="active"/>

        <!-- Complete -->

        <transition from="initial" function="CloseErr" to="initial"/>
        <transition from="initial" function="DepositErr" to="initial"/>
        <transition from="initial" function="WithdrawErr" to="initial"/>

        <transition from="active" function="OpenErr" to="active"/>
        <transition from="active" function="WithdrawErr" to="active"/>
        <transition from="active" function="DepositNegErr" to="active"/>

        <transition from="normal" function="OpenErr" to="normal"/>
        <transition from="normal" function="CloseErr" to="normal"/>
        <transition from="normal" function="WithdrawNegErr" to="normal"/>
        <transition from="normal" function="WithdrawOverErr" to="normal"/>
        <transition from="normal" function="DepositNegErr" to="normal"/>

        <transition from="closed" function="CloseErr" to="closed"/>
        <transition from="closed" function="OpenErr" to="closed"/>
        <transition from="closed" function="WithdrawErr" to="closed"/>
        <transition from="closed" function="DepositErr" to="closed"/>
    </transitions>
```

*The example contains implementation, specification and the java adapter. 

Download the <a class="btn btn-success" href="../examples-downloads/Account2.zip"><span class="icon-download-alt icon-large" style="margin: 0px;"></span> Account2</a> Maven project. 

Download the <a class="btn btn-success" href="../examples-downloads/Account2NoImple.zip"> <span class="icon-download-alt icon-large" style="margin: 0px;"></span>  Account2NoImple</a> Maven project without implementation.


[1]: ../examples-downloads/Account2.zip      "Account2"
[2]: ../examples-downloads/Account2NoImple.zip      "Account2NoImple" 