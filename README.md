# Cucumber on Spring Boot (Maven)
From a gherkin file (.feature) we will generate in a ATDD (Accepttance Test Driven Development) way the code to test the application.
Cucumber is a tool that helps software development teams to write automated tests in a language that is easy for everyone to understand. It allows the team to focus on the expected behavior of the application and ensure that it works as intended. Think of it as a way to make sure the software does what it's supposed to do, in a language that everyone can understand.

## Example gherking file example.feature
```gherkin
Feature: Example
  Scenario: Example
    Given I have a cucumber spring boot project
    When I run the project
    Then I should see the output
```

# Dependencies pom.xml
```xml
<properties>
    <java.version>17</java.version>
    <cucumber.version>7.5.0</cucumber.version>
</properties>

<dependencies>
    <dependency>
        <groupId>io.cucumber</groupId>
        <artifactId>cucumber-junit</artifactId>
        <version>{cucumber.version}</version>
    </dependency>
    <dependency>
        <groupId>io.cucumber</groupId>
        <artifactId>cucumber-java</artifactId>
        <version>{cucumber.version}</version>
    </dependency>
    <dependency>
        <groupId>io.cucumber</groupId>
        <artifactId>cucumber-spring</artifactId>
        <version>{cucumber.version}</version>
    </dependency>
</dependencies>
```