# Cucumber on Spring Boot (Maven)
From a gherkin file (.feature) we will generate in a ATDD (Accepttance Test Driven Development) way the code to test the application.
Cucumber is a tool that helps software development teams to write automated tests in a language that is easy for everyone to understand. It allows the team to focus on the expected behavior of the application and ensure that it works as intended. Think of it as a way to make sure the software does what it's supposed to do, in a language that everyone can understand.

## Example gherkin file _login.feature_
```gherkin
Feature: Login
  As a registered user
  I want to log in to my account
  So that I can access my profile

  Background:
    Given I am on the login page

  Scenario: Successful login
    When I enter valid credentials
    And I click the login button
    Then I should be redirected to my profile page

  Scenario: Invalid login
    When I enter invalid credentials
    And I click the login button
    Then I should see an error message
    And I should remain on the login page

  Scenario Outline: Forgot password
    When I click the forgot password link
    And I enter my email "<email>"
    And I click the submit button
    Then I should see a success message

    Examples:
      | email                 |
      | john.doe@example.com  |
      | jane.doe@example.com  |

  Scenario Template: Change password
    Given I am on my profile page
    When I click the change password link
    And I enter my current password "<current_password>"
    And I enter my new password "<new_password>"
    And I confirm my new password "<new_password>"
    And I click the save button
    Then I should see a success message

    Examples:
      | current_password | new_password |
      | password123      | newpassword  |
      | secret           | mysecretpass |

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

