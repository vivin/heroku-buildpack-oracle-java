Heroku buildpack: Oracle JDK
============================

This is a Heroku buildpack for Java applications that use Maven as build tool.
The buildpack installs Oracle JDK 1.8.0_05 and Maven 3.2.1 by default. This 
buildpack has been modified from the trautonen's original buildback to remove 
support for JCE and Ruby gems.

**Oracle License Agreement**  
By using this buildpack you must agree the Oracle Binary Code License
Agreement for the Java SE Platform Products and JavaFX.  
http://www.oracle.com/technetwork/java/javase/terms/license/index.html

Usage
-----

    $ ls
    Procfile  pom.xml  src

    $ heroku apps:create example --buildpack https://github.com/vivin/heroku-buildpack-oracle-java

    $ git push heroku master
    ...
    -----> Fetching custom git buildpack... done
    -----> Java app detected
    -----> Installing wget... version 1.15 installed
    -----> Installing JDK... version 1.8.0_05 installed
    -----> Installing Maven... version 3.2.1 installed
    -----> Executing build...
           mvn -B -Duser.home=/tmp/build_2be971b4-90c0-48d4-8045-8ef1b5521352 -Dmaven.repo.local=/app/tmp/cache/.m2/repository -DskipTests=true -U clean install

The buildpack will detect `pom.xml` in the project root folder and executes
maven with `clean` and  `install` goals to create the executable.


License
-------

Licensed under the MIT License. See LICENSE.MIT file.
