# Key Impact Analyzer for Simplify QA

## Objective
Analyze the impact of latest code changes by comparing new code with existing regression test cases. Generate impacted regions analysis and identify new test cases that need to be added in CSV format for Simplify QA (SQA) execution.

## Prerequisites
- Access to cloned repository with latest code changes
- Existing regression test cases exported from SQA in CSV/XLSX format
- Understanding of application architecture and component relationships
- Knowledge of Simplify QA (SQA) test management capabilities

## Essential Requirements for SQA Integration
1. **Cloned Repository**: Local copy of repository with latest code changes
2. **Existing Test Suite**: Test cases exported from SQA in CSV or XLSX format
3. **SQA Environment**: Access to Simplify QA tool for test case import and execution
4. **Change Documentation**: Basic understanding of what changes were made

## **Input Requirements**

### **Code Repository - [YOUR INPUT]:**
```
Cloned Repository Path: [Local path to cloned repository]
Branch with Changes: [Branch name with latest changes]
Changed Files: [List of modified files or commit details]
```

### **Existing Test Cases from SQA - [YOUR INPUT]:**
```
File Format: CSV or XLSX exported from SQA
File Path: [Path to exported test cases file]
Test Suite Name: [Name of the test suite]
Total Test Cases: [Number of existing tests]
```

## Impact Analysis Framework

### Change Impact Levels
- **Critical**: Authentication, Payment, Security, Database schema
- **High**: New features, UI changes, Business logic, API changes
- **Medium**: Bug fixes, Code refactoring, Configuration updates
- **Low**: Documentation, Comments, Formatting changes

## **CSV Output Format for SQA**

### **Impact Analysis Output - [TEMPLATE]:**
| ImpactArea | ImpactLevel | ChangeType | ChangedFiles | TestCasesAffected | RiskAssessment | RecommendedAction |
|------------|-------------|------------|--------------|-------------------|----------------|-------------------|
| Authentication | High | New Feature | auth.js, login.tsx | 15 | High Risk | Full regression + New tests |

### **New Test Cases Required - [YOUR OUTPUT]:**
| LogicalName | Version | Prerequisite | UserStory_Name | Module_Name | Description | Labels | Suite_Name | StepDescription | ExpectedResult | Parameter | qTest Req Reference | Is Automated? |
|-------------|---------|--------------|----------------|-------------|-------------|--------|------------|-----------------|----------------|-----------|-------------------|---------------|
| IMPACT_Auth_NewFeature_Test | 1 | Setup requirements | US-123 | Authentication | Test new auth feature | Impact;NewFeature | AuthImpact | 1. Test step description | Expected result | Test data | | Yes |

## Usage Instructions for SQA

1. **Provide Repository**: Share the cloned repository path with latest changes
2. **Upload Test Cases**: Provide CSV/XLSX file exported from SQA with existing test cases
3. **Analyze Impact**: Tool will generate impact analysis and affected areas
4. **Review Output**: Examine impact analysis and new test case recommendations
5. **Import to SQA**: Use generated CSV to import new tests into SQA
6. **Execute Tests**: Run impact-based testing in SQA environment

## **Example Input Format - [USAGE TEMPLATE]**

### **Repository Information - [EXAMPLE]:**
```
Repository Path: C:\Projects\MyApp
Changed Branch: feature/user-authentication
Modified Files: 
- src/auth/loginService.js
- src/components/LoginForm.tsx
- database/migrations/add_mfa.sql
```

### **SQA Test Export - [EXAMPLE]:**
```
File: existing_tests.csv (exported from SQA)
Columns: LogicalName, Module_Name, Description, StepDescription, ExpectedResult
Test Count: 150 existing test cases
Coverage: Authentication, User Management, Payment Processing
```

## SQA Integration Benefits
- Quick impact assessment based on code changes
- Automatic identification of affected test areas
- New test case generation in SQA-compatible format
- Risk-based testing recommendations
- Direct CSV import into SQA test management
