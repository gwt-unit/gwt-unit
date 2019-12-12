# gwt-unit

**gwt-unit** is based on the great work of Gael Lazzari and his **gwt-test-utils** framework. Because there is no further 
development, we had to create a alternative which is under active development: **gwt-unit**, the next 
generation of GWT unittesting. 

 It provides a simple way to write **fast** Java tests for your GWT client code, **without GWTTestCase** or 
 any servlet container instance! This means you are able to use any Java tool without 
 restriction: JUnit, reflection, Easymock, Mockito, etc.

Writing tests looks like:

```java
@Test
public void clickOnButtonShouldDisplayMessageInLabel() {
  // Arrange
  SampleView view = new SampleView();
  // ensure the label is not visible at init
  assertThat(view.label).isNotVisible();
  
  // Act: simulate a click event
  Browser.click(view.button);
  
  // Assert: label should be visible and filled
  assertThat(view.label).isVisible().textEquals("The button was clicked!");
}
```

If you want to write **fast** tests which will still deal with your GWT view layout and simulate browser events on 
your widgets easily, you really should consider this framework.  

## Features (atm, we support the same feature as gwt-test-utils)

* GWT code unit testing with small execution time (no hosted mode / browser launched in the background)
* Simulation for browser's events (click, blur, change, ...)
* Fluent interface for assertions on widgets, based on [assertj](https://joel-costigliola.github.io/assertj/)
* Mocks handling using [Mockito](http://mockito.org/) or [EasyMock](http://easymock.org/)
* Standard maven-surefire-plugin support for testing with [Maven](http://maven.apache.org/)
* Support for GWT + [Spring](http://www.springsource.org/) application testing
* Support for GWT + [Guice](https://github.com/google/guice) application testing
* Support for GWT + [GIN](http://code.google.com/p/google-gin/) application testing, with [Jukito](https://github.com/ArcBees/Jukito) if wanted
* Support for [JUnitParams](https://github.com/Pragmatists/JUnitParams)
* Complex use-case testing using CSV-based scenarios
* Extensibility through the use of custom patches

## Documentation

**gwt-unit** is GWT 2.8.2 only and we don't intend to support older versions.

Until we managed to write our own documentation, please have a look at 
the **gwt-test-utils** [wiki](https://github.com/gwt-test-utils/gwt-test-utils/wiki).

## Roadmap

Here is a short overview of the features like to work on:

* Support for gxt2, gxt3
* Support for newer Mockito versions, including moving our class generation to ByteBuddy
* Support for JUnit 5
* Support for [RequestFactory](http://www.gwtproject.org/doc/latest/DevGuideRequestFactory.html)
* Support for [PowerMock](https://github.com/jayway/powermock)
* Support for [TestNG](http://testng.org/)

We try to improve **gwt-unit** every day and look forward to get your feedback, ideas and comments. Please use our Github Issue tracker.