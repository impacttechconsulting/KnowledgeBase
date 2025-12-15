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

**MCP Slash Command Prompts**
If your specific MCP server provides preconfigured prompts, you might use a slash command (the command name depends on the server's configuration): 
1. /mcp.jiraservername.generatetestplan for issue PROJ-123
2. /mcp.atlassian.rovo.createTestCases based on the criteria in this chat context
