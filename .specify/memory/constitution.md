<!--
Version change: 1.0.0 (initial creation)
List of modified principles:
  - PRINCIPLE_1_NAME -> Modularity
  - PRINCIPLE_2_NAME -> Clear Interfaces
  - PRINCIPLE_3_NAME -> Test-Driven Development (NON-NEGOTIABLE)
  - PRINCIPLE_4_NAME -> Continuous Integration & Deployment
  - PRINCIPLE_5_NAME -> Documentation & Readability
Added sections: None (placeholders filled)
Removed sections: None (placeholders filled)
Templates requiring updates:
  - .specify/templates/plan-template.md: ✅ updated
  - .specify/templates/spec-template.md: ✅ updated (no direct updates, but constitution principles apply)
  - .specify/templates/tasks-template.md: ✅ updated (no direct updates, but constitution principles apply)
  - .gemini/commands/*.toml: ✅ updated (no outdated references found)
Follow-up TODOs: None
-->
# Checkpoint Gemini Constitution
<!-- Example: Spec Constitution, TaskFlow Constitution, etc. -->

## Core Principles

### Modularity
<!-- Example: I. Library-First -->
Features are developed as self-contained, independently testable modules with clear responsibilities. Modules must minimize external dependencies and provide well-defined interfaces.

### Clear Interfaces
<!-- Example: II. CLI Interface -->
All modules expose functionality through consistent, well-documented interfaces. These interfaces should prioritize clarity and ease of use, supporting both human and programmatic interaction where applicable.

### Test-Driven Development (NON-NEGOTIABLE)
<!-- Example: III. Test-First (NON-NEGOTIABLE) -->
Adherence to Test-Driven Development (TDD) is mandatory. Tests must be written and approved before implementation, following a strict Red-Green-Refactor cycle. This ensures high code quality, maintainability, and verifies functionality against requirements.

### Continuous Integration & Deployment
<!-- Example: IV. Integration Testing -->
All changes are subject to automated build, test, and deployment processes. A robust CI/CD pipeline ensures code quality, rapid delivery, and minimizes regressions, focusing on quick feedback loops and reliable deployments.

### Documentation & Readability
<!-- Example: V. Observability, VI. Versioning & Breaking Changes, VII. Simplicity -->
Code must be self-documenting where possible, complemented by clear and concise external documentation for complex logic, APIs, and architectural decisions. Readability is paramount, facilitating understanding and collaboration among team members.

## Development Standards
<!-- Example: Additional Constraints, Security Requirements, Performance Standards, etc. -->

All code must adhere to established coding standards, style guides, and project-specific conventions. Static analysis tools and linters will be used to enforce these standards. Compliance is a prerequisite for code review approval.

<h2>Review Process</h2>
<!-- Example: Development Workflow, Review Process, Quality Gates, etc. -->

All code changes require peer review before merging. Reviews focus on correctness, maintainability, adherence to principles, and impact on overall system health. Constructive feedback and knowledge sharing are integral to this process.

## Governance
<!-- Example: Constitution supersedes all other practices; Amendments require documentation, approval, migration plan -->

This Constitution outlines the fundamental principles guiding project development. Amendments require a documented proposal, team consensus, and a clear migration plan. Compliance is verified during code reviews and continuous integration.

**Version**: 1.0.0 | **Ratified**: 2026-06-05 | **Last Amended**: 2026-06-05
<!-- Example: Version: 2.1.1 | Ratified: 2025-06-13 | Last Amended: 2025-07-16 -->
