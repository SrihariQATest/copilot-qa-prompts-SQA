# 🔍 Release Branch Impact Analyzer for Simplify QA

## 📋 Objective
Compare two release branches to analyze code changes and their impact on existing regression test cases. Generate comprehensive impact analysis and identify new test cases required for Simplify QA (SQA) execution.

## 🎯 What This Tool Does
- **Compares two release branches** to identify code differences
- **Analyzes impact** on existing regression test coverage
- **Generates new test cases** in SQA-compatible CSV format
- **Provides risk assessment** and testing recommendations
- **Creates actionable reports** for QA teams

## 📁 User-Friendly Input Guide

### **Step 1: Provide Your Branch Information**
When using this analyzer, simply provide the following information in your chat:

```
Branch 1 (Base/Previous Release): [Folder Name]
Branch 2 (New/Current Release): [Folder Name] 
Regression Test File: [CSV File Name]
```

**Example:**
```
Branch 1: Release_V2.1_Branch
Branch 2: Release_V2.2_Branch  
Regression Test File: Regression_AT_Test_Pack.csv
```

### **Step 2: What You Need to Prepare**
1. **Two Release Branch Folders** - Clone both release branches into your workspace
2. **Regression Test CSV File** - Export your existing test cases from SQA as CSV
3. **This Prompt File** - Keep this .md file in your workspace
## 🔒 **IMPORTANT - READ ONLY ACCESS**
**This analyzer will ONLY READ your code - NO commits, NO code changes, NO modifications will be made!**

**Permissions Required:**
- ✅ **READ ONLY** - View code files and analyze changes between branches
- ✅ **READ ONLY** - Access branch information and file differences  
- ✅ **READ ONLY** - Compare regression test coverage
- ❌ **NO COMMITS** - Will not create any commits
- ❌ **NO CODE CHANGES** - Will not modify any source code
- ❌ **NO FILE MODIFICATIONS** - Will not alter any files

**You have full control - only reading permission granted for analysis!**

## 🏗️ How It Works

### **Branch Comparison Process:**
1. **Analyzes differences** between your two release branches
2. **Identifies changed files** and code modifications
3. **Maps changes** to functional areas and components
4. **Compares against** your existing regression test coverage
5. **Generates impact assessment** with risk levels
6. **Creates new test cases** in SQA-compatible format

### **Flexible Naming Support:**
- ✅ **Any folder names** - Name your branch folders however you want
- ✅ **Any CSV file names** - Use your existing regression test file names
- ✅ **Any workspace location** - Works with any workspace structure
- ✅ **Custom file paths** - Specify exact paths if needed

## 📊 Impact Analysis Framework

### **Change Impact Levels:**
- **🔴 Critical**: Authentication, Payment, Security, Database schema, Core APIs
- **🟠 High**: New features, UI changes, Business logic, Integration points
- **🟡 Medium**: Bug fixes, Code refactoring, Configuration updates, Performance improvements
- **🟢 Low**: Documentation, Comments, Formatting changes, Minor UI updates

### **Risk Assessment Categories:**
- **Functional Risk**: Impact on business functionality
- **Integration Risk**: Impact on system integrations
- **Performance Risk**: Impact on system performance
- **Security Risk**: Impact on application security
- **Data Risk**: Impact on data integrity and accuracy

## 📤 **Output Format for SQA Integration**

### **📋 Impact Analysis Report - [GENERATED .MD FILE]:**
**File Name:** `Impact_Analysis_Report_[Timestamp].md`

**Contents Include:**
- 📊 **Executive Summary** with overall impact assessment
- 🎯 **Detailed Impact Areas** with risk levels and recommendations
- 🧪 **Affected Test Case Analysis** with specific Test Case IDs from your regression pack
- ⚠️ **Risk Assessment Matrix** prioritized by impact level
- 📝 **Actionable Recommendations** for QA team

### **🔍 Test Case Impact Analysis:**
The analyzer will examine your regression test CSV and identify specific test cases that are impacted by analyzing:
- **Test Case ID** - Extract the unique identifier from your CSV
- **Test Description** - Match functionality changes with test descriptions
- **Test Steps** - Analyze step descriptions to find affected scenarios
- **Module/Component** - Map code changes to test modules

**Example Impact Mapping:**
```markdown
## 🎯 Affected Test Cases from Regression Pack

### Authentication Module Changes:
- **TC-001**: Login with Valid Credentials ⚠️ **HIGH IMPACT**
- **TC-025**: Multi-Factor Authentication ⚠️ **CRITICAL IMPACT**  
- **TC-067**: Password Reset Functionality ⚠️ **MEDIUM IMPACT**

### Payment Processing Changes:
- **TC-156**: Credit Card Payment Processing ⚠️ **HIGH IMPACT**
- **TC-203**: Payment Export Functionality ⚠️ **CRITICAL IMPACT**
```

### **📊 Impact Analysis Summary Table:**
| ImpactArea | ImpactLevel | ChangeType | ChangedFiles | AffectedTestCaseIDs | RiskAssessment | RecommendedAction |
|------------|-------------|------------|--------------|-------------------|----------------|-------------------|
| Authentication | High | New Feature | auth.js, login.tsx | TC-001, TC-025, TC-067 | High Risk | Full regression + New tests |
| Payment Module | Critical | Bug Fix | payment.js | TC-156, TC-203 | Medium Risk | Targeted regression |

