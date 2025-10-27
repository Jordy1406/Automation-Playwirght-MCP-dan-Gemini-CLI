# 🤖 AI-Driven QA Automation with Gemini CLI and Playwright MCP

## Getting Started: Install & First Run

This project demonstrates how to leverage the power of the Gemini CLI, combined with the Playwright Model Context Protocol (MCP) server, to perform complex, end-to-end web QA testing using natural language prompts.

### Step 1: Install Gemini CLI

The Gemini CLI is the primary interface for running the AI agent.

```bash
# Install globally with npm
npm install -g @google/gemini-cli
Step 2: Configure Playwright MCP Server
The Playwright MCP Server provides the browser automation capabilities. You need to configure the Gemini CLI to use it by adding the following JSON block to your Gemini CLI settings file, which is typically located at ~/.gemini/settings.json.
Create or edit ~/.gemini/settings.json and add the following content:
code
JSON
{
  "mcpServers": {
    "playwright": {
      "command": "npx",
      "args": [
        "@playwright/mcp@latest"
      ]
    }
  }
}
Step 3: Authenticate the Gemini CLI
Log in to the Gemini CLI. The OAuth option is recommended for the free tier access to Gemini 2.5 Pro.
code
Bash
gemini
# Follow the prompt to choose 'Login with Google' and complete the browser flow.
Step 4: Run the Automated Test Case (First Run Example)
Once configured and authenticated, start the Gemini CLI and provide the natural language command. The playwright tool is automatically available via the @playwright prefix.
code
Bash
gemini
Inside the Gemini CLI, enter the following prompt:
code
Bash
@playwright Open @ https://www.saucedemo.com/, then log in with "standard_user" and "secret_sauce". Add the "Sauce Labs Backpack" to the cart, proceed to checkout, fill in random valid data for first name, last name, and zip code. Continue and finish the order. Finally, verify that the message "Thank you for your order!" is visible on the page.
Project: AI-Automated E-commerce Checkout Test
![alt text](https://img.shields.io/badge/Powered%20By-Gemini%20CLI-blue)

![alt text](https://img.shields.io/badge/Tool-Playwright%20MCP-green)

![alt text](https://img.shields.io/github/license/google-gemini/gemini-cli)
🌟 Overview
This portfolio project showcases a modern, AI-driven approach to Quality Assurance (QA) and test automation. Instead of writing and maintaining brittle Page Object Models (POMs) or imperative code, we define complex end-to-end test scenarios using natural language.
The combination of Gemini CLI (the open-source AI agent) and the Playwright Model Context Protocol (MCP) server allows the Large Language Model (LLM) to directly interact with the browser's accessibility tree, making automation highly flexible, resilient, and descriptive.
🧪 Test Scenario: SauceDemo E-commerce Checkout
The core of this demonstration is automating a standard e-commerce workflow on the SauceDemo site.
Step	Action	Tool
1	Navigate to https://www.saucedemo.com/	@playwright
2	Login with standard_user and secret_sauce	@playwright
3	Add product "Sauce Labs Backpack" to the cart	@playwright
4	Navigate to the cart and click Checkout	@playwright
5	Fill in form data (First Name, Last Name, Zip)	@playwright
6	Click Continue and then Finish	@playwright
7	Verification: Assert the success message "Thank you for your order!" is visible.	@playwright
🛠️ Key Technologies
Gemini CLI: The AI orchestrator that interprets the user's natural language prompt and decides which tool (@playwright, built-in shell, etc.) to call.
Playwright MCP Server: A dedicated Model Context Protocol server that exposes Playwright's browser automation capabilities (browser_navigate, browser_click, browser_type) as structured tools for the LLM.
Model Context Protocol (MCP): The secure, structured protocol enabling the LLM to connect and communicate with external tools.
💡 Why this approach is powerful for QA
Natural Language Testing: Test cases become living documentation written in plain English, reducing the barrier to entry for non-developers.
High Resilience: The Playwright MCP uses the accessibility tree, which is less prone to breaking from minor UI changes than traditional XPath or CSS selectors.
Extensibility: The Gemini CLI's built-in tools (Shell Commands, File System Operations) allow for hybrid tests, such as: "Deploy the app, then run the checkout test on the staging URL, and if it fails, capture a screenshot and save it."



