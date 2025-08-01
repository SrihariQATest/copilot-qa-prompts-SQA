# Copilot Prompt Packs for Simplify QA (SQA)

A specialized collection of GitHub Copilot prompts designed specifically for Simplify QA (SQA) testing tool integration. These prompts generate test cases, analysis reports, and documentation in CSV format optimized for direct import and execution within the SQA platform.

## Prerequisites

Before using these prompt packs, ensure you have access to the following:

### Required Access & Tools
- **GitHub Copilot Access**: Active GitHub Copilot subscription and proper configuration in your IDE
- **Simplify QA (SQA) Access**: Valid SQA account with appropriate permissions to:
  - Import and manage test cases
  - Execute automated and manual tests
  - Access API, UI, and Database testing modules
  - Generate reports and analytics
- **JIRA Access**: Valid JIRA account with appropriate permissions to:
  - Read tickets and user stories
  - Access project configurations and workflows
  - View attachments and requirements documentation

### General Requirements
- Basic understanding of testing methodologies compatible with SQA
- Familiarity with CSV format for test case management
- Knowledge of your application's business domain and workflows
- Understanding of SQA's automation capabilities and limitations

## Available Prompt Packs

### 1. **JIRA TestCase Generation Prompt** (`Jira_TestCase_Generation_Prompt.md`)
**Purpose**: Generate comprehensive test cases from JIRA tickets and export them to CSV format compatible with SQA. Automatically adapts to generate API test cases when the JIRA ticket is about API functionality.
**Essential Requirements**:
- JIRA ticket access with detailed acceptance criteria
- Understanding of SQA CSV template structure for test case management
- Knowledge of positive/negative testing scenarios
- SQA test case import functionality

### 2. **Key Impact Analyzer Prompt** (`Key_Impact_Analyzer_Prompt.md`)
**Purpose**: Analyze code changes impact by comparing latest release branch with existing regression test cases, generating new test requirements for SQA.
**Essential Requirements**:
- Access to latest release branch and code change documentation
- Existing regression test suite in CSV or SQA format
- Understanding of SQA impact analysis and test case management
- Knowledge of application architecture and component dependencies

### 3. **UI Object Extractor Prompt** (`UI_Object_Extractor_Prompt.md`)
**Purpose**: Extract UI elements and their properties (XPath, CSS selectors) in CSV format for new pages or enhanced features based on JIRA tickets and latest code.

**⚠️ IMPORTANT - Web Recorder Priority**: 
**Before using this Object Extractor prompt, always try Web Recorder first!** Web Recorder is much more efficient and should be your **primary method** for UI element extraction because:
- **Higher Accuracy**: Records actual browser interactions for precise element identification
- **Faster Extraction**: Automated capture vs manual coding
- **Multiple Attributes**: Automatically captures XPath, ID, CSS, class, text, and accessibility attributes
- **Real-time Validation**: Tests elements during recording for reliability
- **No Technical Expertise Required**: Point-and-click interface, no coding needed

**Use the Object Extractor prompt only when**:
- Web Recorder tool is not available
- Complex scenarios require manual analysis
- Code-level element extraction is needed

**Essential Requirements**:
- **Priority 1**: SQA Web Recorder tool access (recommended primary method)
- JIRA ticket details for new pages or feature enhancements
- Access to latest code repository with UI implementations (for manual extraction)
- SQA UI automation module and object repository access
- Understanding of DOM structure and element identification strategies

### 4. **Regression Scope Analysis Prompt** (`Regression_Scope_Prompt.md`)
**Purpose**: Analyze code changes in the latest branch and assess impact on existing regression test cases extracted from Simplify QA tool.

**🔒 READ ONLY ACCESS**: This prompt only reads your code - NO commits, NO changes, NO modifications will be made!

**⚠️ IMPORTANT - Default Naming Conventions:**
Before using this prompt, review and update the naming conventions if needed:
- **Module_Name**: Currently set to "test" for all test cases - change if your project uses different module names
- **Test Case Naming**: Uses "P_" prefix for positive tests and "N_" prefix for negative tests - modify if your organization uses different conventions

**What You Need:**
- **Latest Branch**: Your current code branch with recent changes
- **Regression Tests**: CSV/Excel file extracted from Simplify QA tool

**What It Does:**
- **Reads**: Latest code changes with existing regression test coverage (READ ONLY)
- **Analyzes**: Impact on current test cases from Simplify QA (READ ONLY)
- **Generates**: Updated regression scope in CSV format for SQA import
- **Prioritizes**: Critical vs. lower-priority test updates

**Essential Requirements**:
- READ ONLY access to latest code branch with recent changes
- Existing regression test cases exported from Simplify QA tool
- Understanding of code change impact on test coverage

## Why Use These Prompts?

- **Ready for SQA**: All outputs are in CSV format for direct SQA import
- **Save Time**: Automated test generation reduces manual work
- **Consistent Format**: Standardized structure across all test types
- **Easy Integration**: Seamless workflow with SQA platform

## 🎯 UI Element Extraction Priority

**For UI Object Extraction, always follow this order:**

1. **FIRST: Web Recorder** ⭐ (Much faster and more accurate)
2. **SECOND: Object Extractor Prompt** (Only when Web Recorder unavailable)

## Simple Workflow

1. **Choose your prompt** based on what you need (test cases, UI elements, or impact analysis)
2. **Gather your inputs** (JIRA tickets, code info, etc.)
3. **Copy the prompt** into GitHub Copilot Chat
4. **Provide context** and generate CSV output
5. **Import to SQA** and run your tests

## SQA Integration

### Test Management
- Import CSV files directly into SQA
- Organize by module and priority
- Track test results and reports

## Best Practices for SQA Integration

### **UI Element Extraction Best Practices**
- **Always use Web Recorder first** - It's significantly more efficient than manual extraction
- **Web Recorder captures more attributes** - Automatically records multiple locator strategies
- **Faster turnaround time** - Point-and-click vs manual coding and analysis
- **Higher reliability** - Real-time validation during element capture
- **Reserve Object Extractor prompt for special cases** - Complex scenarios or when Web Recorder unavailable

### Test Case Quality
- Review generated test cases for SQA compatibility
- Validate test data requirements and availability
- Ensure test cases are independent and executable in SQA
- Maintain consistent naming conventions across test suites

### Data Management
- Prepare test data suitable for SQA execution
- Ensure data privacy and security compliance
- Maintain test data freshness and relevance

## How to Use These Prompts

1. **Select the appropriate prompt** based on your testing needs
2. **Copy the prompt content** into GitHub Copilot Chat 
3. **Provide the necessary context** (JIRA tickets, code changes, requirements, etc.)
4. **Generate CSV output** formatted for SQA import
5. **Import into SQA** and execute your tests

### **Example Usage:**
```
I need to generate test cases for:
- JIRA Ticket: TICKET-123
- Feature: User Login Page

Please generate CSV output for SQA import.
```

### **For Regression Scope Analysis:**
```
I need regression scope analysis for:
- Latest Branch: feature/user-management-v2.1
- Regression Tests: [Upload CSV from Simplify QA tool]
- Permission: READ ONLY access (no commits, no code changes)

Please analyze impact and generate updated CSV for SQA import.
```

## Quick Tips

- **For UI Elements**: Always try Web Recorder first - it's much faster and more accurate
- **Review generated content** for accuracy before importing to SQA
- **Customize prompts** based on your organization's needs
- **Keep prompts updated** based on lessons learned

## Support

For issues or improvements, please refer to the project's contribution guidelines.
