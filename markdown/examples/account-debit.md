## AccountDebit Example

The following snippet describes the states and the transitions of the AccountDebit JSXM specification.

```
  <!--States definition-->
  <states>
    <state name="empty" />
    <state name="credit" />
    <state name="debit" />
  </states>
  
  <!--Initial State definition-->
  <initialState state="empty" />
  
  <!--Transitions definition-->
    <transitions>
        <transition from="empty" function="DepositCredit" to="credit" />
        <transition from="empty" function="WithdrawDebit" to="debit" />
        <transition from="credit" function="DepositCredit" to="credit" />
        <transition from="credit" function="WithdrawCredit" to="credit" />
        <transition from="credit" function="WithdrawEmpty" to="empty" />
        <transition from="credit" function="WithdrawDebit" to="debit" />
        <transition from="debit" function="DepositDebit" to="debit" />
        <transition from="debit" function="DepositEmpty" to="empty" />
        <transition from="debit" function="DepositCredit" to="credit" />
        <transition from="debit" function="WithdrawError" to="debit" />
    </transitions>
```

*The example contains implementation, specification and the java adapter.

Download the <a class="btn btn-success" href="../examples-downloads/AccountDebit.zip"><span class="icon-download-alt icon-large" style="margin: 0px;"></span> AccountDebit</a> Maven project.

[1]: ../examples-downloads/AccountDebit.zip      "AccountDebit"  