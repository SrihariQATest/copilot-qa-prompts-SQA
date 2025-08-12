# `Jira Ticket to TestCase Generation`

## Objective

Generate high-quality manual test cases and export them to a CSV file using the below format for the respective Jira Ticket. The agent will automatically analyze the Jira ticket content to determine the appropriate test type and adapt the test case format accordingly.

## **Template Structure**

The CSV file must follow this exact structure with the following columns:

**[TEMPLATE - DO NOT MODIFY COLUMN STRUCTURE - REQUIRED FOR SQA IMPORT]**

| Column Name | Requirement | Instructions |
|-------------|-------------|-------------|
| **LogicalName** | **Mandatory** | A clear and unique test case name that describes the test scenario. Format adapts based on test type: "API_Verify [Jira Ticket ID] [method] [condition]" for API tests, "DB_Test [Jira Ticket ID] [operation] [condition]" for database tests, "Verify [Jira Ticket ID] [functionality] [condition]" for functional tests. Examples: "API_Verify TICKET-123 POST with valid credentials", "DB_Test TICKET-123 user insertion with valid data", "Verify TICKET-123 login functionality with valid credentials"|
| **Version** | **Mandatory** | Set this as "1" for all test cases |
| **Prerequisite** | Optional | Extract setup requirements from Jira ticket description, acceptance criteria, and requirements. Include environment setup, test data, user accounts, or specific configurations needed |
| **UserStory_Name** | Optional | Leave blank |
| **Module_Name** | **Mandatory** | **IMPORTANT**: Use the module name provided by the user. If no module is specified, ask: "Can I proceed with creating test cases using 'test' as the module name, or would you prefer to specify a different module name?" |
| **Description** | Optional | Brief description of the test case purpose and what it validates |
| **Labels** | Optional | Use labels from Jira ticket if available, otherwise leave blank |
| **Suite_Name** |  Optional | Leave blank |
| **StepDescription** | **Mandatory** | Clear, actionable test steps. Format adapts to test type - API steps include HTTP requests, DB steps include SQL operations, Functional steps include UI interactions |
| **ExpectedResult** | **Mandatory** | The expected result for each corresponding test step |
| **Parameter** | Optional | Include relevant parameters based on test type - API parameters, SQL queries, test data, etc. |
| **qTest Req Reference** | Optional | Leave blank |
| **Is Automated?** | **Mandatory** | Set this as "No" for all manual test cases |

## **CSV Format Requirements**

### **Row 1 (Headers) - [TEMPLATE]:**

```text
LogicalName,Version,Prerequisite,UserStory_Name,Module_Name,Description,Labels,Suite_Name,StepDescription,ExpectedResult,Parameter,qTest Req Reference,Is Automated?
```

### **Row 2 (Field Requirements) - [TEMPLATE]:**

```text
(Mandatory),(Mandatory),,,(Mandatory),,,,(Mandatory),(Mandatory),,,(Mandatory)
```

### **Row 3 onwards (Test Case Data) - [YOUR TEST CASES]:**

- **First row of each test case**: Fill all applicable fields including LogicalName, Version, Module_Name, Description, etc.
- **Subsequent rows for same test case**: Leave most fields blank except StepDescription and ExpectedResult to continue the test steps

## Intelligent Test Case Creation Guidelines

### Quality Standards

- **Create only high-quality test cases** - Focus on the most critical scenarios that provide maximum coverage
- **Skip unnecessary testing** - Do not include cross-browser testing, performance testing, or security testing scenarios unless specifically mentioned in the ticket
- **Adapt to test type** - Automatically detect test type from Jira ticket content and adapt test case format accordingly:
  - **API Testing**: Focus on endpoints, HTTP methods, request/response validation
  - **Database Testing**: Focus on CRUD operations, data integrity, constraints
  - **Functional Testing**: Focus on user workflows, business logic, UI interactions
  - **Performance Testing**: Focus on load conditions, response times, scalability
