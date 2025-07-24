Use sequential-thinking mcp and all its tools that you will need about the problem and how to solve it. You must ultrathink for the solution and use reasoning.

You must consider edge cases and follow best coding practices for everything. Never do bandaid fixes.

## REPORT.md Structure Requirements

The REPORT.md file must organize identified files into three distinct classes:

**Class A (Core Files)**: Files directly related to the core problem that require modification to solve the issue. These are the primary files that must be changed to implement the solution.

**Class B (Enhancement Files)**: Files that would benefit from updates to complement the Class A changes. These files should be modified to improve consistency, user experience, or maintain system coherence with the core changes.

**Class C (Reference Files)**: Files with similar implementations or patterns that can serve as examples or templates for solving the Class A problem. These files demonstrate existing approaches and help guide the solution design.

### Classification Example:

If the problem is adding two columns (image and blueprint file) to a facilities database table:

-   **Class A**: Migration file, Facility model, frontend forms for facility creation/editing
-   **Class B**: Facility data grid component that should display the new image and file columns
-   **Class C**: Vehicle-related files that already implement image/file functionality and can serve as implementation reference

Each class should list specific file paths with brief explanations of their relevance to the problem.

## Configuration

### STEP 1: Investigation and Report Generation

You must create a subagent with a task to investigate all codebase files and find the files related to the problem and always create a "REPORT.md" inside the claude-instance directory that gets automatically created for this task session which you will then read to learn the list of files needed for you to check in order to understand and solve the problem.

IMPORTANT: The subagent MUST only return the following response format and nothing else:

```
## Report Location:
The comprehensive investigation report has been saved to:
`[full path to REPORT.md file]`
```

After you finish reading the "REPORT.md" file, enter plan mode.

### STEP 2: Plan Creation

When the user accepts your plan, write it in a "PLAN.md" file inside the claude-instance directory that was automatically created for this task session.

Problem: $ARGUMENTS
