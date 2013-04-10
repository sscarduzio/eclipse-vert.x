Notes on Eclipse integration for Vert.x 1.3.x
==============

This is how you're getting your Vert.x Java code to run and debug into Eclipse IDE.

1. create a conf folder in your project, and put there the [langs.properties](https://raw.github.com/vert-x/vert.x/v1.3.1.final/src/dist/conf/langs.properties) file vertx needs to startup. 
![adding conf folder](https://raw.github.com/sscarduzio/eclipse-vert.x/master/pics/conf_langs.properties.png)

2. In maven, add vertx-lang-java dependency to your pom.xml. If you are not using maven or other build tools, just add a user library with all the jars that come with Vert.x distribution.
![adding maven dependency](https://raw.github.com/sscarduzio/eclipse-vert.x/master/pics/mavenDep.png)

3. Then go to debug configurations and fill in the Main class as "org.vertx.java.deploy.impl.cli.Starter"
 ![main class](https://raw.github.com/sscarduzio/eclipse-vert.x/master/pics/MainClass.png)

4. Setup the program arguments to something similar to what you would run to command line:
``` run com.example.MainVerticle -conf ${project_loc:/VertxProject}/configuration.json -cp ${project_loc:/VertxProject}/target/classes:/path/to/optional/other/jars"``` 
And if you are not using JUL logging, add to the VM arguments the logging handler of you choice.
 ![main class](https://raw.github.com/sscarduzio/eclipse-vert.x/master/pics/Arguments.png)
