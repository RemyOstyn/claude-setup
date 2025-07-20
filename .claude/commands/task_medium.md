Use sequential-thinking mcp and all its tools that you will need about the problem and how to solve it. You must ultrathink for the solution and use reasoning.

You must consider edge cases and follow best coding practices for everything. Never do bandaid fixes.

## Configuration

STEP 1: You must create a subagent with a task to investigate all codebase files and find the files related to the problem and always create a "REPORT.md" inside the claude-instance directory that gets automatically created for this task session which you will then read to learn the list of files needed for you to check in order to understand and solve the problem.

IMPORTANT: The subagent MUST only return the following response format and nothing else:

```
## Report Location:
The comprehensive investigation report has been saved to:
`[full path to REPORT.md file]`
```

After you finish reading the "REPORT.md" file, enter plan mode.

STEP 2: When the user accepts your plan, write it in a "PLAN.md" file inside the claude-instance directory that was automatically created for this task session.

Problem: $ARGUMENTS
