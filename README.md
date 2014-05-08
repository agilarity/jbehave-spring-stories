[![Stories in Ready](https://badge.waffle.io/agilarity/jbehave-spring-stories.png?label=ready&title=Ready)](https://waffle.io/agilarity/jbehave-spring-stories)
[![Build Status](https://travis-ci.org/agilarity/jbehave-spring-stories.svg?branch=master)](https://travis-ci.org/agilarity/jbehave-spring-stories)

This project provides a useful base class for running [JBehave](http://jbehave.org/reference/stable/) test scenarios with injected steps using [Spring](http://spring.io/).

### Usage:
1 - Add a Spring annotated resource class.
```java
@Configuration
@ComponentScan("com.agilarity.examples.smoke.steps")
public class SmokeTestResources {

}
```
2 - Specify the resource in your test class.
```java
    public class SmokeTest extends SpringJBehaveStories {
    
        @Override
        protected String[] getSpringResources() {
            return new String[] { SmokeTestResources.class.getName() };
        }
    }
```
3 - Put your story files under <tt>src/test/resources</tt>, at or below the same package as your test class.

4 - Run your test class as a normal [JUnit](http://junit.org/) test.