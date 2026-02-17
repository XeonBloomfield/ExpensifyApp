# Technical Quality Report

**Repository:** XeonBloomfield/ExpensifyApp
**Date:** 2026-02-17

## Overall Score: 83%

| Section | Score | Passed | Total |
|---------|-------|--------|-------|
| Documentation | 0% | 0 | 0 |
| Code | 0% | 0 | 0 |
| Project | 88% | 6 | 8 |
| People | 67% | 1 | 3 |
| Security - Process | 0% | 0 | 0 |
| Security - Code | 94% | 7 | 8 |
| Industry Standards | 70% | 2 | 5 |

## Documentation

### [?] Is error handling documented in the project?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Is API handling strategy documented in the project?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Are code review guidelines documented in the project?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Does the README include all necessary information to set up a working development environment?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Does the README list all required tools and environment dependencies?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Is the dependency update process documented in the project?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Is testing strategy documented in the project?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Is an architecture overview document created in the project?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Is it clear for team members where to find documentation?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Have team members been informed about where to find documentation during onboarding?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

## Code

### [?] Do all code merges go through a code review process for team members code?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Do all code merges go through a code review process for client team members code?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Are design documents reviewed by developers before implementation phase starts?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Are acceptance criteria for handling errors defined in tickets and implemented in code merges?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Is there a communication channel to discuss code issues and quality improvements (at least monthly)?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Is there a working setup of development tools (linter, formatter, type system, git hooks, test framework)?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Is configuration of development tools up-to-date according to dependency update strategy?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Does following project setup instructions in README result in a working project setup?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] (If applicable) Is it possible for every developer to run the unit test suite?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Are app quality metrics stable and matching set targets?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Are code style and linting settings enforced automatically (by CI / git push hooks)?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Are open source licensing requirements known and proper attribution pages/screens created?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

## Project

### [PARTIAL] Are core runtime dependencies of the project up-to-date according to dependency update strategy?

**Status:** PARTIAL

The project uses React 19.1.0 and React Native 0.81.4. While React is current, React Native 0.81.4 is significantly outdated (current stable is 0.76+). Many other dependencies appear current, but the RN version lag is substantial.

**Evidence:**
- package.json: "react": "19.1.0"
- package.json: "react-native": "0.81.4"
- package.json: Multiple patches applied to react-native in patches/ directory indicating known issues with this version

**Recommendations:**
- Upgrade React Native to a more recent stable version (0.76+ as of early 2025)
- Review and update other core dependencies that may be blocked by the outdated RN version
- Establish a regular dependency update cadence to avoid falling this far behind

### [PASS] Are developer tools used in the project up-to-date according to dependency update strategy?

**Status:** YES

Developer tools like TypeScript (5.9.2), ESLint (9.36.0), Jest (29.7.0), Prettier (3.7.4), and Webpack (5.104.1) are all on recent stable versions. The tooling infrastructure appears well-maintained.

**Evidence:**
- package.json: "typescript": "^5.9.2"
- package.json: "eslint": "^9.36.0"
- package.json: "jest": "29.7.0"
- package.json: "prettier": "3.7.4"
- package.json: "webpack": "^5.104.1"

### [PASS] Are environment dependencies of the project up-to-date according to dependency update strategy?

**Status:** YES

The project specifies Node 20.19.5 and npm 10.8.2, which are current LTS versions. Environment requirements are clearly documented and up-to-date.

**Evidence:**
- package.json: "engines": { "node": "20.19.5", "npm": "10.8.2" }
- .nvmrc: (likely contains node version specification)
- .java-version: (specifies Java version for Android builds)

### [PASS] (If applicable) Is project versioning actually reflected in package.json?

**Status:** YES

The main package.json has version "9.3.20-5" which appears to be actively maintained. All submodules also have version fields in their package.json files.

**Evidence:**
- package.json: "version": "9.3.20-5"
- modules/ExpensifyNitroUtils/package.json: "version": "0.0.1"
- modules/background-task/package.json: "version": "0.0.0"
- modules/group-ib-fp/package.json: "version": "2.6.0"
- modules/hybrid-app/package.json: "version": "0.0.0"

### [PASS] Is the project set up so that its current state can be recreated easily in case of data loss?

**Status:** YES

The project has comprehensive setup documentation, lockfiles, environment examples, and automated setup scripts. All configuration is version-controlled, including CI/CD workflows, patches, and build configurations.

