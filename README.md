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

To start using spring-integration, take a first look at `build.gradle` and
choose, witch further artifacts of spring-integration you want to enable, by
default, I just enabled core, so you probably want to also enable http, jmx or
mail.

Now take a look at `servlet-config.xml`, here I enabled most namespaces (you
can get rid of the ones you don't want to use). Now this is the file you want
to start to define all spring-beans including the spring-integration beans.

It's easiest, if you install a plugin to your IDE, like STS for eclipse, see
http://spring.io/tools/sts.

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
