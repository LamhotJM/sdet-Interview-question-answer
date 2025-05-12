---
header-includes:
  - \usepackage{etoolbox}
  - \usepackage{fancyhdr}
  - \pagestyle{fancy}
  - \fancyhead{}
  - \fancyfoot[L]{Curated by Lamhot Siagian}
  - \fancyfoot[C]{\thepage}
---

![image](https://github.com/user-attachments/assets/7e1da1f8-cf8c-42d9-882f-fc967bcf8b00)

## 💻 1. Languages: Java

**Q1. Describe a time you designed a maintainable test framework in Java.**  
**Situation:** Our UI tests were brittle and duplicated code across modules. 🤔  
**Task:** Refactor into a scalable, maintainable Java framework. 🎯  
**Action:**  
- Created a Page Object Model base using Java interfaces & generics  
- Centralized utilities (waits, logging)  
- Enforced coding standards via Checkstyle  
- Published the framework as a Maven artifact  
**Result:** Adoption across 3 teams cut new‐script development time by **50%** and reduced duplicate code by **80%**. 🚀

**Q2. How have you leveraged Java 8+ features (Streams, Lambdas) to improve test code readability?**  
**Situation:** Data-driven tests manipulated large collections with verbose loops. 📋  
**Task:** Make filtering & transformation concise and expressive. ✂️  
**Action:**  
- Refactored methods with Java Streams & lambdas (`stream().filter().map()`)  
- Introduced method references for reusable filters  
- Used `Optional` to handle nulls gracefully  
**Result:** Reduced boilerplate by **40%**, tests became easier to read, and peer reviews flagged **30%** fewer style issues. 🎉



**Q3. Tell me about diagnosing a challenging bug in test code using Java debugging tools.**  
**Situation:** Intermittent `NullPointerException` in Selenium tests stalled CI builds. ⚠️  
**Task:** Identify root cause and eliminate flaky failures. 🔍  
**Action:**  
- Ran tests in IntelliJ with breakpoints  
- Inspected object lifecycles, discovered a race condition  
- Added synchronized waits and restructured setup/teardown  
**Result:** Flakiness dropped to **0%**, CI stability improved and trust was regained. 🛠️



**Q4. Explain how you managed test data and objects in Java for data-driven tests.**  
**Situation:** Needed to run the same suite against dozens of user profiles & regions. 🌐  
**Task:** Implement a robust data-driven solution. 📝  
**Action:**  
- Created a `TestDataProvider` utility reading JSON/YAML via Jackson  
- Mapped data to Java POJOs  
- Populated tests via TestNG’s `@DataProvider`  
- Validated schemas with JSON‐schema  
**Result:** Eliminated manual CSV handling; tests scaled to **100+** scenarios with minimal code changes. 📈



**Q5. Share an example of optimizing Java-based test execution for performance.**  
**Situation:** Full regression suite took **6 hours** to run. ⏳  
**Task:** Cut execution time without losing coverage. ✂️  
**Action:**  
- Parallelized tests using TestNG’s `@Parallel`  
- Pooled WebDriver instances  
- Lazy-loaded test data  
- Disabled non-critical logging  
**Result:** Execution time shrank to **90 minutes**, enabling daily overnight runs and faster feedback. ⚡

## ⚙️ 2. Automation & Testing: Cucumber · Selenium · Playwright

**Q6. How did you integrate Selenium WebDriver with a Page Object Model?**  
**Situation:** UI tests coupled locators directly in scripts. 🔗  
**Task:** Modularize locators & actions for reusability. 🛠️  
**Action:**  
- Defined page classes with `WebElement` fields & methods  
- Used a base `PageFactory` for initialization  
- Wrote clear action methods (e.g., `loginPage.submitCredentials()`)  
**Result:** Locator duplication dropped by **70%**, and updates were isolated to page classes. 📦



**Q7. Share an instance where you wrote a complex Cucumber step definition for a dynamic scenario.**  
**Situation:** Acceptance criteria required verifying variable table structures. 📊  
**Task:** Implement a flexible Cucumber step for any table. 🔄  
**Action:**  
- Created `Then the table should contain:` Gherkin step with a DataTable parameter  
- Parsed `DataTable` into a list of maps in Java  
- Compared against Selenium-scraped table via reflection  
**Result:** One step handled **20+** table validations, streamlining maintenance. 🎯



**Q8. Describe using Playwright to handle flaky UI elements.**  
**Situation:** Pop-ups & async loaders caused timeouts. ⏲️  
**Task:** Stabilize tests against dynamic content. 🛡️  
**Action:**  
- Used `page.waitForSelector()` with sensible timeouts  
- Targeted visible elements via `page.locator().first()`  
- Wrapped key actions in retry logic  
**Result:** Flakiness dropped from **15%** to under **2%**. 🎉



**Q9. Tell me about automating cross-browser tests with Selenium Grid or Playwright.**  
**Situation:** Needed coverage across Chrome, Firefox & Edge. 🌐  
**Task:** Scale tests in parallel across browsers. 🚀  
**Action:**  
- Deployed Selenium Grid on Docker  
- Parameterized browser in TestNG  
- Leveraged Playwright’s built-in cross-browser runner  
- Configured CI to spawn containers & aggregate reports  
**Result:** Full cross-browser suite ran in **<30 minutes**. ⏱️



**Q10. Explain how you designed reusable test libraries for Cucumber, Selenium & Playwright.**  
**Situation:** Teams built fragmented helper methods. 🧩  
**Task:** Create a shared automation library. 📚  
**Action:**  
- Developed a Java library module with generic utilities (waiters, screenshots, JSON parsing)  
- Published to Nexus with semantic versioning  
- Documented public APIs  
**Result:** Adopted by 3 projects, cutting new helper code by **60%** and ensuring consistency. ✅

## 📐 3. Methodologies: Test Strategy · Test Planning · BDD · Bug Triage · Agile Testing

**Q11. Describe how you developed a test strategy for a high-risk feature.**  
**Situation:** New payment component carried regulatory risk. 💳  
**Task:** Balance speed & thoroughness. ⚖️  
**Action:**  
- Led a risk assessment workshop  
- Prioritized smoke, functional, performance & security tests  
- Mapped scenarios to automation vs. manual  
- Defined entry/exit criteria  
**Result:** Strategy approved by stakeholders; caught 2 compliance issues pre-release. 🔒



**Q12. Tell me about creating & tracking a test plan for a major release.**  
**Situation:** Quarterly release with 50+ features. 📅  
**Task:** Ensure coverage, resource allocation & visibility. 🔍  
**Action:**  
- Drafted a Jira‐backed test plan: scope, schedule, roles, traceability matrix  
- Held daily stand-ups; updated dashboards  
- Escalated blockers promptly  
**Result:** Shipped on time with **100%** planned coverage and no critical post-release bugs. 🎉



**Q13. Share an example of using BDD to align on acceptance criteria.**  
**Situation:** UX & dev teams disagreed on “responsive design.” 📐  
**Task:** Prevent misalignment before development. 🛠️  
**Action:**  
- Facilitated a session to write Gherkin scenarios covering breakpoints, element rearrangement & performance  
- Reviewed feature files in retrospectives  
**Result:** UI regressions dropped by **75%**, and devs built to correct specs. 🚀



**Q14. Describe a time you triaged multiple defects & prioritized them effectively.**  
**Situation:** End-of-sprint saw 20 bugs across severities. ⚠️  
**Task:** Decide which to fix now vs. defer. 📋  
**Action:**  
- Convened triage with PM, dev & QA  
- Used a risk‐based matrix (severity × frequency)  
- Reclassified borderline issues; agreed on hotfix for P0/P1  
**Result:** 100% of P0/P1 fixed; P2/P3 parked for backlog. ✅



**Q15. Explain how you adapted testing practices in an Agile sprint with changing requirements.**  
**Situation:** Mid-sprint API spec changed significantly. 🔄  
**Task:** Update tests without derailing the timeline. 🕒  
**Action:**  
- Refactored API tests to contract-driven approach  
- Updated Cucumber scenarios  
- Communicated impact in stand-ups; reprioritized manual tests  
**Result:** Absorbed change with only a half-day delay; maintained confidence. 💪

## 📦 4. CI/CD & DevOps: Docker · Jenkins

**Q16. Describe how you containerized test environments with Docker.**  
**Situation:** “Works on my machine” issues plagued the team. 🐳  
**Task:** Ensure consistency across dev, CI & test. 🔄  
**Action:**  
- Wrote Dockerfiles bundling JDK, browsers & drivers  
- Used Docker Compose to orchestrate app + test containers  
- Published images to internal registry  
**Result:** Eliminated environment drift; developers ran tests locally with one command. ✅



**Q17. Tell me about integrating automated tests into a Jenkins pipeline.**  
**Situation:** QA ran tests manually post-deployments. 🛠️  
**Task:** Automate E2E & integration tests on every commit. 🔄  
**Action:**  
- Created a `Jenkinsfile` with stages: Build, Unit-Test, Dockerize, Deploy-to-Test, Run-Automation, Publish-Reports  
- Implemented parallel execution  
- Set up email/Slack notifications on failures  
**Result:** Feedback time dropped from hours to minutes; productivity soared. 🚀



**Q18. Explain managing test execution across environments using Docker Compose.**  
**Situation:** Tests required dependent services (DB, queues). 🔗  
**Task:** Spin up complete stack reliably for CI runs. 🐳  
**Action:**  
- Defined services in `docker-compose.yml` with healthchecks  
- Used network aliases for service discovery  
- Parameterized via `.env` files for dev vs. staging  
**Result:** Flaky environment issues dropped by **90%**, standardizing runs. 🎉



**Q19. Share an instance where you optimized Jenkins jobs to reduce feedback time.**  
**Situation:** Full suite ran sequentially for 2 hours. ⏰  
**Task:** Speed up CI feedback. ⚡  
**Action:**  
- Categorized tests (unit, smoke, regression)  
- Triggered smoke on PRs; regression nightly  
- Leveraged Jenkins agents for parallel runs  
- Cached dependencies between builds  
**Result:** PR feedback in **<10 minutes**; nightly regression in **45 minutes**. ✅



**Q20. How have you handled secrets & credentials in Jenkins and Docker?**  
**Situation:** Tests needed API keys & DB passwords. 🔒  
**Task:** Securely manage and inject secrets. 🗝️  
**Action:**  
- Stored secrets in Jenkins Credentials Store; referenced via `credentials()`  
- Used Docker secrets for containers  
- Rotated keys quarterly  
**Result:** No leaked credentials; passed security audit with zero findings. 🎉

## 🗄️ 5. Databases: MySQL

**Q21. Describe automating validation of MySQL schema changes.**  
**Situation:** DB migrations sometimes broke tests. ⚠️  
**Task:** Catch incompatible changes early. 🚦  
**Action:**  
- Integrated Flyway in tests against a fresh MySQL container  
- Wrote SQL to verify table/column presence  
- Failed build on mismatches  
**Result:** Prevented two breaking changes from reaching staging. 🛡️



**Q22. Tell me about writing SQL in Java to verify data integrity.**  
**Situation:** UI counts didn’t match backend aggregates. 📊❌  
**Task:** Automate cross-verification. 🔍  
**Action:**  
- Used JDBC to run `SELECT COUNT(*)`, `SUM()` queries  
- Compared to UI values via Selenium  
- Logged discrepancies for debugging  
**Result:** Caught a logic bug undercounting by **5%**; fixed pre-release. ✅



**Q23. Explain managing test data setup & teardown in MySQL.**  
**Situation:** Tests polluted the shared staging DB. 🧹  
**Task:** Isolate runs with clean data. 🔄  
**Action:**  
- Spun up ephemeral MySQL via Docker  
- Populated seed data with SQL scripts in Maven pre-test phase  
- Dropped tables in post-test cleanup  
**Result:** Each run started from a known state; eliminated contamination. 🧼



**Q24. Share an example of optimizing MySQL queries to speed up data-driven tests.**  
**Situation:** Complex joins slowed tests to minutes per query. 🐢  
**Task:** Improve execution time. ⚡  
**Action:**  
- Analyzed slow queries with `EXPLAIN`  
- Added appropriate indexes  
- Refactored joins into temp tables; batched queries  
**Result:** Query time dropped from **5s** to **0.3s**, shaving **15 minutes** off nightly suite. ⏱️



**Q25. How did you handle database migration testing & version control for MySQL schemas?**  
**Situation:** Multiple teams applied migrations independently, causing conflicts. 🔀  
**Task:** Centralize schema versioning. 📚  
**Action:**  
- Adopted Flyway with scripts in Git; enforced sequential numbering  
- Configured tests to validate current version  
- Reviewed new scripts in CI  
**Result:** Zero merge conflicts; reliable schema evolution across environments. 🎉
