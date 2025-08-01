# Regression Scope Analysis Prompt

## **Objective**
Analyze code changes in the latest branch and assess impact on existing regression test cases extracted from Simplify QA. Generate updated regression test recommendations in CSV format.

## **What You Need to Provide**
1. **Latest Branch**: The current code branch with recent changes
2. **Regression Tests Excel**: CSV/Excel file extracted from Simplify QA tool with existing regression test cases

## **⚠️ IMPORTANT - READ ONLY ACCESS**
**This prompt will ONLY READ your code - NO commits, NO code changes, NO modifications will be made!**

**Permissions Required:**
- ✅ **READ ONLY** - View code files and changes
- ✅ **READ ONLY** - Access branch information and file differences  
- ❌ **NO COMMITS** - Will not create any commits
- ❌ **NO CODE CHANGES** - Will not modify any source code
- ❌ **NO FILE MODIFICATIONS** - Will not alter any files

**You have full control - only reading permission granted, nothing more!**

## **How It Works**
- **Compare**: Latest branch changes vs existing regression test coverage
- **Analyze**: Impact on current test cases from Simplify QA
- **Generate**: Updated regression scope in CSV format for SQA import

## **Test Case Structure (From Simplify QA)**
Your existing regression tests from SQA follow this format:
```
LogicalName,Version,Prerequisite,UserStory_Name,Module_Name,Description,Labels,Suite_Name,StepDescription,ExpectedResult,Parameter,qTest Req Reference,Is Automated?
```

## **Template Structure for New/Updated Tests**
When creating new regression tests or updating existing ones, follow this exact structure:

**[TEMPLATE - DO NOT MODIFY COLUMN STRUCTURE]**

| Column Name | Requirement | Instructions |
|-------------|-------------|-------------|
| **LogicalName** | **Mandatory** | A clear and unique test case name that describes the test scenario. If it's positive include P on prefix and N for Negative |
| **Version** | **Mandatory** | Set this as "1" for all test cases |
| **Prerequisite** | Optional | Mention any setup or preconditions required before executing the test. Leave blank if none |
| **UserStory_Name** | Optional | Leave blank |
| **Module_Name** | **Mandatory** | Set this as "test" for all test cases |
| **Description** | Optional | Brief description of the test case purpose and what it validates |
| **Labels** | Optional | Use labels from Jira ticket if available, otherwise leave blank |
| **Suite_Name** | Optional | Leave blank |
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

## **Analysis Process**

### **READ ONLY Analysis - No Code Modifications:**
- **View Code Changes**: Only read files added, modified, or removed in latest branch
- **Read Impact Assessment**: Only analyze how changes affect existing regression tests from SQA
- **Read Test Gap Analysis**: Only identify new functionality needing additional regression tests
- **Read Update Requirements**: Only assess existing tests that need modification

**🔒 SECURITY: This analysis is completely READ ONLY - your code remains untouched!**

### **Output Generated:**
- **Updated Regression Tests**: Modified test cases considering code changes
- **New Test Requirements**: Additional tests needed for new functionality
- **Impact Summary**: Which existing tests are affected and how
- **Priority Recommendations**: Critical vs. lower-priority test updates

## **Simple Usage**

### **What to Provide:**
```
Latest Branch: [Your current code branch with recent changes]
Regression Tests: [CSV/Excel file extracted from Simplify QA tool]
Permission: READ ONLY access to analyze code changes

Please analyze regression scope and generate updated CSV for SQA import.
Note: No commits or code modifications will be made - READ ONLY analysis only!
```

### **What You Get:**
- **Impact Analysis**: Which existing tests are affected
- **Updated Test Cases**: Modified regression tests in CSV format
- **New Test Requirements**: Additional tests needed for new features
- **Priority Report**: Critical vs. lower-priority updates

## **Output Format - [SAMPLE CSV]:**
```csv
LogicalName,Version,Prerequisite,UserStory_Name,Module_Name,Description,Labels,Suite_Name,StepDescription,ExpectedResult,Parameter,qTest Req Reference,Is Automated?
(Mandatory),(Mandatory),,,(Mandatory),,,,(Mandatory),(Mandatory),,,(Mandatory)
P_Updated_Login_Flow,1,User account exists,,test,Login functionality updated due to code changes,High,,1. Navigate to login page,Login page should be displayed,,,No
,,,,,,,,2. Enter valid credentials,Username and password fields should accept the input,,,
,,,,,,,,3. Verify new validation rules,New validation feedback should be shown,,,
,,,,,,,,4. Complete login process,User should be successfully logged in with updated flow,,,
N_Invalid_Login_Data,1,,,test,New validation rules need negative testing,Medium,,1. Navigate to login page,Login page should be displayed,,,No
,,,,,,,,2. Enter invalid credentials,Username and password fields should accept the input,,,
,,,,,,,,3. Submit form,Appropriate error message should be displayed for invalid inputs,,,
P_New_Payment_Feature,1,Payment gateway setup,,test,New payment method added requiring regression test,Critical,,1. Access payment page,Payment options should be displayed,,,No
,,,,,,,,2. Select new payment option,New payment method should be available,,,
,,,,,,,,3. Complete transaction,Payment should be processed successfully,,,
,,,,,,,,4. Verify confirmation,Payment confirmation should be displayed,,,
```

## **Notes:**
- **🔒 READ ONLY**: This prompt only reads your code - NO commits, NO changes, NO modifications
- **User-Friendly**: Just provide latest branch + SQA regression tests
- **Automatic Analysis**: Compares code changes with existing test coverage (READ ONLY)
- **SQA Compatible**: Output format ready for direct import to Simplify QA
- **Priority Focus**: Critical changes highlighted first
- **Safe Analysis**: Your codebase remains completely untouched - only reading permissions used
- **Proper CSV Format**: Uses correct structure with P/N prefixes and proper step formatting
- **Test Case Structure**: First row contains all test info, subsequent rows continue steps only