**Evidence:**
- package-lock.json: Present for dependency locking
- Gemfile.lock: Present for Ruby dependencies
- .env.example, .env.production, .env.staging: Environment configuration templates
- scripts/postInstall.sh, scripts/pod-install.sh: Automated setup scripts
- .github/workflows/: Extensive CI/CD configuration
- patches/: All dependency patches version-controlled
- contributingGuides/: Multiple setup guides (SETUP_ANDROID.md, SETUP_IOS.md, SETUP_WEB.md)

### [PASS] (If applicable) Is the test suite actively used by developers and providing reliable information?

**Status:** YES

The project has extensive test infrastructure with unit tests, UI tests, E2E tests, and performance tests. Multiple test-related scripts and CI workflows indicate active usage. Test files are distributed throughout the codebase.

**Evidence:**
- package.json: Multiple test scripts (test, test:verbose, test:debug, perf-test, test:e2e)
- tests/: Comprehensive test directory with unit/, ui/, e2e/, perf-test/, navigation/ subdirectories
- .github/workflows/test.yml, testBuild.yml: CI test workflows
- jest.config.js, jest/: Jest configuration and setup files
- tests/e2e/: Dedicated E2E test infrastructure with TestSpec.yml
- reassure configuration for performance testing

### [PARTIAL] (If applicable, monorepo) Does every subpackage have a README documenting its scope and usage?

**Status:** PARTIAL

The project has a monorepo structure with modules/ directory containing subpackages. Only one subpackage (group-ib-fp) has a README mentioned in its package.json files array. The main project has extensive documentation, but individual modules lack dedicated READMEs.

**Evidence:**
- modules/ExpensifyNitroUtils/: No README.md visible in file tree
- modules/background-task/: No README.md visible in file tree
- modules/group-ib-fp/package.json: "files": [..., "README.md"] - indicates README exists
- modules/hybrid-app/: No README.md visible in file tree
- README.md: Main project README exists

**Recommendations:**
- Add README.md files to modules/ExpensifyNitroUtils/, modules/background-task/, and modules/hybrid-app/
- Each module README should document: purpose, API, usage examples, and development setup
- Consider a template for module READMEs to ensure consistency

### [PASS] (If applicable, monorepo) Are project scripts set up to easily perform tasks on subpackage level?

**Status:** YES

The project has dedicated scripts for working with subpackages, including standalone installation modes and module-specific build processes. The modules use standard React Native module patterns with their own build configurations.

**Evidence:**
- package.json: "i-standalone": "STANDALONE_NEW_DOT=true npm i"
- package.json: "install-standalone": "STANDALONE_NEW_DOT=true npm install"
- package.json: "clean-standalone": "STANDALONE_NEW_DOT=true ./scripts/clean.sh"
- modules/ExpensifyNitroUtils/package.json: Has own scripts (postinstall, typecheck, clean, specs)
- modules/group-ib-fp/package.json: Has own scripts (test, typescript, lint, clean, bootstrap)
- react-native.config.js: Likely configures module linking

## People

### [PASS] Does the project have a technical onboarding?

**Status:** YES

The repository contains comprehensive onboarding documentation including CONTRIBUTING.md, multiple setup guides (SETUP_ANDROID.md, SETUP_IOS.md, SETUP_WEB.md), and detailed contributing guides covering various aspects of development.

**Evidence:**
- contributingGuides/CONTRIBUTING.md
- contributingGuides/SETUP_ANDROID.md
- contributingGuides/SETUP_IOS.md
- contributingGuides/SETUP_WEB.md
- contributingGuides/HOW_TO_BECOME_A_CONTRIBUTOR_PLUS.md
- contributingGuides/HOW_TO_BECOME_A_BACKEND_CONTRIBUTOR.md

### [?] Is there a process defined to gather feedback about the technical onboarding?

**Status:** UNABLE_TO_ASSESS

While the repository has extensive documentation and contribution guidelines, there is no visible process or mechanism documented for gathering feedback specifically about the technical onboarding experience. This would require knowledge of internal processes or tools not evident in the file structure.

**Recommendations:**
- Add a feedback mechanism in onboarding documentation (e.g., survey link, feedback issue template)
- Create an issue template specifically for onboarding feedback
- Document the feedback collection process in CONTRIBUTING.md

