# Mastering Playwright: 10 Essential Chapters & 200 Interview Questions to Land Your Next Role
**Author:** Lamhot Siagian 🔗 [LinkedIn](https://www.linkedin.com/in/lamhotsiagian)

---

### 1. Introduction to Playwright

1. What distinguishes Playwright from other end-to-end testing frameworks like Selenium or Cypress?
2. Explain Playwright’s architecture—how does it achieve cross-browser automation?
3. Which languages does Playwright support, and what are the trade-offs of each?
4. How does Playwright handle headless vs. headful browser modes?
5. Describe Playwright’s installation process and its bundled browser dependencies.
6. What built-in features does Playwright offer for test retries and flakiness mitigation?
7. How does Playwright ensure consistent behavior across Chromium, Firefox, and WebKit?
8. Explain Playwright’s tracing feature and its benefits for debugging.
9. What are Playwright “contexts” and how do they facilitate isolated test sessions?
10. Describe a scenario where Playwright’s multi-page support is critical.

---

### 2. Getting Started & Environment Setup

1. Walk me through setting up a new Playwright project in Node.js from scratch.
2. How do you configure Playwright in a non-JavaScript language (e.g., Python or C#)?
3. Where does Playwright store its browser binaries, and how can you customize that path?
4. What command generates Playwright’s initial test scaffold, and what does it include?
5. How do you install only a subset of browsers (e.g., Chromium only) to save space?
6. Explain how to integrate Playwright into an existing monorepo or workspace.
7. How can you pin Playwright to a specific browser version?
8. What environment variables or config files can you use to customize test runs?
9. How do you upgrade Playwright to the latest version with minimal breaking changes?
10. What troubleshooting steps would you take if “npx playwright install” fails?

---

### 3. Selectors & Element Handling

1. Compare CSS, XPath, text, role, and data-test selectors in Playwright—when to use each?
2. How does Playwright’s `getByRole()` selector improve test resilience?
3. Explain how to wait for an element to become attached, visible, enabled, or stable.
4. What’s the difference between `page.$()`, `page.$$()`, and `page.locator()`?
5. How do you handle dynamic elements whose selectors change at runtime?
6. Describe how to chain locator filters (e.g., `.filter()`, `.nth()`).
7. How would you click an element inside a shadow DOM or iframe?
8. Explain built-in auto-waiting: which actions implicitly wait and what do they wait for?
9. How can you assert an element’s CSS property or computed style?
10. What strategy would you use to locate elements in a highly data-driven, dynamic web app?

---

### 4. Writing Robust Tests

1. How do you structure tests using fixtures, hooks, and test suites in Playwright Test Runner?
2. Describe the purpose of `beforeAll`, `beforeEach`, `afterEach`, and `afterAll`.
3. What best practices ensure test isolation and avoid state leakage between tests?
4. How do you share common setup logic across multiple test files?
5. Explain how retries and timeouts work at the test and suite level.
6. How would you parameterize a test to run with multiple input sets?
7. What are the trade-offs between using `test.describe.parallel` vs. sequential execution?
8. How do you write custom matchers or extend Playwright’s assertion library?
9. Explain how to capture and attach screenshots and videos upon test failures.
10. How do you debug flaky tests—what diagnostic information do you collect first?

---

### 5. Working with Pages & Frames

1. How do you navigate to a URL and wait for specific network or load events?
2. Describe how to handle multiple tabs or popup windows in a test.
3. How do you switch context into an iframe and interact with its contents?
4. Explain Playwright’s `page.waitForNavigation()` vs. `locator.waitFor()`.
5. How would you test a multi-step redirect flow across different domains?
6. What are the pitfalls of using `page.reload()` or `page.goto()` repeatedly in tests?
7. How do you handle file downloads and uploads via Playwright?
8. Explain how to intercept and handle dialogs (alerts, confirms, prompts) on a page.
9. How can you expose functions from the test into the page’s JavaScript context?
10. Describe a strategy for testing web apps that open complex modal dialogs or overlays.

---

### 6. Network Interception & Mocking

1. How do you intercept network requests and modify responses on the fly?
2. Explain the difference between `route.fulfill()`, `route.abort()`, and `route.continue()`.
3. How can you simulate slow network conditions or offline mode?
4. What’s the recommended approach to mock API responses for deterministic tests?
5. How do you record and replay real API traffic in Playwright?
6. Describe how to verify request payloads and headers in tests.
7. How do you stub only certain endpoints while letting others pass through?
8. Explain how to handle authentication tokens or cookies when mocking.
9. What challenges arise when testing WebSocket or SSE connections, and how do you intercept them?
10. How do you ensure your mock data stays in sync with evolving backend contracts?

---

### 7. Cross-Browser & Mobile Testing

1. How do you configure Playwright to run tests across Chromium, Firefox, and WebKit?
2. What options are available to emulate mobile devices and set viewport sizes?
3. How do you test geolocation- or device-orientation-sensitive features?
4. Explain how to capture and compare screenshots for visual regression across browsers.
5. What considerations apply when running tests on iOS or Android emulators vs. real devices?
6. How can you integrate Playwright tests with a cloud-based device farm?
7. Describe the process to record video for each browser session and attach it to reports.
8. How do you detect and handle browser-specific quirks or CSS prefixes in tests?
9. Explain how to parameterize your test matrix to include browser, device, and locale.
10. What metrics would you gather to compare performance across browsers?

---

### 8. CI/CD Integration & Parallel Execution

1. How do you run Playwright tests in GitHub Actions, and what key config steps are needed?
2. Explain how to distribute tests across multiple machines or containers for parallelism.
3. What environment variables control Playwright’s behavior in CI (e.g., `CI`, `DEBUG`)?
4. How can you generate and store HTML or JUnit reports in a CI pipeline?
5. Describe how to configure retries only on CI, but not on local development runs.
6. What are the best practices for caching browser binaries and node modules in CI?
7. How do you set up a custom reporter (e.g., Slack, TestRail) in your pipeline?
8. Explain how to detect and fail fast on critical test failures to save CI minutes.
9. How do you integrate Playwright tests into Docker-based build flows?
10. What strategies help diagnose CI-only failures vs. local-only failures?

---

### 9. Reporting & Debugging

1. What built-in reporters does Playwright provide, and when would you choose each?
2. How do you generate an HTML trace and use the Trace Viewer to debug a test?
3. Explain how to attach console logs, network logs, and request/response bodies to reports.
4. How can you configure Playwright to take a screenshot on every action or step?
5. Describe how to write a custom reporter plugin for your own dashboard.
6. What tools help you step through a paused test and inspect page state interactively?
7. How do you debug tests in CI where you can’t launch a headed browser?
8. Explain the usage of `DEBUG=pw:api` or other debug environment flags.
9. How can you integrate Playwright’s output with external test management systems?
10. What metrics would you collect from test runs to measure suite health over time?

---

### 10. Advanced Extensions & Ecosystem

1. Compare Playwright Test Runner vs. using Playwright with Jest or Mocha—pros and cons?
2. What community plugins or extensions have you used to enhance Playwright’s functionality?
3. How would you integrate Playwright into a larger BDD framework like Cucumber?
4. Explain how Playwright’s experimental features (e.g., web component testing) might fit your needs.
5. How can you leverage Playwright’s API to build a custom test orchestration tool?
6. Describe how to extend Playwright’s playwright.config.js with TypeScript or advanced logic.
7. What patterns help you organize and share helper functions or page-object modules?
8. How do you keep your test suite maintainable as the application under test grows?
9. Explain the role of Playwright in performance testing or accessibility auditing.
10. What are emerging trends in Playwright’s roadmap that you’re excited about?

---
### 100 top Playwright JavaScript automation interview questions with one-liner answers
1. **What is Playwright?**
   Playwright is a Node.js library for automating web browsers.

2. **Which browsers does Playwright support?**

    * Chromium
    * Firefox
    * WebKit

3. **How do you install Playwright?**

   ```bash
   npm install @playwright/test
   ```

4. **How do you launch a browser in Playwright?**

   ```javascript
   const browser = await playwright.chromium.launch();
   ```

5. **How do you open a new page in Playwright?**

   ```javascript
   const page = await browser.newPage();
   ```

6. **How do you navigate to a URL in Playwright?**

   ```javascript
   await page.goto('https://example.com');
   ```

7. **How do you take a screenshot in Playwright?**

   ```javascript
   await page.screenshot({ path: 'screenshot.png' });
   ```

8. **How do you click an element in Playwright?**

   ```javascript
   await page.click('selector');
   ```

9. **How do you type into an input field in Playwright?**

   ```javascript
   await page.fill('selector', 'text');
   ```

10. **How do you wait for an element to be visible in Playwright?**

    ```javascript
    await page.waitForSelector('selector');
    ```

11. **How do you get the text content of an element in Playwright?**

    ```javascript
    const text = await page.textContent('selector');
    ```

12. **How do you set the viewport size in Playwright?**

    ```javascript
    await page.setViewportSize({ width: 1280, height: 720 });
    ```

13. **How do you emulate a mobile device in Playwright?**

    ```javascript
    await page.emulate(devices['iPhone 11']);
    ```

14. **How do you handle file uploads in Playwright?**

    ```javascript
    await page.setInputFiles('input[type="file"]', 'path/to/file');
    ```

15. **How do you handle alerts in Playwright?**

    ```javascript
    page.on('dialog', dialog => dialog.accept());
    ```

16. **How do you hover over an element in Playwright?**

    ```javascript
    await page.hover('selector');
    ```

17. **How do you simulate a drag-and-drop action in Playwright?**

    ```javascript
    await page.dragAndDrop('source', 'target');
    ```

18. **How do you check if an element is visible in Playwright?**

    ```javascript
    const isVisible = await page.isVisible('selector');
    ```

19. **How do you check if an element is enabled in Playwright?**

    ```javascript
    const isEnabled = await page.isEnabled('selector');
    ```

20. **How do you wait for navigation in Playwright?**

    ```javascript
    await page.waitForNavigation();
    ```

21. **How do you select an option from a dropdown in Playwright?**

    ```javascript
    await page.selectOption('selector', 'value');
    ```

22. **How do you get the value of an input field in Playwright?**

    ```javascript
    const value = await page.inputValue('selector');
    ```

23. **How do you press a key in Playwright?**

    ```javascript
    await page.keyboard.press('Enter');
    ```

24. **How do you get the current URL in Playwright?**

    ```javascript
    const url = page.url();
    ```

25. **How do you run a script in the browser context in Playwright?**

    ```javascript
    await page.evaluate(() => /* script */);
    ```

26. **How do you capture a PDF of a page in Playwright?**

    ```javascript
    await page.pdf({ path: 'page.pdf' });
    ```

27. **How do you handle cookies in Playwright?**

    ```javascript
    await page.context().addCookies([
      { name: 'cookie', value: 'value', domain: 'example.com' }
    ]);
    ```

28. **How do you clear cookies in Playwright?**

    ```javascript
    await page.context().clearCookies();
    ```

29. **How do you set a browser context in Playwright?**

    ```javascript
    const context = await browser.newContext();
    ```

30. **How do you close the browser in Playwright?**

    ```javascript
    await browser.close();
    ```

31. **How do you run a headless browser in Playwright?**

    ```javascript
    const browser = await playwright.chromium.launch({ headless: true });
    ```

32. **How do you perform mouse actions in Playwright?**

    ```javascript
    await page.mouse.click(x, y);
    ```

33. **How do you handle authentication in Playwright?**

    ```javascript
    await page.authenticate({ username: 'user', password: 'pass' });
    ```

34. **How do you get the HTML of an element in Playwright?**

    ```javascript
    const html = await page.innerHTML('selector');
    ```

35. **How do you wait for a specific timeout in Playwright?**

    ```javascript
    await page.waitForTimeout(5000);
    ```

36. **How do you handle multiple pages or tabs in Playwright?**

    ```javascript
    const newPage = await context.newPage();
    ```

37. **How do you save the HAR file in Playwright?**

    ```javascript
    await page.routeFromHAR('example.har');
    ```

38. **How do you handle iframes in Playwright?**

    ```javascript
    const frame = await page.frame({ name: 'frameName' });
    ```

39. **How do you check if an element is checked in Playwright?**

    ```javascript
    const isChecked = await page.isChecked('selector');
    ```

40. **How do you set a default timeout for actions in Playwright?**

    ```javascript
    page.setDefaultTimeout(10000);
    ```

41. **How do you capture network requests in Playwright?**

    ```javascript
    page.on('request', request => console.log(request.url()));
    ```

42. **How do you mock network responses in Playwright?**

    ```javascript
    await page.route('**/api', route =>
      route.fulfill({ status: 200, body: 'mocked' })
    );
    ```

43. **How do you block certain URLs in Playwright?**

    ```javascript
    await page.route('**/*', route => route.abort());
    ```

44. **How do you listen to console messages in Playwright?**

    ```javascript
    page.on('console', msg => console.log(msg.text()));
    ```

45. **How do you run tests in parallel in Playwright?**

    ```javascript
    test.parallel();
    ```

46. **How do you capture video of a test run in Playwright?**

    ```javascript
    await context.newPage({ recordVideo: { dir: 'videos/' } });
    ```

47. **How do you assert that an element has a specific attribute in Playwright?**

    ```javascript
    await expect(page.locator('selector')).toHaveAttribute('attr', 'value');
    ```

48. **How do you use a proxy server in Playwright?**

    ```javascript
    const browser = await playwright.chromium.launch({
      proxy: { server: 'http://proxy.com' }
    });
    ```

49. **How do you change the user agent in Playwright?**

    ```javascript
    await page.setUserAgent('custom-agent');
    ```

50. **How do you assert that an element has specific text in Playwright?**

    ```javascript
    await expect(page.locator('selector')).toHaveText('text');
    ```

51. **How do you check if an element is disabled in Playwright?**

    ```javascript
    const isDisabled = await page.isDisabled('selector');
    ```

52. **How do you wait for a network response in Playwright?**

    ```javascript
    await page.waitForResponse('**/api');
    ```

53. **How do you handle timeouts for specific actions in Playwright?**

    ```javascript
    await page.click('selector', { timeout: 5000 });
    ```

54. **How do you run a single test in Playwright?**

    ```javascript
    test.only('test name', async ({ page }) => { /* test code */ });
    ```

55. **How do you skip a test in Playwright?**

    ```javascript
    test.skip('test name', async ({ page }) => { /* test code */ });
    ```

56. **How do you mark a test as failing in Playwright?**

    ```javascript
    test.fail('test name', async ({ page }) => { /* test code */ });
    ```

57. **How do you take a screenshot on failure in Playwright?**
    Configure `screenshot: 'only-on-failure'` in your test configuration.

58. **How do you retry a failing test in Playwright?**
    Use `retries: 2` in your test configuration.

59. **How do you capture a trace of a test run in Playwright?**

    ```javascript
    await page.tracing.start({ screenshots: true, snapshots: true });
    ```

60. **How do you stop capturing a trace in Playwright?**

    ```javascript
    await page.tracing.stop({ path: 'trace.zip' });
    ```

61. **How do you disable JavaScript in Playwright?**

    ```javascript
    await page.setJavaScriptEnabled(false);
    ```

62. **How do you set a geolocation in Playwright?**

    ```javascript
    await context.setGeolocation({ latitude: 59.95, longitude: 30.33 });
    ```

63. **How do you change the timezone in Playwright?**

    ```javascript
    await context.setDefaultTimezone('Europe/London');
    ```

64. **How do you add HTTP headers to requests in Playwright?**

    ```javascript
    await page.setExtraHTTPHeaders({ 'header': 'value' });
    ```

65. **How do you emulate offline mode in Playwright?**

    ```javascript
    await context.setOffline(true);
    ```

66. **How do you emulate a slow network in Playwright?**

    ```javascript
    await context.setNetworkConditions({
      download: 100000,
      upload: 50000,
      latency: 200
    });
    ```

67. **How do you handle basic authentication in Playwright?**

    ```javascript
    await page.authenticate({ username: 'user', password: 'pass' });
    ```

68. **How do you handle form submission in Playwright?**

    ```javascript
    await page.click('form [type="submit"]');
    ```

69. **How do you check if a checkbox is checked in Playwright?**

    ```javascript
    const isChecked = await page.isChecked('input[type="checkbox"]');
    ```

70. **How do you record a video of a test run in Playwright?**
    Configure `recordVideo` in the browser context options.

71. **How do you add a script tag to a page in Playwright?**

    ```javascript
    await page.addScriptTag({ url: 'https://example.com/script.js' });
    ```

72. **How do you add a style tag to a page in Playwright?**

    ```javascript
    await page.addStyleTag({ content: 'body { background-color: red; }' });
    ```

73. **How do you focus an element in Playwright?**

    ```javascript
    await page.focus('selector');
    ```

74. **How do you blur an element in Playwright?**

    ```javascript
    await page.blur('selector');
    ```

75. **How do you check if an element is editable in Playwright?**

    ```javascript
    const isEditable = await page.isEditable('selector');
    ```

76. **How do you scroll an element into view in Playwright?**

    ```javascript
    await page.locator('selector').scrollIntoViewIfNeeded();
    ```

77. **How do you get the bounding box of an element in Playwright?**

    ```javascript
    const box = await page.locator('selector').boundingBox();
    ```

78. **How do you use Playwright with TypeScript?**
    Install TypeScript and configure Playwright with TypeScript support.

79. **How do you integrate Playwright with CI/CD pipelines?**
    Use the Playwright test runners and integrate with CI/CD tools like GitHub Actions, Jenkins, or CircleCI.

80. **How do you debug Playwright tests?**

    ```javascript
    test('name', async ({ page }) => {
      await page.pause();
    });
    ```

81. **How do you capture console logs in Playwright?**

    ```javascript
    page.on('console', msg => console.log(msg.text()));
    ```

82. **How do you handle network failures in Playwright?**

    ```javascript
    page.on('requestfailed', request => console.log(request.url()));
    ```

83. **How do you run Playwright tests headlessly?**

    ```javascript
    const browser = await playwright.chromium.launch({ headless: true });
    ```

84. **How do you capture network traffic in Playwright?**

    ```javascript
    page.on('response', response => console.log(response.url()));
    ```

85. **How do you set cookies in Playwright?**

    ```javascript
    await context.addCookies([{ name: 'cookie', value: 'value', domain: 'example.com' }]);
    ```

86. **How do you delete cookies in Playwright?**

    ```javascript
    await context.clearCookies();
    ```

87. **How do you get cookies in Playwright?**

    ```javascript
    const cookies = await context.cookies();
    ```

88. **How do you set local storage in Playwright?**

    ```javascript
    await page.evaluate(() => localStorage.setItem('key', 'value'));
    ```

89. **How do you get local storage in Playwright?**

    ```javascript
    const value = await page.evaluate(() => localStorage.getItem('key'));
    ```

90. **How do you capture network request bodies in Playwright?**

    ```javascript
    page.on('request', request => console.log(request.postData()));
    ```

91. **How do you handle multiple downloads in Playwright?**

    ```javascript
    await page.waitForEvent('download');
    ```

92. **How do you handle popups in Playwright?**

    ```javascript
    page.on('popup', popup => /* handle popup */);
    ```

93. **How do you measure page load time in Playwright?**

    ```javascript
    const timing = await page.evaluate(() => performance.timing);
    ```

94. **How do you capture browser logs in Playwright?**

    ```javascript
    page.on('console', msg => console.log(msg.text()));
    ```

95. **How do you handle redirects in Playwright?**

    ```javascript
    page.on('response', response => response.url());
    ```

96. **How do you handle CSP (Content Security Policy) in Playwright?**

    ```javascript
    await page.setExtraHTTPHeaders({ 'Content-Security-Policy': 'default-src "self"' });
    ```

97. **How do you handle service workers in Playwright?**

    ```javascript
    await context.serviceWorkers();
    ```

98. **How do you check the status code of a network response in Playwright?**

    ```javascript
    page.on('response', response => response.status());
    ```

99. **How do you set viewport size in Playwright?**

    ```javascript
    await page.setViewportSize({ width: 1280, height: 720 });
    ```

100. **How do you capture HTTP headers in Playwright?**

     ```javascript
     page.on('request', request => console.log(request.headers()));
     ```

# References
https://medium.com/@s.atmaramani/101-top-playwright-javascript-automation-interview-questions-with-one-liner-answers-56ba240fa84c