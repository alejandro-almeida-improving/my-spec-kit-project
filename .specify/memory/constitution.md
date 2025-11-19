<!--
Sync Impact Report
- Version change: 1.0.1 -> 1.0.2
- Modified items: Remove Prettier references — ESLint-only policy; wording clarified
- Added sections: none (content translated and refined)
- Removed sections: none
- Templates reviewed:
  - .specify/templates/plan-template.md ✅ aligned
  - .specify/templates/spec-template.md ✅ aligned
  - .specify/templates/tasks-template.md ✅ aligned (tests optional — policy unchanged)
  - .specify/templates/checklist-template.md ✅ aligned
- Follow-up TODOs: none
-->

# my-spec-kit-project Constitution

## Core Principles

### Principle I: Static-First Web (STATIC-FIRST)
The application is a static website built with Next.js (Static Generation / ISR when necessary).
All pages and routes MUST prefer static pre-rendering; use of Server-Side Rendering (SSR) or dynamic APIs
must be justified by a clear business need. This is a MUST: favoring SSG/ISR reduces complexity,
cost, and improves performance.

### Principle II: Performance and Accessibility (PERFORMANCE & A11Y)
The project MUST follow best practices for performance (Core Web Vitals) and accessibility (WCAG AA as
the minimum target). Library and resource choices MUST prioritize bundle size and load time impact.

### Principle III: Code Style and Quality (NEXTJS GUIDELINES)
Code MUST follow Next.js and TypeScript guidelines: use the App Router where applicable, clear routes and
layouts, small composable components without unexpected side effects. ESLint MUST be integrated and enforced in PRs.

### Principle IV: Simplicity and Minimal Dependencies (SIMPLICITY)
Avoid unnecessary dependencies and heavy frameworks for simple functionality. Every external dependency
MUST include an explicit justification in the PR (benefit vs maintenance cost). Prefer platform-native
solutions (Next.js, native CSS, web APIs) over large abstractions.

### Principle V: Tests Optional — Not Required (NO_TESTS_REQUIRED)
Automated tests are explicitly NOT REQUIRED for this project: verification focuses on code reviews, linters,
and manual QA. Automated tests may be added at the team's discretion but are not a condition for merging
or deploying in this repository.

## Technical Restrictions

- Primary stack: Next.js with TypeScript, Tailwind CSS, and `shadcn/ui` for component patterns. Tailwind and
  shadcn MUST be used for styling and UI primitives unless a strong justification is provided.
- Use static hosting (Vercel, Netlify, S3+CDN, etc.); no additional server runtime is required unless explicitly justified.
- Optimize images and fonts using Next.js native utilities (`next/image`, `next/font`) where appropriate.
- Do not introduce additional server runtimes or heavy backend frameworks without an approved justification.

## Development Workflow

- Pull Requests: all PRs MUST pass linting (ESLint) and follow the project's formatting rules (editorconfig or ESLint autofix).
- Reviews: at least one approving code review is required before merge; reviewers verify:
  - adherence to principles (static-first, performance, accessibility),
  - absence of unnecessary dependencies,
  - changes do not negatively impact bundle size.
- Continuous integration: running linters and builds in CI is recommended; tests remain optional per project policy.

## Governance

- The Constitution is the project's governing document. Amendments require a PR that includes:
  1) Proposed text and the section to change; 2) Rationale and expected impact; 3) Migration plan if applicable.
- Approval: an amendment MUST be approved by at least one repository maintainer and merged into the `main` branch.
- Constitution versioning: use Semantic Versioning for the document:
  - MAJOR: incompatible governance changes or removal/redefinition of principles.
  - MINOR: addition of principles or substantial expansions.
  - PATCH: wording fixes, formatting, or minor clarifications.

**Version**: 1.0.2 | **Ratified**: 2025-11-19 | **Last Amended**: 2025-11-19