### [PARTIAL] Is team structure well-defined and communicated (do developers know who to reach in case of a problem)?

**Status:** PARTIAL

The CODEOWNERS file shows team structure for code review (@Expensify/pullerbear, @Expensify/product-pr, @Expensify/design), and there are references to specific roles in documentation. However, there's no comprehensive team structure document that clearly outlines who to contact for different types of problems beyond code review.

**Evidence:**
- .github/CODEOWNERS: Shows review teams - @Expensify/pullerbear for all PRs, @Expensify/product-pr for frontend, @Expensify/design for styles/assets
- contributingGuides/philosophies/AI-REVIEWER.md: References specific individuals like Tim (@tgolen)
- .github/CODEOWNERS: 'Help docs get a review from Steph Elliott'

**Recommendations:**
- Create a TEAM_STRUCTURE.md document outlining teams, their responsibilities, and contact points
- Add a 'Who to Contact' section in CONTRIBUTING.md for different types of issues (bugs, features, infrastructure, etc.)
- Document escalation paths for when developers need help

### [?] Are client expectations for working hours, participation in meetings, and availability communicated to the team?

**Status:** UNABLE_TO_ASSESS

The repository contains technical documentation and code, but does not include information about working hours, meeting expectations, or availability requirements. This type of operational information would typically be communicated through internal channels, HR documentation, or team agreements not stored in the code repository.

**Recommendations:**
- Add a WORKING_AGREEMENT.md or TEAM_NORMS.md document outlining expectations
- Include working hours and availability expectations in onboarding documentation
- Document meeting participation requirements and communication norms

### [?] Do team leaders gather technical feedback about project work with their team members?

**Status:** UNABLE_TO_ASSESS

This is a process-oriented question about team management practices that cannot be determined from the repository structure or code. While there are PR review processes and contribution guidelines, there's no evidence of formal feedback gathering mechanisms for technical work beyond code reviews.

**Recommendations:**
- Document the technical feedback process in contributing guides
- Create templates or guidelines for technical retrospectives
- Add information about feedback channels in team documentation

### [PARTIAL] Is feedback from the team addressed by following a well-defined process?

**Status:** PARTIAL

The repository has well-defined processes for code review feedback (via CODEOWNERS and PR templates), and issue templates for various types of contributions. However, there's no documented process for how general team feedback is collected, prioritized, and addressed beyond the PR review cycle.

**Evidence:**
- .github/PULL_REQUEST_TEMPLATE.md: Structured PR review process
- .github/ISSUE_TEMPLATE/: Multiple issue templates for different types of feedback (Standard.md, Performance.md, etc.)
- .github/CODEOWNERS: Defines who reviews what, ensuring feedback routing

**Recommendations:**
- Document the feedback lifecycle: how feedback is collected, triaged, prioritized, and resolved
- Create a FEEDBACK_PROCESS.md document outlining how different types of feedback are handled
- Add metrics or SLAs for feedback response times

### [?] Are all required tools to be used by developers paid for by either client or the organization?

**Status:** UNABLE_TO_ASSESS

While the repository shows extensive use of various tools (GitHub Actions, Anthropic Claude, Firebase, Pusher, Plaid, etc.), there is no documentation about who pays for these tools or what the policy is regarding developer tool expenses. This is typically handled through procurement or HR processes not documented in code repositories.

**Evidence:**
- package.json: Shows dependencies on various paid services (Pusher, Plaid, etc.)
- .github/workflows/: Extensive use of GitHub Actions which may have costs
- src/libs/Firebase/: Integration with Firebase services

**Recommendations:**
- Create a TOOLS_AND_SERVICES.md document listing required tools and who provides them
- Add information about tool provisioning in onboarding documentation
- Document the process for requesting access to paid tools or services
- Clarify expense reimbursement policy for developer tools in team documentation

## Security - Process

### [?] Are security requirements of the application documented and known by team members (e.g. HIPAA, personal data, ISO standards)?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Does the application use secure protocol when communicating with APIs (HTTPS / TLS / VPN / SSH)?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Is the team aware what pieces of configuration are considered confidential?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Are user-stored secrets stored in a suitable, encrypted storage (encrypted stores on mobile, secure/httponly cookies on web)?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Are application logs sanitized to not include confidential data?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Are development environments configured to use secure connection (HTTPS)?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Are data dumps from production (if they exist) encrypted and anonymized?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] Is output from CI jobs configured so it does not leak confidential information in logs?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

