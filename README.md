spring-integration-base
=======================

When I started looking at spring-integration, I had troubles getting a simple
setup. So here's my result, feel free to use it, and if you have a idea, please
provide updates.

This setup does use gradle, but it's easy to adapt to maven.

Setup
-----

The following files are in the project:

    README.md                                    this Readme
    build.gradle                                 gradle-configuration
    src/main/webapp/WEB-INF/servlet-config.xml   spring-integration configuration
    src/main/webapp/WEB-INF/web.xml              web-container configuration

To start using spring-integration, change `servlet-config.xml` (perhaps I
should rename it to integration-config.xml).


Build
-----

Run `gradle build` to build and test the whole project:

    rjung:~/spring-integration-base$ gradle build
    :compileJava UP-TO-DATE
    :processResources
    :classes
    :war
    :assemble
    :compileTestJava UP-TO-DATE
    :processTestResources
    :testClasses
    :test
    :check
    :build
    
    BUILD SUCCESSFUL
    
    Total time: 6.211 secs
    rjung:~/spring-integration-base$

Using `gradle jettyRun` you can directly run the code locally with jetty, stop
it with Ctrl-C:

    rjung:~/Projects/spring-integration-base[master*]$ gradle jettyRun
    :compileJava UP-TO-DATE
    :processResources UP-TO-DATE
    :classes UP-TO-DATE
    > Building > :jettyRun > Running at http://localhost:8080/spring-integration-base

See further tasks by running `gradle tasks`.
