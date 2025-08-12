# Copilot QA Prompts for Simplify QA

A collection of specialized prompts for software quality assurance workflows, designed to integrate seamlessly with Simplify QA.

## Prompts

### 🧪 Intelligent Test Case Generation

**File:** `Jira_TestCase_Generation_Prompt.md`

Generates comprehensive test cases from Jira tickets with automatic adaptation for different testing types (API, Database, Functional, Performance). Outputs CSV format ready for Simplify QA import.

**Key Features:**

- Smart test type detection and adaptation
- Jira ticket analysis and parsing
- SQA-compatible CSV output format
- Intelligent naming conventions with Jira Ticket ID

### 🔍 Key Impact Analyzer

**File:** `Key_Impact_Analyzer_Prompt.md`

Analyzes release branches to identify key impacts and potential testing areas. Provides comprehensive impact assessment for release planning.

**Key Features:**

- Branch impact analysis
- User-friendly input format
- READ ONLY analysis approach
- Comprehensive output generation

### 📊 Regression Scope Analyzer

**File:** `Regression_Scope_Prompt.md`

Analyzes code changes and their impact on existing regression test cases from Simplify QA.

### 🎯 UI Object Extractor

**File:** `UI_Object_Extractor_Prompt.md`

Extracts UI elements and properties for test automation. Use Web Recorder first when available - this prompt is for when manual extraction is needed.

## Usage

1. Copy the desired prompt from the markdown files
2. Paste into your AI assistant (Claude, ChatGPT, etc.)
3. Follow the prompt-specific instructions
4. For test case generation: Import the CSV output directly into Simplify QA

## CSV Template Structure

All test case outputs follow the Simplify QA CSV template with these columns:

- LogicalName, TestCaseDescription, Priority, Tags, Preconditions, TestData, Steps, ExpectedResults

Perfect for direct import into your QA management system.
