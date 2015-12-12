## eShop Example

Shipment is a specification describing a shipment process when an order is made in an eShop. 
Shipment uses various XSDs, similar to the Cart example.

The following snippet describes the states and the transitions of the Shipment JSXM specification.

```
    <!--States definition-->
    <states>
        <state name="initial"/>
        <state name="created"/>
        <state name="quoteOffered"/>
        <state name="confirmed"/>
        <state name="cancelled"/>
    </states>
    <!--Initial State definition-->
    <initialState state="initial"/>
    <transitions>
        <transition from="initial" function="createPF" to="created"/>
        <transition from="created" function="getShipmentRatePF" to="quoteOffered"/>
        <transition from="quoteOffered" function="getShipmentRatePF" to="quoteOffered"/>
        <transition from="created" function="cancelPF" to="cancelled"/>
        <transition from="quoteOffered" function="cancelPF" to="cancelled"/>
        <transition from="quoteOffered" function="confirmPF" to="confirmed"/>
        <transition from="confirmed" function="getConfirmedRatePF" to="confirmed"/>
    </transitions>
```

*The example does not contain implementation and the java adapter. 

Download the <a class="btn btn-success" href="../examples-downloads/eShop.zip"> <span class="icon-download-alt icon-large" style="margin: 0px;"></span>  eShop</a> Maven project.

[1]: ../examples-downloads/eShop.zip      "eShop" 