Use sequential-thinking mcp and all its tools that you will need about the problem and how to solve it. You must ultrathink for the solution and use reasoning.

You must consider edge cases and follow best coding practices for everything. Never do bandaid fixes.

## Configuration

1. If user types the keyword I_T, you must create a subagent with a task to investigate all codebase files and find the files related to the problem and create a "Report.md" on project root which you will then read to learn the list of files needed for you to check in order to understand and solve the problem. YOU MUST NEVER read the subagents results directly from the subagent, you have to wait until the subagent has finished executing its task and only then search for the "Report.md" file on project root. After you finish reading the "Report.md" file, enter plan mode.

Problem: $ARGUMENTS