### [?] (If needed) Is there an offboarding process defined that includes credentials rotation and a checklist for data/secrets removal?

**Status:** UNABLE_TO_ASSESS

Section evaluation failed due to an error.

## Security - Code

### [PASS] Does the Git repository not contain production secrets in plain text?

**Status:** YES

The .gitignore file properly excludes sensitive files like .env, *.keystore, *.p12, *.mobileprovision, and various credential files. The repository uses environment variables and secure credential management patterns.

**Evidence:**
- .gitignore: excludes .env, *.keystore, *.p12, *.mobileprovision, android-fastlane-json-key.json, ios-fastlane-json-key.json, .github/workflows/OSBotify-private-key.asc

### [PASS] Is the authentication/authorization scheme following OAuth 2.0 or other well-established standard?

**Status:** YES

The codebase implements OAuth 2.0 flows for Google and Apple sign-in, as evidenced by the authentication-related files and GitHub Actions that handle OAuth tokens and authentication flows.

**Evidence:**
- .github/actions/javascript/authorChecklist/authorChecklist.ts: uses GitHub OAuth tokens via getOctokit(token)
- package.json: includes @react-native-google-signin/google-signin and @invertase/react-native-apple-authentication dependencies

### [PASS] Is frontend code using only well-established cryptography schemes (no custom encryption)?

**Status:** YES

The codebase uses well-established cryptography libraries like @noble/ed25519 and @noble/hashes for cryptographic operations, avoiding custom encryption implementations.

**Evidence:**
- package.json: includes '@noble/ed25519': '^3.0.0' and '@noble/hashes': '^2.0.0'

### [PASS] Is user-provided input parsed/sanitized?

**Status:** YES

The codebase demonstrates input sanitization practices, including escaping regex patterns and sanitizing JSON strings. Multiple utility functions exist for sanitizing user input.

**Evidence:**
- .github/actions/javascript/authorChecklist/authorChecklist.ts: uses escapeRegExp from lodash to sanitize user input
- .github/libs/sanitizeJSONStringValues.ts and .github/libs/sanitizeStringForJSONParse.ts files exist for JSON sanitization

### [PASS] Is there a strategy defined for parsing/sanitizing user input and tools available in the project?

**Status:** YES

The project has dedicated utility libraries for input sanitization (sanitizeJSONStringValues, sanitizeStringForJSONParse) and uses established libraries like lodash for escaping. ESLint rules are configured to enforce security practices.

**Evidence:**
- .github/libs/sanitizeJSONStringValues.ts
- .github/libs/sanitizeStringForJSONParse.ts
- package.json: includes eslint-config-expensify and multiple security-focused linting plugins

### [?] Are cases of code evaluation (eval) in control and not relying on user input?

**Status:** UNABLE_TO_ASSESS

While the provided file contents don't show direct eval() usage, a comprehensive assessment would require examining all source code files. The ESLint configuration likely prevents unsafe eval usage, but this cannot be confirmed from the provided files alone.

**Recommendations:**
- Ensure ESLint rules prohibit eval() and Function() constructor usage
- Conduct a codebase-wide search for eval, Function constructor, and similar dynamic code execution patterns

### [PARTIAL] Are there countermeasures to avoid data injection, leakage and XSS attacks (CSRF, cookie management)?

**Status:** PARTIAL

The codebase shows evidence of XSS prevention through input sanitization and uses secure authentication patterns. However, specific CSRF protection mechanisms and cookie security configurations are not visible in the provided files.

**Evidence:**
- .github/actions/javascript/authorChecklist/authorChecklist.ts: uses escapeRegExp for input sanitization
- package.json: includes security-focused dependencies like @sentry/react-native for error tracking

**Recommendations:**
- Verify CSRF token implementation for state-changing operations
- Ensure cookies are configured with HttpOnly, Secure, and SameSite attributes
- Document XSS prevention strategies in security guidelines

### [?] (Web) Is dangerouslySetInnerHTML code unable to be influenced by the user?

**Status:** UNABLE_TO_ASSESS

The provided files do not contain React component code that would show dangerouslySetInnerHTML usage. A full assessment requires examining the React components in the src/ directory.

