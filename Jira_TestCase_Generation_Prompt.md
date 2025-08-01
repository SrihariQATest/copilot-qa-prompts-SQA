# Jira Ticket to Test Cases Generation Prompt

## Objective
Generate high-quality manual test cases and export them to a CSV file using the TestcaseTemplate.csv format.

## **Template Structure**
The CSV file must follow this exact structure with the following columns:

**[TEMPLATE - DO NOT MODIFY COLUMN STRUCTURE]**

| Column Name | Requirement | Instructions |
|-------------|-------------|-------------|
| **LogicalName** | **Mandatory** | A clear and unique test case name that describes the test scenario if its postive inculde P on prefix and N for Negative|
| **Version** | **Mandatory** | Set this as "1" for all test cases |
| **Prerequisite** | Optional | Mention any setup or preconditions required before executing the test. Leave blank if none |
| **UserStory_Name** | Optional | Leave blank |
| **Module_Name** | **Mandatory** | Set this as "test" for all test cases |
| **Description** | Optional | Brief description of the test case purpose and what it validates |
| **Labels** | Optional | Use labels from Jira ticket if available, otherwise leave blank |
| **Suite_Name** |  Optional | Leave blank |
| **StepDescription** | **Mandatory** | Clear, actionable test steps. Format as: "1. Step description" for first step, then continue with "2. Next step description" in subsequent rows |
| **ExpectedResult** | **Mandatory** | The expected result for each corresponding test step |
| **Parameter** | Optional | Leave blank unless specific parameters are required for the test |
| **qTest Req Reference** | Optional | Leave blank |
| **Is Automated?** | **Mandatory** | Set this as "No" for all manual test cases |

## **CSV Format Requirements**

### **Row 1 (Headers) - [TEMPLATE]:**
```
LogicalName,Version,Prerequisite,UserStory_Name,Module_Name,Description,Labels,Suite_Name,StepDescription,ExpectedResult,Parameter,qTest Req Reference,Is Automated?
```

### **Row 2 (Field Requirements) - [TEMPLATE]:**
```
(Mandatory),(Mandatory),,,(Mandatory),,,,(Mandatory),(Mandatory),,,(Mandatory)
```

### **Row 3 onwards (Test Case Data) - [YOUR TEST CASES]:**
- **First row of each test case**: Fill all applicable fields including LogicalName, Version, Module_Name, Description, etc.
- **Subsequent rows for same test case**: Leave most fields blank except StepDescription and ExpectedResult to continue the test steps

## Test Case Creation Guidelines

### Quality Standards:
- **Create only valuable test cases** - Skip vague, redundant, or duplicate scenarios
- **Focus on real-world usage** - Base test cases on actual user workflows and business requirements
- **Ensure comprehensive coverage** - It Should Satisfy the Acceptance Criteria, Securtiy standards, performance , Include positive, negative, and edge case scenarios and the acceptance criteria, the scope, and the functionality where applicable

### Test Step Format:
- Write clear, actionable steps that any tester can follow
- Each step should have a corresponding expected result
- Be specific about UI elements, data inputs, and user actions

### Naming Convention:
- LogicalName should be descriptive and unique
- Format: "Verify [functionality] when [condition]" or "Test [feature] with [scenario]"
- **Examples:** "Verify login functionality with valid credentials", "Test file upload with invalid file format"

## **Example Output Format - [SAMPLE CSV]:**
```csv
LogicalName,Version,Prerequisite,UserStory_Name,Module_Name,Description,Labels,Suite_Name,StepDescription,ExpectedResult,Parameter,qTest Req Reference,Is Automated?
(Mandatory),(Mandatory),,,(Mandatory),,,,(Mandatory),(Mandatory),,,(Mandatory)
Verify user login with valid credentials,1,User account exists in system,,test,Validate successful login process with correct credentials,,,1. Navigate to login page,Login page should be displayed,,,No
,,,,,,,,2. Enter valid username and password,Username and password fields should accept the input,,,
,,,,,,,,3. Click on Login button,User should be successfully logged in and redirected to dashboard,,,
Verify error handling for invalid login,1,,,test,Validate error message display for incorrect credentials,,,1. Navigate to login page,Login page should be displayed,,,No
,,,,,,,,2. Enter invalid username and password,Username and password fields should accept the input,,,
,,,,,,,,3. Click on Login button,Error message should be displayed indicating invalid credentials,,,
```

## **Instructions for Use:**
1. Analyze the provided Jira ticket thoroughly
2. Identify all testable functionalities and scenarios
3. Create comprehensive test cases covering the requirements
4. Export to CSV file following the exact template format
5. Ensure all mandatory fields are populated appropriately
6. Validate that test cases provide real testing value

### **Usage Template Example:**
```
Please generate test cases for:
JIRA Ticket: [TICKET-ID]
Feature: [Feature Name]
Acceptance Criteria: [Copy acceptance criteria from JIRA]

Generate CSV output in the TestcaseTemplate.csv format for SQA import.
```

## **Notes:**
- Maintain consistency with the TestcaseTemplate.csv structure
- Each test case should be independent and executable
- Include both happy path and error scenarios where relevant
- Ensure test steps are detailed enough for manual execution
