[![Stories in Ready](https://badge.waffle.io/agilarity/jbehave-spring-stories.png?label=ready&title=Ready)](https://waffle.io/agilarity/jbehave-spring-stories)
[![Build Status](https://travis-ci.org/agilarity/jbehave-spring-stories.svg?branch=master)](https://travis-ci.org/agilarity/jbehave-spring-stories)

This project provides a useful base class for running [JBehave](http://jbehave.org/reference/stable/) test scenarios with injected steps using [Spring](http://spring.io/).

### Usage:
1 - Add dependency.
```xml
<dependency>
    <groupId>com.agilarity</groupId>
    <artifactId>jbehave-spring-stories</artifactId>
    <version>1.0.3</version>
</dependency>
```
2 - Add a Spring annotated resource class.
```java
@Configuration
@ComponentScan("com.agilarity.examples.smoke.steps")
public class SmokeTestResources {

}
```
3 - Specify the resource in your test class.
```java
    public class SmokeTest extends SpringJBehaveStories {
    
        @Override
        protected String[] getSpringResources() {
            return new String[] { SmokeTestResources.class.getName() };
        }
    }
```
4 - Add the <tt>@Component</tt> annotation to you steps so Spring will wire it up.

5 - Put your story files under <tt>src/test/resources</tt>, at or below the same package as your test class.

6 - Run your test class as a normal [JUnit](http://junit.org/) test.