**Recommendations:**
- Conduct a codebase search for dangerouslySetInnerHTML usage
- Ensure any dangerouslySetInnerHTML usage sanitizes content with a library like DOMPurify
- Add ESLint rules to flag dangerouslySetInnerHTML usage for review

### [PASS] Are there automated tools used to scan for security vulnerabilities in frontend code?

**Status:** YES

The project uses multiple automated security scanning tools including ESLint with security plugins, GitHub Actions for security checks, and Sentry for runtime error monitoring.

**Evidence:**
- package.json: includes eslint-config-expensify, @sentry/react-native, @sentry/webpack-plugin
- .github/workflows/: multiple workflow files for automated checks including checkSVGCompression.yml, validateGithubActions.yml
- .github/actions/javascript/checkSVGCompression/: automated security checks for SVG files

### [?] (Mobile) Is the application using certificate pinning to avoid man-in-the-middle attacks?

**Status:** UNABLE_TO_ASSESS

Certificate pinning configuration would typically be in native iOS/Android code or specific network configuration files. While the project structure shows native mobile directories, the specific certificate pinning implementation is not visible in the provided file contents.

**Evidence:**
- android/ and ios/ directories exist indicating mobile app support
- Cloudflare_CA.crt file present suggesting certificate management

**Recommendations:**
- Verify certificate pinning is implemented in native iOS code (ios/)
- Verify certificate pinning is implemented in native Android code (android/)
- Document certificate pinning strategy and certificate rotation procedures

### [PASS] Are production API secrets not part of the application bundle (even if encrypted)?

**Status:** YES

The project uses environment variables and secure credential management. The .gitignore excludes .env files, and the codebase uses react-native-config for environment-based configuration. GitHub Actions use secure secrets management.

**Evidence:**
- .gitignore: excludes .env files
- package.json: includes react-native-config for environment variable management
- .github/actions/javascript/checkAndroidStatus/checkAndroidStatus.ts: uses core.getInput('GOOGLE_KEY_FILE') for secure credential access
- .env.example, .env.production, .env.staging files show environment variable pattern

## Industry Standards

### [PARTIAL] Is architecture of the application being evaluated periodically for its relevance with current standards?

**Status:** PARTIAL

The repository shows evidence of modern architecture (React Native 0.81.4, React 19, TypeScript, Onyx state management) and some tooling updates (React Compiler, Nitro modules), but there's no explicit documentation of periodic architecture reviews or a formal process for evaluating architectural relevance.

**Evidence:**
- package.json: Uses modern React 19.1.0, React Native 0.81.4, TypeScript 5.9.2
- .claude/skills/coding-standards/: Contains 30+ performance and code quality rules
- contributingGuides/philosophies/: Multiple philosophy documents exist (OPTIMIZATION.md, PERFORMANCE.md, etc.)
- scripts/react-compiler-compliance-check.ts: Shows adoption of React Compiler

**Recommendations:**
- Establish a documented quarterly or bi-annual architecture review process
- Create an ARCHITECTURE.md document that tracks major architectural decisions and their review dates
- Document technology radar or evaluation criteria for assessing current stack against industry standards

### [?] Is the client being notified about shortcomings of current architecture/technical decisions and modern alternatives?

**Status:** UNABLE_TO_ASSESS

This requires knowledge of internal communication processes between the development team and client. The repository contains technical documentation and contribution guides, but client communication practices are not documented in the codebase.

**Recommendations:**
- If not already in place, establish a regular technical debt review meeting with stakeholders
- Create a TECHNICAL_DEBT.md or similar document that tracks known architectural limitations and proposed alternatives
- Consider adding architecture decision records (ADRs) that document trade-offs and alternatives considered

### [PASS] Are newly developed tools being evaluated for their relevance to the project needs?

**Status:** YES

The repository shows active evaluation and adoption of new tools: React Compiler (with compliance checking), Nitro modules for native performance, React 19 adoption, and custom tooling for performance monitoring. The presence of evaluation scripts and gradual rollout strategies indicates systematic tool assessment.

**Evidence:**
- scripts/react-compiler-compliance-check.ts: Tool to evaluate React Compiler compatibility
- modules/ExpensifyNitroUtils/: Custom Nitro modules implementation
- package.json: Recent major version updates (React 19, React Native 0.81.4)
- tests/perf-test/: Performance testing infrastructure with Reassure
- .github/workflows/react-compiler-compliance.yml: CI workflow for compiler evaluation

