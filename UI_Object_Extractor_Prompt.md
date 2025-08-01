# UI Element Extraction and Object Repository Generation Prompt

## **Objective**
Extract UI elements from web applications and generate comprehensive object repository data in CSV format using the SQA ObjectTemplate structure.

## **Template Structure**
The CSV file must follow this exact structure with the following columns:

**[TEMPLATE - DO NOT MODIFY COLUMN STRUCTURE]**

| Column Name | Requirement | Instructions |
|-------------|-------------|-------------|
| **ElementName** | **Mandatory** | A clear and unique name for the UI element (e.g., LoginButton, UsernameField) |
| **XPath** | **Mandatory** | XPath locator for the element |
| **ID** | Optional | HTML ID attribute value if available |
| **CSS** | Optional | CSS selector for the element |
| **ClassName** | Optional | HTML class attribute value |
| **Name** | Optional | HTML name attribute value |
| **Text** | Optional | Visible text content of the element |
| **TagName** | **Mandatory** | HTML tag name (input, button, div, etc.) |
| **AccessibilityID** | Optional | Accessibility identifier if available |
| **AdditionalProperties** | Optional | Other attributes in key=value format (type=text;placeholder=Enter name) |

## **CSV Format Requirements**

### **Row 1 (Headers) - [TEMPLATE]:**
```
ElementName,XPath,ID,CSS,ClassName,Name,Text,TagName,AccessibilityID,AdditionalProperties
```

### **Row 2 (Field Requirements) - [TEMPLATE]:**
```
(Mandatory),(Mandatory),,,,,,,(Mandatory),,
```

### **Row 3 onwards (Element Data) - [YOUR UI ELEMENTS]:**
- Each row represents one UI element with all its properties
- Mandatory fields must be filled for each element
- Optional fields can be left blank if not available or applicable

## **Element Extraction Guidelines**

### **Extraction Methods:**
- **SQA Web Recorder** (Recommended): Automated recording tool that captures multiple attributes
- **Browser Developer Tools**: Manual inspection using F12 developer tools
- **Code Analysis**: Direct examination of source code when available

### **Quality Standards:**
- **Create only valuable elements** - Focus on interactive and testable UI components
- **Use descriptive names** - Element names should clearly describe the component's purpose
- **Ensure unique identification** - Each element should have reliable locators
- **Include multiple locators** - Provide backup identification strategies when possible

### **Element Naming Convention:**
- ElementName should be descriptive and follow camelCase format
- Format: [ComponentType][Purpose] or [Page][ComponentType]
- **Examples:** "LoginButton", "UsernameInput", "HomePageNavMenu", "SubmitFormButton"

## **Example Output Format - [SAMPLE CSV]:**
```csv
ElementName,XPath,ID,CSS,ClassName,Name,Text,TagName,AccessibilityID,AdditionalProperties
(Mandatory),(Mandatory),,,,,,,(Mandatory),,
LoginButton,//button[@id='login-btn'],login-btn,#login-btn,btn btn-primary,loginBtn,Login,button,login-button,type=submit;role=button
UsernameInput,//input[@name='username'],username-field,.username-input,form-control,username,,input,username-input,type=text;placeholder=Enter username
PasswordInput,//input[@type='password'],password-field,.password-input,form-control,password,,input,password-input,type=password;placeholder=Enter password
RememberCheckbox,//input[@type='checkbox' and @name='remember'],remember-me,#remember-checkbox,checkbox-input,remember,Remember me,input,remember-checkbox,type=checkbox;checked=false
ForgotPasswordLink,//a[contains(text(),'Forgot Password')],forgot-pwd-link,.forgot-password,link-text,,"Forgot Password?",a,forgot-password-link,href=/forgot-password
ErrorMessage,//div[@class='error-message'],error-msg,.error-display,alert alert-danger,,"Invalid username or password",div,error-message,role=alert;aria-live=polite
```

## **Instructions for Use:**
1. Analyze the target web application or provided specifications
2. Identify all interactive UI elements that need to be captured
3. Extract element properties using preferred method (Web Recorder, Developer Tools, or Code Analysis)
4. Create descriptive and unique element names
5. Export to CSV file following the exact template format
6. Ensure all mandatory fields are populated appropriately
7. Validate that extracted elements can be reliably located

### **Usage Template Example:**
```
Please extract UI elements for:
Application: [Application Name/URL]
Page/Feature: [Specific page or feature]
JIRA Ticket: [TICKET-ID] (if applicable)
Element Focus: [Login form, Navigation menu, etc.]

Generate CSV output in the SQA ObjectTemplate format for automation.
```

## **Notes:**
- Maintain consistency with the SQA ObjectTemplate structure
- Each element should be independently locatable and testable
- Include both primary and backup locator strategies where possible
- Ensure element names are clear and follow naming conventions
- Test extracted locators in browser console when possible

