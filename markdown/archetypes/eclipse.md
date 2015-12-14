    
### Eclipse

#### Adding Archetype Catalog

(Preferences->Maven->Archetypes->Add Remote Catalog)

Navigate to the Preferences pane, expand Maven, locate Archetypes submenu.

![alt text](../images/prefCatalog.png "Eclipse Remote Catalog Menu")

Select Add Remote Catalog

![alt text](../images/addNewCatalog.png "Add remote catalog")

Enter the following info in the Maven Archetype Interface

    Catalog File: http://www.jsxm.org/maven2/archetype-catalog.xml
    Description: JSXM Archetypes
    
![alt text](../images/addNewCatalog2.png "Add remote catalog JSXM")
 
Click verify to see that all 3 archetypes are available.   

After adding the archetype catalog in Eclipse the archetypes will be available 
when creating new Maven Projects.

#### Create a maven project based on JSXM example archetype 

Select File -> New -> Other -> Maven Project -> Next

 ![alt text](../images/newMaven.png "New Maven Project")
 
*Make sure that "Create a simple project(slip archetype selection)" is unselected 

Select JSXM Archetypes from the catalog drop down menu or add "jsxm" keyword in the filter input
and select jsxm-example-archetype.

 ![alt text](../images/newMaven3.png "JSXM Example Archetype ")

Select Next, provide your desired group and artifact id and click Finish.
 
![alt text](../images/newMaven5.png "JSXM Artifact id/Group id wizard ")

Locate the pom.xml of the created project, locate the jsxm-maven-plugin inside the build element 
and make sure that you comment/uncomment the right section depending on your operating system.

```
<plugin>
    <groupId>org.jsxm.maven.plugin</groupId>
    <artifactId>jsxm-maven-plugin</artifactId>
    <version>1.4.11-RC4</version>
    <configuration>
        <jsxmList>
            <!-- Unix Paths -->
            <param>org/jsxm/examples/SampleProject</param>
            <!-- Windows Paths -->
            <!-- <param>org\jsxm\examples${artifactId}</param> -->
         </jsxmList>
     </configuration>
</plugin>
```
Use 

    mvn jsxm:create-sample
  
and a JSXM example will be created inside the spec src/spec folder.

The above example contains all the necessary information to trigger any 
of the available [JSXM goals][1].

[1]: ../plugin-info.html        "JSXM goals"     
