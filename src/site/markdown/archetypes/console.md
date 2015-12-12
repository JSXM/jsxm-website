### Interactive Console Usage

The archetype can be used by invoking archetype:generate in interactive mode and selecting 
the number that corresponds to desired archetype. The exact maven call is:

    mvn archetype:generate -DarchetypeCatalog=http://www.jsxm.org/maven2/
    
After selecting the archetype, groupId, artifactId, version and package
must be provided in order to create the maven project.  
    

### Batch Console Usage

Skipping interactive mode by calling Maven with the following command

    mvn -DarchetypeGroupId=org.jsxm.archetypes 
        -DarchetypeArtifactId=jsxm-example-archetype 
        -DarchetypeVersion=1.3 
        -DarchetypeRepository=http://www.jsxm.org/maven2/ 
        -DgroupId={your group id} 
        -DartifactId={your artifact id} 
        -Dversion={your version} 
        -Dpackage={your package} 
        -Dbasedir={your base directory} 
        -Darchetype.interactive=false 
        --batch-mode archetype:generate