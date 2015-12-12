## Cart Example

Cart is a specification of a shopping cart similar to the shopping carts that are used 
in online shopping. The Cart uses XSDs for declaring user defined types such as
PaymentType, OrderDetailsType, CartItemType and CartType.  

The following snippet describes the states and the transitions of the Cart JSXM specification.

```
    <!--States definition-->
    <states>
        <state name="shopping"/>
        <state name="pending"/>
    </states>

    <!--Initial state definition-->
    <initialState state="shopping"/>

    <!--Transitions definition-->
    <transitions>
        <transition from="shopping" function="addToCartPF" to="shopping"/>
        <transition from="shopping" function="removeFromCartPF" to="shopping"/>
        <transition from="shopping" function="getCartPF" to="shopping"/>
        <transition from="shopping" function="setCartPF" to="shopping"/>
        <transition from="shopping" function="checkOutPF" to="pending"/>
    </transitions>
```

*The example does not contain implementation and the java adapter. 

Download the <a class="btn btn-success" href="../examples-downloads/Cart.zip"> <span class="icon-download-alt icon-large" style="margin: 0px;"></span>  Cart</a> Maven project.

[1]: ../examples-downloads/Cart.zip      "Cart" 