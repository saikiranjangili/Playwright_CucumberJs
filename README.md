# Playwright Project

This project uses [Playwright](https://playwright.dev/) for end-to-end testing. Below are the detailed steps for setup, execution, maintenance, and Git commands.

---

## Setup

1. **Clone the Repository**:
    
   git clone https://github.com/saikiranjangili/Playwright_CucumberJs.git
      

2. **Install Node.js**:
   Ensure you have Node.js installed. Download it from [Node.js Official Website](https://nodejs.org/).

3. **Install Dependencies**:
   Run the following command to install project dependencies:
    
   npm install
   

4. **Install Playwright Browsers**:
   Install the required browsers for Playwright:
    
   npx playwright install
   

5. **Environment Configuration**:
   - Create a \.env\ file in the root directory if environment variables are required.
   - Example \.env\ file:
     
     BASE_URL=https://example.com
     

---

### Tips and convention:

File and Folders
	• Folders: camelCase
	• Files: lowercase with hyphen
	• Feature files: a noun describing functionality
	• Feature files ends with .feature
	• Keep feature file names short but descriptive (be creative)

Steps
	• Step definition files ends with -steps.js
	• Step definition code and logic should be short and mostly on one line i.e. all logic is abstracted within the page object.
	• No Logic in step definition file
	• Step definition mirrors page object e.g. login-page.js => login-steps.js [Steps and workflows are specific to a page]
	• Step definition Gherkin, if the action is unique to a page, should end with the page title. this will help easy location and re-use by other people
	e.g. "And Alex has selected "Employee Prefill" option on Employee Invite page"
	• On a then step Exposed methods should return either a Boolean, string or an array for assertion.
	• On other steps, one method from page object should represent a real life action
	• Parameterize actions if possible for re-useability

Page Objects
	• Page objects ends with -page.js
	• Page objects inherits from base-page.js
	• Use methods from base page accessed via this
	• No assertions in page objects

Tips
	• Use async and await.
	• Each folder in the data folder maps to environment variable set (ADP_ENV=fit_api)
	• Prefer to use tags on feature, ignore scenarios that are not ready yet.
	• Avoid duplicating user actions in page object - take the time to study what we currently have
	• Tag scenarios with Story's Jira story number for traceability: e.g. @SBSRUNMOD-4676 ??
	• You can place a unique tag on a scenario whilst working on it e.g. @aawip and execute using e.g. 
	• ADP_ENV=fit SELENIUM_BROWSER=chrome SELENIUM_REMOTE_URL=http://10.97.125.165:4444/wd/hub node . -t "@aawip"

Branch naming (TBC)
	• feat(proj): comment - When a new feature is being added
	• fix(proj): comment - When editing an existing feature
	• chore(proj): comment - When modifying anything else

---

## Execution

1. **Run All Tests**:
    
   npx playwright test
   

2. **Run Tests in Debug Mode**:
    
   npx playwright test --debug
   

3. **Run Specific Test File**:
    
   npx playwright test tests/example.spec.ts
   

4. **Generate HTML Report**:
   After running tests, generate and view the report:
    
   npx playwright show-report
   

5. **Run Tests with Specific Tags**:
   Use tags to filter tests:
    
   npx playwright test --grep @tagname
   

---

## Maintenance

1. **Update Dependencies**:
    
   npm update
   

2. **Handle Test Failures**:
   - Check the Playwright report for failure details.
   - Use the debug mode to investigate issues:
      
     npx playwright test --debug
     

3. **Add New Tests**:
   - Create a new \.spec.ts\ file in the \	ests\ folder.
   - Use Playwright's [Test Generator](https://playwright.dev/docs/codegen) to scaffold tests:
      
     npx playwright codegen <url>
     

4. **Lint and Format Code**:
   Ensure code quality by running:
    
   npm run lint
   npm run format
   

---

## Git Commands

1. **Clone Repository**:
    
   git clone https://github.com/saikiranjangili/Playwright_CucumberJs.git
   

2. **Check Status**:
    
   git status
   

3. **Stage Changes**:
    
   git add .
   

4. **Commit Changes**:
    
   git commit -m \Your commit message\
   

5. **Push Changes**:
    
   git push origin <branch-name>
   

6. **Pull Latest Changes**:
    
   git pull origin <branch-name>
   

7. **Create a New Branch**:
    
   git checkout -b <new-branch-name>
   

8. **Merge Branches**:
    
   git checkout <target-branch>
   git merge <source-branch>
   

9. **Resolve Merge Conflicts**:
   - Open conflicting files in your editor.
   - Resolve conflicts manually.
   - Stage resolved files:
      
     git add <file>
     
   - Commit the merge:
      
     git commit
     

---

## Additional Resources

- [Playwright Documentation](https://playwright.dev/docs/intro)
- [Node.js Documentation](https://nodejs.org/en/docs/)
- [Git Documentation](https://git-scm.com/doc)
