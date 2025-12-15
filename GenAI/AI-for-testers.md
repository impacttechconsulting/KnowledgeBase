# AI for Testers

[MCP Playwright](https://developer.microsoft.com/blog/the-complete-playwright-end-to-end-story-tools-ai-and-real-world-workflows)
## Playwright
1. Bootstrap tests with Codegen: Quickly capture user flows and generate test code.
2. Write and refine tests in VS Code: Organize, run, and debug tests with inline feedback and AI fixes.
3. Explore tests with UI Mode: Browse, filter, and rerun tests interactively.
4. Report and observe with the HTML Report: Get detailed, interactive overviews of your test suite.
5. Debug failures with Trace Viewer: Inspect DOM snapshots, network activity, and logs frame by frame.

## QA testing Use cases & Samples
https://medium.com/@iamsanjeevkumar/github-copilot-automate-test-case-generation-with-a-template-driven-strategy-32fd4816d493

### Sample prompts

**Direct Jira Interaction Prompts**
These prompts help fetch the requirements or features you need for the test plan:
1. Search Jira for user stories in the "Website Redesign" project with status "To Do" and provide their acceptance criteria.
2. What are the acceptance criteria for Jira issue PROJ-123: "Implement User Login Page"?
3. List all features under the current Epic #EPIC-456 in Jira Cloud, focusing on the descriptions and acceptance criteria
4. Using the acceptance criteria from Jira issue #PROJ-456, draft a detailed test plan covering unit, integration, and end-to-end test scenarios, including edge cases.
5. #jira_search "Find all 'Story' issues in the 'Website Redesign' project that are in the 'In Progress' status". Based on these issues, generate a comprehensive test plan outlining scope, objectives, resources, schedule, and testing strategy in a markdown format.

**Test Plan Generation Prompts**
Once you have the feature details, you can ask Copilot to generate a test plan. You can either paste the acceptance criteria into the chat or reference the Jira item if your MCP integration supports it: 
1. #PROJ-123: "Implement User Login Page" - Generate a comprehensive test plan including functional, negative, and edge test cases for these acceptance criteria.
2. Create a detailed test plan for the following feature, covering unit, integration, and end-to-end tests: [Paste feature description and acceptance criteria here].
3. Using the requirements in the current active Jira issue, generate a set of positive and negative test cases for the login functionality

**Slash Command Prompts**
If your specific MCP server provides preconfigured prompts, you might use a slash command (the command name depends on the server's configuration): 
1. /mcp.jiraservername.generatetestplan for issue PROJ-123
2. /mcp.atlassian.rovo.createTestCases based on the criteria in this chat context
3. /tests generate unit tests for this feature
4. /tests create tests for [function_name]
5. /tests write comprehensive unit tests, including edge cases, exception handling, and data validation

**Specific requirements or scenarios**
1. Generate a comprehensive suite of unit tests for the selected code block. Ensure coverage for happy paths, edge cases (e.g., zero, negative, and boundary values), and error conditions (e.g., invalid input, null values).
2. Write integration tests for the processPayment function. Use mocks for external services like the NotificationSystem and verify correct interactions.
3. Create a list of manual test cases for the user login functionality described in this file. Include scenarios for valid credentials, invalid password, non-existent user, and locked accounts.
4. Analyze the dataValidation module and suggest any missing test scenarios or areas of low coverage. Focus on security vulnerabilities and performance issues.

**Basic Sanity Tests (Happy Path)**
1. Generate basic sanity test cases for the currently open function/file.
2. Write a simple "happy path" unit test for this code #file:<filename>.
3. Using the Jest framework, generate one positive test case for the 'loginUser' function that validates a successful login.

**Comprehensive Sanity Tests**
1. Develop a comprehensive suite of sanity tests for this module, covering valid inputs and expected successful outputs.
2. Generate test cases for all major scenarios (positive, negative, and edge cases) for the functionality described in the selected code.
3. Create integration tests for the 'processPayment' function. Verify that a successful payment updates the order status to 'completed' and sends a notification.

**Boundary - General Prompts**
1. Generate unit tests for this function, ensuring coverage of all boundary conditions and edge cases.
2. Write comprehensive test cases for the selected code block. Focus on positive, negative, and boundary scenarios.

**Boundary - Specific Prompts**
1. Generate equivalence partition test sets for a variable age with a valid range of 18-65
2. Generate edge case test scenarios for a date input field, including tests for leap years, the last day of the month, the first day of the next month, and invalid dates like February 30th

**Generate QA documentation**
1. Create a detailed test plan outline for the current application. The plan should cover functional, performance, and security testing.
2. Based on the project files in the #codebase, draft a QA sign-off document template.
3. Generate a user acceptance testing (UAT) script for the feature described in #file:feature_spec.md
4. Write a QA assessment report based on the internal requirements in #file:internal_guidelines.docx and the test results in #file:test_results.csv
5. Summarize the #changes in the last pull request and format them as release notes for the QA team

**Review a bug report → summarize → classify root cause**
> [!TIP]
Review the following bug report content. Summarize the core issue, steps to reproduce, and expected vs. actual results in a concise summary (under 50 words).
[Paste the entire bug report text here]

> [!TIP]
> Based on the bug report content I provided (or the summary above), classify the likely root cause into one of these categories: Logic Error, Data Issue, Configuration Problem, UI/UX Flaw, Performance Bottleneck, or External Dependency. Explain your reasoning briefly.[Paste bug report or reference the previous turn]

> [!TIP]
I'm analyzing several recent bugs (reports below). Identify common patterns or recurring themes in the root causes, affected modules, or error messages. Bug Report 1: [Content] Bug Report 2: [Content]