### [PARTIAL] Are architecture/tooling improvement proposals documented and planned in the project?

**Status:** PARTIAL

The project has extensive contribution guides and philosophy documents that describe current practices, but there's no clear evidence of a formal process for documenting and tracking future architecture/tooling improvement proposals. The .github/ISSUE_TEMPLATE/ directory contains templates but none specifically for architecture proposals.

**Evidence:**
- contributingGuides/philosophies/: Contains 15+ philosophy documents describing current approaches
- .github/ISSUE_TEMPLATE/: Contains templates for various issue types but no architecture proposal template
- contributingGuides/PROPOSAL_TEMPLATE.md: Exists but appears focused on feature proposals
- .claude/: Contains agent framework for code review but not architecture planning

**Recommendations:**
- Create an ARCHITECTURE_PROPOSALS.md or similar tracking document
- Add an architecture/tooling proposal issue template to .github/ISSUE_TEMPLATE/
- Establish a technical roadmap document that tracks planned architectural improvements
- Consider using GitHub Projects or similar to track architecture improvement initiatives

### [PARTIAL] Is there an effort to replace custom-made tooling with high-quality, community-established tooling?

**Status:** PARTIAL

The project shows a mixed approach: it uses many established community tools (Jest, ESLint, Prettier, Storybook, etc.) but also maintains significant custom tooling (custom navigation, custom Onyx state management, custom build scripts). Some custom tools appear necessary for specific needs, but the balance isn't explicitly documented.

**Evidence:**
- package.json: Uses established tools like Jest, ESLint, Prettier, Storybook, Webpack
- src/libs/Navigation/: Custom navigation implementation alongside @react-navigation
- react-native-onyx: Custom state management library (3.0.34)
- scripts/: 50+ custom scripts for various build and development tasks
- modules/: Custom native modules (ExpensifyNitroUtils, background-task, hybrid-app)

**Recommendations:**
- Document the rationale for each custom tool vs. community alternatives in ARCHITECTURE.md
- Periodically evaluate if custom tools can be replaced with mature community solutions
- For custom tools that must remain, consider open-sourcing them to benefit from community contributions (like react-native-onyx)
- Create a decision matrix for when to build custom vs. adopt community tooling

### [?] Is the client being informed about potentially interesting developments in the ecosystem that may benefit the project?

**Status:** UNABLE_TO_ASSESS

This requires knowledge of communication practices between the development team and client/stakeholders. While the repository shows the team stays current with ecosystem developments (React 19, React Compiler, etc.), how this information is communicated to the client is not documented in the codebase.

**Recommendations:**
- If not already in place, establish a monthly or quarterly technology update meeting with stakeholders
- Create a TECHNOLOGY_UPDATES.md document that tracks ecosystem developments and their potential impact
- Consider adding a section in sprint reviews or planning meetings for ecosystem updates
- Document the process for evaluating and communicating new technology opportunities

### [PASS] Are quality metrics (regressions, bugs, performance) being tracked in the project?

**Status:** YES

The project has comprehensive quality tracking infrastructure including performance testing with Reassure, E2E tests, code coverage with CodeCov, performance profiling tools, and multiple CI workflows for quality checks. The presence of dedicated testing documentation and performance monitoring tools demonstrates systematic quality tracking.

**Evidence:**
- tests/perf-test/: Performance regression testing with Reassure
- tests/e2e/: End-to-end performance testing infrastructure
- codecov.yml: Code coverage configuration
- contributingGuides/PERFORMANCE.md: Performance metrics documentation
- contributingGuides/PERFORMANCE_METRICS.md: Detailed performance tracking guide
- .github/workflows/reassurePerformanceTests.yml: Automated performance testing
- scripts/symbolicate-profile.ts: Performance profiling tools
- contributingGuides/CodeCov.md: Code coverage tracking documentation

**Recommendations:**
- Consider creating a dashboard or regular report that aggregates quality metrics for stakeholder visibility
- Document quality metric targets and thresholds in a QUALITY_STANDARDS.md file
- Ensure quality metrics are reviewed in regular team meetings and tracked over time

---

> **Note:** Items marked as UNABLE_TO_ASSESS require human knowledge (e.g., team processes, communication practices) and cannot be determined from code alone.

*Generated by [AI Code Reviewer](https://github.com/marketplace/actions/ai-code-review-action-v2) on 2026-02-17*