### **🧪 New Test Cases Required - [SQA-COMPATIBLE CSV]:**
| LogicalName | Version | Prerequisite | UserStory_Name | Module_Name | Description | Labels | Suite_Name | StepDescription | ExpectedResult | Parameter | qTest Req Reference | Is Automated? |
|-------------|---------|--------------|----------------|-------------|-------------|--------|------------|-----------------|----------------|-----------|-------------------|---------------|
| IMPACT_Auth_NewFeature_Test | 1 | Setup requirements | US-123 | Authentication | Test new auth feature | Impact;NewFeature | AuthImpact | 1. Test step description | Expected result | Test data | | No |

## 🚀 **Simple Usage Instructions**

### **Just Tell Me:**
1. **Branch Folder Names** - What are your two release branch folders called?
2. **Regression File Name** - What's your regression test CSV file called?
3. **Any Special Requirements** - Any specific areas you want me to focus on?

### **Example Usage:**
```
Hi! Please analyze these branches:
- Old Release: ProjectA_Release_v1.2
- New Release: ProjectA_Release_v1.3  
- Test File: Regression_80_Test.csv

Focus on payment and authentication modules.
```

### **I'll Automatically:**
- 🔍 Find and compare your branch folders
- 📊 Analyze all code differences
- 🧪 Compare with your existing test coverage
- 📝 Generate impact analysis report
- ✅ Create new test cases in SQA format
- 📋 Provide actionable recommendations

## 💡 **Quick Start Examples**

### **Example 1: Simple Analysis**
```
Please analyze:
Branch 1: WebUI_Release_v2.1
Branch 2: WebUI_Release_v2.2
Test File: Regression_80_Test.csv
```
**Output:** Impact_Analysis_Report_20250801.md + New_Test_Cases_Impact_20250801.csv + Affected_Test_Cases_Summary.csv

### **Example 2: Detailed Analysis**
```
Compare these releases:
- Previous: HealthApp_Sprint23_Release  
- Current: HealthApp_Sprint24_Release
- Regression Pack: Healthcare_Regression_Pack.csv
- Focus: Payment processing and user authentication
```
**Output:** Comprehensive .md report with specific test case IDs (TC-XXX) that are impacted

### **Example 3: Custom Paths**
```
Analyze impact between:
Old Branch: ./releases/v1.5.2/source_code
New Branch: ./releases/v1.6.0/source_code  
Test Suite: ./test_data/full_regression_suite.csv
```
**Output:** Detailed markdown analysis showing which specific test cases from your CSV are affected

## 🔍 **How Test Case Analysis Works**

### **Step 1: CSV Analysis**
- Reads your regression test CSV file
- Extracts test case IDs (TC-001, TC-002, etc.)
- Analyzes test descriptions and step details
- Maps test cases to functional modules

### **Step 2: Code Change Analysis** 
- Compares the two release branches
- Identifies modified files and functions
- Analyzes the scope and impact of changes
- Categorizes changes by functional area

### **Step 3: Intelligent Matching**
- Maps code changes to affected test cases
- Uses AI to match functionality changes with test descriptions
- Analyzes test steps to determine impact level
- Identifies both direct and indirect impacts

### **Step 4: Impact Report Generation**
- Creates markdown report with specific test case IDs
- Generates CSV of new test cases needed
- Provides actionable recommendations
- Prioritizes testing efforts based on risk

## 🎯 **What You'll Get**

### **📁 Generated Files:**
1. **📊 Impact_Analysis_Report_[Timestamp].md** 
   - Comprehensive impact analysis in markdown format
   - Specific affected test case IDs from your regression pack
   - Risk assessment and recommendations
   - Detailed change analysis with visual formatting

2. **📝 New_Test_Cases_Impact_[Timestamp].csv** 
   - New test cases in SQA-compatible format
   - Ready for direct import into SimplifyQA
   - Includes all mandatory fields and test steps

3. **📋 Affected_Test_Cases_Summary.csv**
   - List of existing test case IDs that are impacted
   - Impact level for each affected test case
   - Recommended action for each test case

### **🔍 Detailed Test Case Analysis:**
The analyzer will intelligently map code changes to your existing test cases by:

- **📖 Reading your regression CSV** - Extract test case IDs, names, descriptions, and steps
- **🔍 Analyzing code changes** - Identify what functionality was modified
- **🎯 Smart Matching** - Match changed functionality to test descriptions and steps
- **⚠️ Impact Assessment** - Determine severity of impact for each affected test case
- **📝 Generate Reports** - Create actionable recommendations in markdown format

### **📊 Test Case Impact Categories:**
- **🔴 CRITICAL IMPACT** - Test case directly tests changed functionality
- **🟠 HIGH IMPACT** - Test case covers related functionality that may be affected  
- **🟡 MEDIUM IMPACT** - Test case covers integration points with changed components
- **🟢 LOW IMPACT** - Test case may be indirectly affected

### **📈 SQA Integration Benefits:**
- ✅ **Specific Test Case IDs** - Know exactly which tests to re-run
- ✅ **Markdown Reports** - Easy to read and share with team
- ✅ **CSV Import Ready** - Direct import into SimplifyQA
- ✅ **Risk Prioritization** - Focus testing efforts on high-impact areas
- ✅ **Intelligent Analysis** - AI-powered mapping of changes to test cases

## 🏷️ **Supported File Formats:**
- **Branch Folders**: Any folder structure, any naming convention
- **Test Files**: CSV, XLSX (exported from SQA or other tools)
- **Code Files**: All common programming languages and frameworks
- **Documentation**: README, markdown, text files for context

---

## 🚀 **Ready to Start?**

Simply provide your branch folder names and regression test file name in the chat, and I'll handle the rest!

**Example Message:**
```
Hi! I need to analyze the impact between my Release_Branch_A and Release_Branch_B folders. 
My regression test file is called Regression_80_Test.csv. 
Please focus on any payment or authentication related changes.
```
