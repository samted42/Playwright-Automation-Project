# Playwright-Automation-Project
Playwright automation tests for Automation Exercise using TypeScript
As a Test Analyst, here's an updated context-specific version of the README.md, reflecting both your responsibilities and VSCode utilization. This focuses on creating, running, and managing tests from a QA perspective:
This repository is designed for automated testing of [Automation Exercise](https://automationexercise.com) using **Playwright** and **TypeScript**. As part of the QA process, this project emphasizes test coverage for critical workflows such as:
> Authentication
> Product
> Search Cart Operations
> Responsive UI Validation.

## Purpose of the Project

- Validate the functionality of the Automation Exercise site through automated tests.
- Provide regression testing as part of the QA process.
- Ensure coverage across different browsers (Chrome, Firefox, WebKit) and device types (Desktop, Tablet, Mobile).
- Facilitate collaboration using **Visual Studio Code (VSCode)** and GitHub for source control.


## Prerequisites

### **Tools Required**
- **Node.js**: [Download here](https://nodejs.org/) (v16+ is recommended)
- **npm**: Comes bundled with Node.js installation.
- **VSCode**: [Download Visual Studio Code](https://code.visualstudio.com/)
- **Git**: [Install Git](https://git-scm.com/)

### **VSCode Extensions**
To streamline the development and testing experience, install the following VSCode extensions:
- [**Playwright Test for VSCode**](https://marketplace.visualstudio.com/items?itemName=ms-playwright.playwright): Simplifies test creation, execution, and debugging.
- **Prettier**: For code formatting.
- **ESLint**: Ensures adherence to TypeScript and Playwright coding practices.
- **Debugger for Chrome/Edge/Firefox** (optional for advanced debugging).

---
## Project Set-Up

1. **Clone the Repository**
   Start by cloning the repository to your local system:
   ```bash
   git clone https://github.com/samted42/Playwright-Project.git
   cd Playwright-Project
   ```

2. **Install Dependencies**
   Install the required node modules and dependencies:
   ```bash
   npm install
   ```

3. **Install Playwright Browsers**
   Playwright manages its own browser binaries, which can be installed with the following command:
   ```bash
   npx playwright install
   ```

4. **Configure VSCode Debugger**
   - Open VSCode and load the project folder.
   - Go to the **Debug** view (`Ctrl+Shift+D` / `Cmd+Shift+D`) and select the Playwright configuration options.
   - You can now debug tests directly.

---

## Running Tests

You can run tests directly from the **VSCode terminal** or using the **Playwright Test extension**.

### **Command-Line Options:**

1. **Run All Tests**
   ```bash
   npx playwright test
   ```

2. **Run a Specific Test**
   To run a particular test file, specify it in the command:
   ```bash
   npx playwright test tests/login.spec.ts
   ```

3. **Run Tests in Debug Mode**
   Debugging lets you interact with the test execution:
   ```bash
   npx playwright test --debug
   ```

4. **Cross-browser Testing**
   Playwright automatically runs tests for all supported browsers:
   ```bash
   npx playwright test --project=chromium
   npx playwright test --project=firefox
   ```

---

## Debugging in VSCode

VSCode makes debugging efficient with the following workflows:
- Open any test file (e.g., `tests/login.spec.ts`).
- Add **breakpoints** at the lines where you want execution to pause.
- In the Debug menu, select **Run and Debug** → **Playwright Tests**.
- You can inspect variables, step through the code, and resolve issues live.

---

## Writing Tests as a Test Analyst

### Writing New Test Cases
As a Test Analyst, you can focus on designing tests for the following key areas:
- **Login/Signup Workflows**: Valid and invalid scenarios.
- **Cart Operations**: Add, remove, and update products.
- **Product Search**: Testing search bar functionality and filters.
- **End-to-End Scenarios**: From registration to checkout.

Example new test (`tests/my-new-test.spec.ts`):
```typescript
import { test, expect } from '@playwright/test';

test('Verify product search functionality', async ({ page }) => {
  // Go to the Automation Exercise website
  await page.goto('https://automationexercise.com');

  // Search for a product
  await page.fill('input[name="search"]', 'T-shirt');
  await page.click('button[data-qa="search-button"]');

  // Verify search results are displayed
  await expect(page.locator('.product-title')).toContainText('T-shirt');
});
```

---

## Project Structure

The project structure is designed for clarity and scalability:
```
├── tests/
│   ├── login.spec.ts       # Tests for login workflow
│   ├── cart.spec.ts        # Tests for cart functionality
│   ├── ...
├── .github/
│   ├── workflows/
│   │   ├── playwright.yml  # GitHub CI/CD Pipeline
├── README.md               # Project documentation
├── playwright.config.ts    # Playwright Configuration
├── package.json            # npm dependencies and scripts
├── tsconfig.json           # TypeScript configuration
```

---

## Test Reports

Generate detailed test reports automatically:
1. Run the tests:
   ```bash
   npx playwright test
   ```
2. After execution, open the report:
   ```bash
   npx playwright show-report
   ```

---

## Continuous Integration

GitHub Actions is set up for continuous testing:
- **Trigger**: Tests run automatically on every pull request and commit.
- **Workflow Configuration**: Found in `.github/workflows/playwright.yml`.

---

## Tips for Test Analysts

- Always keep tests modular and reusable.
- Group test cases for better logical flow (e.g., Login > Add to Cart > Checkout).
- Include assertions to verify test outcomes rigorously.
- Use debugging to isolate and resolve failed test cases during development.

---

## Contributing

Suggestions and contributions are welcome to improve test coverage and structure. Follow these steps:
1. Fork the repository and clone it locally.
2. Create a branch for your feature:
   ```bash
   git checkout -b feature/new-test
   ```
3. Commit changes and create a pull request.

---

## License

This project is licensed under the **MIT License**. All contributions and modifications are welcome.
