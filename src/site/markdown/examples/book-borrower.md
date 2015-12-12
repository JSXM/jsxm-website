## Book Borrower Example

The Book Borrower example describes 3 different specifications that depend on each other.
The inlcuded specifications are Book, Borrower and Library. The Library consists of
Books and Borrowers and the Borrowers can borrow books that are available from the Library.

The following snippet describes the states and the transitions of the Book JSXM specification.

```
    <!--States definition-->
    <states>
        <state name="available"/>
        <state name="borrowed"/>
    </states>

    <!--Initial State definition-->
    <initialState state="available"/>

    <!--Transitions definition-->
    <transitions>
        <transition from="available" function="setBorrowedPF" to="borrowed"/>
        <transition from="borrowed" function="releasePF" to="available"/>
        <transition from="available" function="bookIsAvailablePF" to="available"/>
        <transition from="borrowed" function="bookIsNotAvailablePF" to="borrowed"/>
    </transitions>
```

The following snippet describes the dependencies, states and the transitions of the Borrower JSXM specification.

```
    <dependencies>
        <uses sxm="Book"/>
    </dependencies>

    <!--States definition-->
    <states>
        <state name="noBook"/>
        <state name="oneBook"/>
    </states>
    <!--Initial State definition-->
    <initialState state="noBook"/>
    <!--Transitions definition-->
    <transitions>
        <transition from="noBook" function="borrowBookPF" to="oneBook"/>
        <transition from="oneBook" function="returnBookPF" to="noBook"/>
        <transition from="noBook" function="canBorrowBookPF" to="noBook" />
        <transition from="oneBook" function="canNotBorrowBookPF" to="oneBook" />
        <transition from="noBook" function="borrowBookNotAvailablePF" to="noBook"/>
        <transition from="oneBook" function="borrowBookCannotBorrowPF" to="oneBook" />
    </transitions>
```

The following snippet describes the dependencies, states and the transitions of the Library JSXM specification.

```
    <dependencies>
        <uses sxm="Book"/>
        <uses sxm="Borrower"/>
    </dependencies>
    <!--States definition-->
    <states>
        <state name="initial"/>
    </states>
    <!--Initial State definition-->
    <initialState state="initial"/>
    <!--Transitions definition-->
    <transitions>
    <!-- SUCCESSFUL SCENARIOS -->
        <transition from="initial" function="borrowBookPF" to="initial"/>
        <transition from="initial" function="returnBookPF" to="initial"/>
    <!-- EXCEPTIONS -->
        <transition from="initial" function="borrowBookNotAvailablePF" to="initial"/>
        <transition from="initial" function="borrowBookCannotBorrowPF" to="initial"/>
    </transitions>
```

*The example contains implementation, specification and the java adapter for all the JSXM specifications.

Download the <a class="btn btn-success" href="../examples-downloads/Book_Borrower.zip"> <span class="icon-download-alt icon-large" style="margin: 0px;"></span>  Book_Borrower</a> Maven project.


[1]: ../examples-downloads/Book_Borrower.zip      "Book_Borrower" 