- **Focus on functional requirements** - Base test cases on core functionality and user workflows specified in the ticket
- **Ensure acceptance criteria coverage** - Prioritize test cases that directly validate the acceptance criteria and main functionality
- **Extract prerequisites from Jira ticket** - Analyze the Jira ticket description, acceptance criteria, and requirements to identify any setup conditions, preconditions, or dependencies needed before executing test cases. Fill the Prerequisites field with relevant information from the ticket itself
- **Module name validation** - Always confirm the module name with the user if not explicitly provided

### Intelligent Test Step Format

- **API Tests**: Include HTTP method, endpoint, headers, request body, and response validation
- **Database Tests**: Include SQL operations, data setup, integrity checks, and result validation  
- **Functional Tests**: Include UI navigation, data entry, user interactions, and workflow validation
- **Performance Tests**: Include load parameters, monitoring points, and performance criteria
- Write clear, actionable steps that any tester can follow
- Each step should have a corresponding expected result
- Be specific about elements, data inputs, and expected outcomes

### Smart Naming Convention

- **API Tests**: "API_Verify [endpoint] [HTTP method] [condition]" or "API_Test [functionality] with [scenario]"
- **Database Tests**: "DB_Verify [operation] [table/entity] [condition]" or "DB_Test [functionality] with [scenario]"
- **Functional Tests**: "Verify [functionality] [condition]" or "Test [feature] with [scenario]"
- **Performance Tests**: "PERF_Test [functionality] [load condition]" or "PERF_Verify [metric] [scenario]"
- **Examples:** 
  - "API_Verify user login POST with valid credentials"
  - "DB_Test user insertion with valid data"
  - "Verify login functionality with valid credentials"
  - "PERF_Test login under normal load"

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

1. **Analyze the provided Jira ticket thoroughly** - Read the main ticket details, description, and acceptance criteria
2. **Check for linked/cloned tickets** - Identify any related tickets (cloned from, linked to, parent/child relationships) and analyze their requirements to understand the complete context
3. **Review related ticket details** - If linked tickets exist, read their descriptions, acceptance criteria, and requirements to gain comprehensive understanding of the feature scope
4. **Identify core testable functionalities** - Focus only on the most critical 2-3 scenarios that validate the main functionality
5. **Create focused test cases** - Generate only high-value test cases that cover the primary acceptance criteria
6. **Export to CSV file** - Follow the exact template format with all mandatory fields populated
7. **Validate test case quality** - Ensure each test case provides real testing value and is independently executable

### **Usage Template Example:**

```text
Please generate 2-3 focused test cases for:
JIRA Ticket: [TICKET-ID]
Feature: [Feature Name]
Test Type: [API/Database/Functional/Performance - if specific, otherwise will auto-detect]
Module Name: [Specify module name for SQA import - if not provided, will ask for confirmation]
Acceptance Criteria: [Copy acceptance criteria from JIRA]
Linked/Cloned Tickets: [List any related ticket IDs if present]

Requirements:
- Generate only 2-3 high-quality test cases focusing on core functionality
- Auto-adapt test format based on ticket content and test type
- Skip cross-browser, performance, and security testing unless specifically mentioned
- Analyze any linked/cloned tickets for complete context
- Focus on acceptance criteria validation

Generate CSV output in the TestcaseTemplate.csv format for SQA import.
```

### **Module Name Validation:**

If no module name is provided in the request, I will ask:
"Can I proceed with creating test cases using 'test' as the module name, or would you prefer to specify a different module name for better organization in SQA?"

## **Notes:**

- **SQA Template Compliance**: Maintain strict consistency with the TestcaseTemplate.csv structure - DO NOT modify column structure as it's required for SQA import
- **Intelligent Adaptation**: Automatically adapts test case format, naming, and content based on detected test type (API, Database, Functional, Performance)
- **Module Name Validation**: Always confirm module name with user if not provided - essential for proper SQA organization
- **Focused Testing**: Generate only 1-2 focused test cases per ticket to avoid redundancy
- **Independent Execution**: Each test case should be independent and executable
- **Context Analysis**: Always check for linked/cloned tickets to understand complete feature context
- **Scope Management**: Exclude cross-browser compatibility, performance, and security testing scenarios unless specifically mentioned in the ticket
- **Quality Focus**: Prioritize acceptance criteria validation and main user workflows over edge cases
